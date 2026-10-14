---
myst:
  html_meta:
    description: The snap-fde-control interface lets a snap use snapd to access the full-disk-encryption subset of its system-volumes API.
---

(ref-snap-fde-control-interface_snap-fde-control-interface)=
#  snap-fde-control interface

The `snap-fde-control` allows access to the FDE subset of snapd's system-volumes API.

For further details on interfaces, see {ref}`How to connect interfaces <explanation-interfaces-all-about-interfaces>`.

## Developer details

**{ref}`Auto-connect <explanation-interfaces-interface-auto-connection>`**: no</br>
**{ref}`Super-privileged <reference-operations-interfaces-super-privileged-interfaces>`**: yes</br>

### Code examples

The test code can be found in the snapd repository:</br>https://github.com/canonical/snapd/blob/master/interfaces/builtin/snap_fde_control_test.go

The source code for the interface is in the snapd repository:
</br>https://github.com/canonical/snapd/blob/master/interfaces/builtin/snap_fde_control.go
