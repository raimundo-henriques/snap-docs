---
myst:
  html_meta:
    description: The pkcs11 interface lets a snap use snapd to use the PKCS#11 Cryptographic Token Interface Standard with exposed hardware or software tokens.
---

(interfaces-pkcs11)=
#  pkcs11 interface

The `pkcs11` interface enables the [PKCS#11 Cryptographic Token Interface Standard](https://thalesdocs.com/gphsm/ptk/5.9/docs/Content/PTK-C_Program/intro_PKCS11.htm) to be used with access to exposed tokens.


## Developer details

**{ref}`Auto-connect <explanation-interfaces-interface-auto-connection>`**: no</br>
**{ref}`Super-privileged <reference-operations-interfaces-super-privileged-interfaces>`**: yes</br>

### Code examples

The test code can be found in the snapd repository:</br>https://github.com/canonical/snapd/blob/master/interfaces/builtin/pkcs11_test.go

The source code for the interface is in the snapd repository:
</br>https://github.com/canonical/snapd/blob/master/interfaces/builtin/pkcs11.go
