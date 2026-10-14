---
myst:
  html_meta:
    description: The opengles-driver-libs interface lets a snap use snapd to expose OpenGL ES driver libraries to the system for graphics support.
---

(ref-opengles-driver-libs-interface_opengles-driver-libs-interface)=
#  opengles-driver-libs interface

The `opengles-driver-libs` interface allows exposing OpenGLES driver libraries to the system.

For further details on interfaces, see {ref}`How to connect interfaces <explanation-interfaces-all-about-interfaces>`.

## Developer details

**{ref}`Auto-connect <explanation-interfaces-interface-auto-connection>`**: no</br>
**{ref}`Super-privileged <reference-operations-interfaces-super-privileged-interfaces>`**: yes</br>

### Code examples

The test code can be found in the snapd repository:</br>https://github.com/canonical/snapd/blob/master/interfaces/builtin/opengles_driver_libs_test.go

The source code for the interface is in the snapd repository:
</br>https://github.com/canonical/snapd/blob/master/interfaces/builtin/opengles_driver_libs.go
