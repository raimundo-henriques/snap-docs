---
myst:
  html_meta:
    description: The opengl-driver-libs interface lets a snap use snapd to expose OpenGL driver libraries to the system for graphics hardware support.
---

(ref-opengl-driver-libs-interface_opengl-driver-libs-interface)=
#  opengl-driver-libs interface

The `opengl-driver-libs` interface allows exposing OpenGL driver libraries to the system

For further details on interfaces, see {ref}`How to connect interfaces <explanation-interfaces-all-about-interfaces>`.

## Developer details

**{ref}`Auto-connect <explanation-interfaces-interface-auto-connection>`**: no</br>
**{ref}`Super-privileged <reference-operations-interfaces-super-privileged-interfaces>`**: yes</br>

### Code examples

The test code can be found in the snapd repository:</br>https://github.com/canonical/snapd/blob/master/interfaces/builtin/opengl_driver_libs_test.go

The source code for the interface is in the snapd repository:
</br>https://github.com/canonical/snapd/blob/master/interfaces/builtin/opengl_driver_libs.go
