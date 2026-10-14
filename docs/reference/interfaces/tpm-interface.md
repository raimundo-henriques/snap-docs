---
myst:
  html_meta:
    description: The tpm interface lets a snap use snapd to access Trusted Platform Module devices and the in-kernel resource manager on recent kernels.
---

(interfaces-tpm-interface)=
#  tpm interface

`tpm` allows access to the Trusted Platform Module (tpm) device, `/dev/tpm0`, and to the in-kernel resource manager, `/dev/tpmrm0`, on recent kernels (at least _v4.12_)

**{ref}`Auto-connect <explanation-interfaces-interface-auto-connection>`**: no</br>

