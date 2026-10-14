---
myst:
  html_meta:
    description: Reference documentation for microceph-support, which lets the MicroCeph snap operate its service through snapd with privileged access.
---

(interfaces-microceph-support)=
#  microceph-support interface

The `microceph-support` interface permits the [microceph](https://snapcraft.io/microceph) snap to operate as the  [MicroCeph](https://canonical-microceph.readthedocs-hosted.com/en/reef-stable/) service.

## Developer details

**{ref}`Auto-connect <explanation-interfaces-interface-auto-connection>`**: no</br>
**{ref}`Super-privileged <reference-operations-interfaces-super-privileged-interfaces>`**: yes</br>

### Code examples

The test code can be found in the snapd repository:</br>https://github.com/canonical/snapd/blob/master/interfaces/builtin/microceph_support_test.go

The source code for the interface is in the snapd repository:
</br>https://github.com/canonical/snapd/blob/master/interfaces/builtin/microceph_support.go
