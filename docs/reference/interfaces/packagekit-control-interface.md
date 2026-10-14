---
myst:
  html_meta:
    description: The packagekit-control interface lets a snap use snapd to control PackageKit and manage native system packages, alongside AppStream metadata.
---

(interfaces-packagekit-control-interface)=
#  packagekit-control interface

`packagekit-control` allows control of the [PackageKit](https://www.freedesktop.org/software/PackageKit/) service, giving privileged access to native package management on the system.

This interface is intended to work in tandem with {ref}`the AppStream interface <interfaces-appstream-metadata-interface>`. Snaps distributed via the public [Snap store](https://snapcraft.io/store) are not typically granted auto-connection for this interface.

**{ref}`Auto-connect <explanation-interfaces-interface-auto-connection>`**: no</br>
**{ref}`Super-privileged <reference-operations-interfaces-super-privileged-interfaces>`**: yes</br>

Requires snapd version _2.41+_.`

