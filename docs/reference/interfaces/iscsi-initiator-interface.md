---
myst:
  html_meta:
    description: Reference documentation for iscsi-initiator, which lets a snap discover, connect to, and manage iSCSI targets through snapd access.
---

(ref-iscsi-initiator-interface_iscsi-initiator-interface)=
#  iscsi-initiator interface

The `iscsi-initiator` interface allows snaps to act as iSCSI initiators, enabling them to discover, connect to, and manage iSCSI targets for block storage access.

The interface loads kernel modules required for iSCSI operations including iscsi_tcp for transport and target_core_mod for LIO functionality.

See {ref}`Interface management <how-to-guides-work-with-snaps-connect-interfaces>` and {ref}`Supported interfaces <ref-index_interfaces>` for further details on how interfaces are used.

## Developer details

**{ref}`Auto-connect <explanation-interfaces-interface-auto-connection>`**: no </br>
**{ref}`Super-privileged <reference-operations-interfaces-super-privileged-interfaces>`**: yes</br>

### Code examples

The test code can be found in the snapd repository:</br>https://github.com/canonical/snapd/blob/master/interfaces/builtin/iscsi_initiator_test.go

The source code for the interface is in the snapd repository:
</br>https://github.com/canonical/snapd/blob/master/interfaces/builtin/iscsi_initiator.go
