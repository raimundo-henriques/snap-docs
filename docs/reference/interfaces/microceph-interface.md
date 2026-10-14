---
myst:
  html_meta:
    description: Reference documentation for microceph, which lets a snap access the MicroCeph socket through snapd for the MicroCeph snap's internal use.
---

(interfaces-microceph)=
# microceph interface

The `microceph` interface permits access to  the [MicroCeph](https://canonical-microceph.readthedocs-hosted.com/en/reef-stable/) socket, which is used internally by the [microceph](https://snapcraft.io/microceph) snap.

## Developer details

**{ref}`Auto-connect <explanation-interfaces-interface-auto-connection>`**: no</br>
**{ref}`Super-privileged <reference-operations-interfaces-super-privileged-interfaces>`**: yes</br>

### Code examples

The test code can be found in the snapd repository:</br>https://github.com/canonical/snapd/blob/master/interfaces/builtin/microceph_test.go

The source code for the interface is in the snapd repository:
</br>https://github.com/canonical/snapd/blob/master/interfaces/builtin/microceph.go
