---
myst:
  html_meta:
    description: Reference documentation for libvirt, which lets a snap control host libvirtd through snapd using the privileged libvirt socket for QEMU or KVM.
---

(interfaces-libvirt-interface)=
#  libvirt interface

`libvirt` enables access to the *libvirt* control socket, which gives privileged access to control *libvirtd* on the host. This is commonly used to create and manage QEMU/KVM instances on the host.

**Auto-connect**: no

