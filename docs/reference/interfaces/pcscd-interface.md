---
myst:
  html_meta:
    description: The pcscd interface lets a snap use snapd to communicate with the PC/SC smart card daemon and access smart cards or secure tokens.
---

(interfaces-pcscd-interface)=
#  pcscd interface

The `pcscd` interface  permits communication with [PCSD](https://manpages.ubuntu.com/manpages/focal/en/man8/pcscd.8.html), the PC/SC smart card daemon typically used to access smart cards and secure tokens via the SCard API.


## Developer details

**{ref}`Auto-connect <explanation-interfaces-interface-auto-connection>`**: no</br>

### Code examples

The test code can be found in the snapd repository: https://github.com/canonical/snapd/blob/master/interfaces/builtin/pcscd_test.go

The source code for the interface is in the snapd repository: https://github.com/canonical/snapd/blob/master/interfaces/builtin/pcscd.go
