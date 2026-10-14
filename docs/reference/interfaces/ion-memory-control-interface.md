---
myst:
  html_meta:
    description: Reference documentation for ion-memory-control, which lets a snap access the Android ION memory allocator through snapd on Ubuntu Core.
---

(interfaces-ion-memory-control-interface)=
#  ion-memory-control interface

The `ion-memory-control` interface allows access to the Android ION memory allocator, a Linux kernel feature for managing one or more memory pools.

This interface is primarily intended to be used with {ref}`Ubuntu Core <ref-glossary_ubuntu-core>`.


## Developer details

**{ref}`Auto-connect <explanation-interfaces-interface-auto-connection>`**: no</br>
**{ref}`Super-privileged <reference-operations-interfaces-super-privileged-interfaces>`**: yes</br>

The device is expected in the following location:
-  `/dev/ion`

### Code examples

The test code can be found in the snapd repository: https://github.com/canonical/snapd/blob/master/interfaces/builtin/ion_memory_control_test.go

The source code for the interface is in the snapd repository: https://github.com/canonical/snapd/blob/master/interfaces/builtin/ion_memory_control.go
