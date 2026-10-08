---
myst:
  html_meta:
    description: <WIP>
---

(how-to-guides-install-with-tpm-fde)=
# Use the REST API to install Ubuntu with TPM-FDE

This guide shows you how to use the snapd REST API to install Ubuntu with [hardware-backed Full Disk Encryption](https://ubuntu.com/desktop/docs/en/latest/explanation/hardware-backed-disk-encryption/#hardware-backed-disk-encryption) (TPM-FDE).

Refer to the {ref}`snapd REST API reference<reference-development-snapd-rest-api>` for a list of all actions and endpoints. For general instructions in {ref}`the guide on how to use the REST API<how-to-guides-manage-snaps-use-the-rest-api>`.

This guide is aimed at developers working on GUI-based custom Ubuntu installers. While the API can be called directly, this guide assumes that a GUI exists between API calls and end user.

## Get system label

To install Ubuntu with TPM-FDE, you need to identify the system where it will be installed. In the snapd REST API, systems are identified with a label.

To find the label of the system where you want to install Ubuntu with TPM-FDE, make a `GET` request to `/v2/systems`. This will return `200 OK` with a response body.

Within the `result` field of the response body there will be a list of available systems. Each system will include a `label`. For example:

```json
{
  ...
  "systems": [
    {
      "current": true,
      "default-recovery-system": true,
      "label": "20240522",
      "model": {
          "model": "my-device",
          "brand-id": "example-brand",
          "display-name": "My Device"
      },
      ...
    }
  ]
}
```

The system label will be used to [perform the relevant pre-install checks](#perform-pre-install-checks).

## Perform pre-install checks

To perform the pre-install checks, use the system's label to make a `GET` request to `/v2/systems/{label}` (replacing `{label)` with your system's label). This will return `200 OK` with a response body. 

The `result` field of the response body will include all the relevant details about this system. The field `storage-encryption` includes details about the system's storage encryption capabilities. It can also include errors that need to be adressed before proceeding with the installation.

### Encryption is available

If encryption is available, the `storage-encryption` will state it clearly (under `support`) and will include no errors. For example:

```json
{
  "storage-encryption": {
    "support": "available",
    "features": [
      "passphrase-auth",
      "pin-auth"
    ],
    "storage-safety": "prefer-encrypted",
    "encryption-type": "cryptsetup",
    "requirements": [
      "volumes-auth"
    ]
  }
}
```

You should note the requirements and features, and move on to [setup storage encrytpion](#setup-storage-encryption).

### Encryption is unavailable due to recoverable errors

If encryption is unavailable, due to errors that can be recovered, `storage-encryption` include `unavailable-reason` and a non-empty array of `availability-check-errors`. For example:

```json
{
  "storage-encryption": {
    "support": "unavailable",
    "features": [
      "passphrase-auth",
      "pin-auth"
    ],
    "storage-safety": "prefer-encrypted",
    "unavailable-reason": "not encrypting device storage as checking TPM gave: error with TPM2 device: TPM2 device is present but is currently disabled by the platform firmware",
    "availability-check-errors": [
      {
        "kind": "tpm-device-disabled",
        "message": "error with TPM2 device: TPM2 device is present but is currently disabled by the platform firmware",
        "actions": [
          "enable-tpm-via-firmware",
          "enable-and-clear-tpm-via-firmware",
          "reboot-to-fw-settings"
        ]
      }
    ],
    "requirements": [
      "volumes-auth"
    ]
  }
}
```

In this example, the system has a TPM 2.0 device disabled by the firmware. This error can be recovered by the API by executing the actions within the `actions` array in the order by which they are presented. 

The initial `GET` request to `/v2/systems/{label}` creates an in-memory pre-install check context that will be reused while fixing the errors. This context is destroyed upon a new `GET` request to the same endpoint and upon reboot. See the [section on how to fix encryption support](#fix-encryption-support) for guidelines about how to fix these errors.

### Encryption is unavailable

If the system does not support encryption, `storage-encryption` will include `unavailable-reason`, but no `availability-check-errors`. For example:

```json
{
  "storage-encryption": {
    "support": "unavailable",
    "features": [
      "passphrase-auth",
      "pin-auth"
    ],
    "storage-safety": "prefer-encrypted",
    "unavailable-reason": "cannot use encryption with the gadget, disabling encryption: gadget does not support encrypted data: required partition with system-save role is missing",
    "requirements": [
      "volumes-auth"
    ]
  }
}
```

In this example, encryption is not possible because the gadget lacks a system-save partition. This error cannot be recovered by the API and requires the usage of an encryption-compatible gadget. No further steps are applicable until the gadget is replaced.

## Perform pre-install recovery actions

If [encryption is unavailable due to recoverable errors](#encryption-is-unavailable-due-to-recoverable-errors), you can fix them by performing the actions listed in the `actions` array of each error (listed in `availability-check-errors`). These actions should be performed in the same order by which they appear in that array.

Some actions can be performed by making a `POST` request to `/v2/systems/{label}` with a request body specifying the execution of the API action `fix-encryption-support` and the concrete fix to be applied. For example:

```json
{
  "action": "fix-encryption-support",
  "fix-action": "enable-tpm-via-firmware"
}
```

If successful, this will return `200 OK` with a response body. The `result` field of the response body with include the system details. The `storage-encryption` field will be updated and might show different errors. For example

```json
{
  "storage-encryption": {
    "support": "unavailable",
    "features": [
      "passphrase-auth",
      "pin-auth"
    ],
    "storage-safety": "prefer-encrypted",
    "unavailable-reason": "not encrypting device storage as checking TPM gave: a reboot is required to complete the action",
    "availability-check-errors": [
      {
        "kind": "reboot-required",
        "message": "a reboot is required to complete the action",
        "actions": [
          "reboot"
        ]
      }
    ],
    "requirements": [
      "volumes-auth"
    ]
  }
}
```

In this example, the next action is a reboot of the system. This is not a fix to be requested through `fix-encryption-support`, but rather an instruction for the installer or the user. The same applies to actions `shutdown`, `reboot-to-fw-settings`, `contact-oem`, and `contact-os-vendor`.

Rebooting the system will destroy the in-memory pre-install check context that was created with the initial `GET` request to `/v2/systems/{label}`. After rebooting, a new `GET` request to the same endpoint should be made, followed by new requests to fix encryption support, if necessary. Keep in mind that the order by which the fix actions are executed should be the same as the order by which they appear in the `actions` array of an error in `availability-check-errors`. 

Once the system details about storage encryption show that [encryption is available](#encryption-is-available), you are ready to [install Ubuntu with TPM-FDE](#install-ubuntu-with-tpm-fde).

## Install Ubuntu with TPM-FDE

Now that the pre-install checks are completed, you can install Ubuntu with TPM-FDE. While the actual installation will only take place after a reboot, these instructions show how the REST API can be used to configure it.

### Add a PIN or passphrase

The `storage-encryption` field in the system details may include both `requirements` and `features`. For example:

```json
{
  ...
  "features": ["passphrase-auth", "pin-auth"],
  "requirements": ["volumes-auth"],
  ...
}
```

If `volumes-auth` is present in `requirements`, at least one authentication method (PIN or passphrase) must be set up. Only authentication methods listed under `features` can be used. In this example, both PIN and passphrase can be used and at least one of them must be used.

If `volumes-auth` is not present in `requirements`, setting a PIN or passphrase (according to what the system supports) is optional.

To add a PIN or passphrase, make a `POST` request to `/v2/systems/{label}` with a request body specifying the execution of API action `install` step `setup-storage-encryption`. For example:

```json
{
  "action": "install",
  "step": "setup-storage-encryption",
  "on-volumes": {
    "pc": {
      "bootloader": "grub"
    }
  },
  "volumes-auth": {
    "mode": "pin",
    "pin": "123456"
  },
  "keyboard-config": {
    "model": "pc105",
    "layout": "us"
  }
}
```

When setting up a PIN or a passphrase during installation, `keyboard-config` must be defined. This guarantees that the keyboard layout used when setting up the PIN or passphrase will be the same used for first boot.

If successful, this will return a `202 Accepted` and a response body including a change ID.

### Check PIN or passphrase quality

TODO

## Generate recovery key

Once the storage encryption has been setup, you can generate a recovery key. This step is optional, but highly recommended. A recovery key is a high-entropy fallback credential, that will be used to recover the data in the disk if all other methods fail.

To generate a recovery key, call the `generate-recovery-key` step of action `install`:

```http
POST /v2/systems/{label}
Content-Type: application/json
```

```json
{
  "action": "install",
  "step": "generate-recovery-key"
}
```

If successful, this will return a `200 OK` with a body including a recovery key, e.g.:

```json
{
  "type": "sync",
  "status-code": 200,
  "status": "OK",
  "result": {
    "recovery-key": "12345-67890-12345-67890-12345-67890-12345-67890"
  }
}
```

```{important}
In order for the recovery key to fulfill its goal, it must be shown to the user, with a clear indication that it is an important key that should be noted down and preserved. In case of disk damages, without the recovery key, all data is lost.
```

## Finish installation

Once storage encryption has been set up, you are ready to wrap-up the pre-installation steps and move on with the actual installation, which will happen after the system reboots. This phase is started by calling the `finish` step of the `install` action, e.g.:

```http
POST /v2/systems/{label}
Content-Type: application/json
```

```json
{
  "action": "install",
  "step": "finish",
  "on-volumes": {
    "pc": {
      "bootloader": "grub"
    }
  }
}
```

If successful, this request will return a `202 Accepted` with a response body including a change ID.

```{note}
While the `finish` step finishes the strictly necessary preparation for the installation, it does not include important optimization aspects. Those are covered by the `preseed` step, which, although optional, is highly recommended, and should be run after `finish`.
```

## Preseed installation

Preseeding the system with the relevant snaps will make the actual installation after reboot much faster. Calling the `preseed` step of action `install` is, therefore, recommended. It should be performed after the `finish` step and before reboot.

To perform this step, a final `POST` request is needed:

```http
POST /v2/systems/{label}
Content-Type: application/json
```

```json
{
  "action": "install",
  "step": "preseed",
  "target-root": "<path/to/mounted/target-root>"
}
```

[Below: copied from SD201]

Usage of this new step requires that the caller create some mount points from the host system into the root filesystem of the installation target. This aligns with the current expectations of the existing preseeding workflow. These mount points are:

```sh
/dev
/proc
/sys
/sys/kernel/security
```

Note that `/sys` and `/sys/kernel/security` must be mounted independently due to some existing checks within snapd's preseeding implementation.

In addition, it is required to make the target system available by bind mounting `/var/lib/snapd/seed` into `/target/var/lib/snapd/seed`
