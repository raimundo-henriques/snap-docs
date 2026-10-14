---
myst:
  html_meta:
    description: The ubuntu-pro-control interface lets a snap use snapd to control the Ubuntu Pro desktop daemon and its service entitlements over D-Bus.
---

(interfaces-ubuntu-pro-control-interface)=
#  ubuntu-pro-control interface

`ubuntu-pro-control` allows control of the Ubuntu Pro desktop daemon over D-Bus.

This interface lets a connected snap attach or detach the system from Ubuntu Pro, inspect available Pro services and their entitlement/status, and enable or disable individual services.

**{ref}`Auto-connect <explanation-interfaces-interface-auto-connection>`**: no</br>
**{ref}`Super-privileged <reference-operations-interfaces-super-privileged-interfaces>`**: yes</br>
