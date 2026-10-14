---
myst:
  html_meta:
    description: Reference documentation for lxd, which lets a snap access the LXD API through snapd using the socket provided by the lxd snap.
---

(interfaces-lxd-interface)=
#  lxd interface

`lxd` allows access to the LXD API via the socket provided by the *lxd* snap. *LXD_DIR* must be set to `/var/snap/lxd/common/lxd`. This interface requires manual connection.

**{ref}`Auto-connect <explanation-interfaces-interface-auto-connection>`**: no</br>
**{ref}`Super-privileged <reference-operations-interfaces-super-privileged-interfaces>`**: yes</br>

