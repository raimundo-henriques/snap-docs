---
myst:
  html_meta:
    description: The qualcomm-ipc-router interface lets a snap use snapd to access Qualcomm IPC Router sockets, primarily on Ubuntu Core devices.
---

(interfaces-qualcomm-ipc-router-interface)=
#  qualcomm-ipc-router interface

The `qualcomm-ipc-router` interface allows access to the Qualcomm IPC Router sockets.

This interface is primarily intended to be used with {ref}`Ubuntu Core <ref-glossary_ubuntu-core>`.


## Developer details

**Auto-connect**: no

### Code examples

The test code can be found in the snapd repository: https://github.com/canonical/snapd/blob/master/interfaces/builtin/qualcomm_ipc_router_test.go

The source code for the interface is in the snapd repository: https://github.com/canonical/snapd/blob/master/interfaces/builtin/qualcomm_ipc_router.go
