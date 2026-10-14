---
myst:
  html_meta:
    description: Reference documentation for mount-observe, which lets a trusted snap read mount-table and quota information through restricted snapd access.
---

(interfaces-mount-observe-interface)=
#  mount-observe interface

`mount-observe` enables a snap to read mount table and quota information. This interface is restricted because it gives privileged read access to mount arguments and should only be used with trusted apps.

**Auto-connect**: no

