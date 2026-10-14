---
myst:
  html_meta:
    description: Reference documentation for lxd-support, which lets the upstream LXD snap operate its service through snapd with specialised confinement rules.
---

(interfaces-lxd-support-interface)=
#  lxd-support interface

`lxd-support` enables operating as the LXD service. This interface can currently only be established with the upstream LXD project.

## Developer details

**{ref}`Auto-connect <explanation-interfaces-interface-auto-connection>`**: no</br>
**{ref}`Super-privileged <reference-operations-interfaces-super-privileged-interfaces>`**: yes</br>
**Transitional**: yes

**Attributes**:

 * **enable-unconfined-mode** (plug, optional):  indicates that snapd should make use of the AppArmor `unconfined` profile mode (if this is supported by the system) when generating the associated AppArmor profiles for the snap which plugs this interface.


