---
myst:
  html_meta:
    description: Reference documentation for the accel interface, which lets a snap access Linux compute accelerator device nodes managed by snapd confinement.
---

(interfaces-accel)=
#  accel interface

**This interface is under development and is not currently available for general use.**

The `accel` interface allows access to device nodes in `/dev/accel` , which are managed by the [Linux compute accelerators subsystem](https://docs.kernel.org/accel/introduction.html).

## Developer details

**{ref}`Auto-connect <explanation-interfaces-interface-auto-connection>`**: yes</br>

### Code examples

The test code can be found in the snapd repository: [https://github.com/canonical/snapd/blob/master/interfaces/builtin/accel_test.go](https://github.com/canonical/snapd/blob/master/interfaces/builtin/accel_test.go)

The source code for the interface is in the snapd repository:[ https://github.com/canonical/snapd/blob/master/interfaces/builtin/accel.go](https://github.com/canonical/snapd/blob/master/interfaces/builtin/accel.go)
