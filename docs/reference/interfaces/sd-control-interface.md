---
myst:
  html_meta:
    description: The sd-control interface lets a snap use snapd to manage SD cards on compatible devices through the DualSD driver and its /dev/DualSD node.
---

(interfaces-sd-control-interface)=
#  sd-control interface

The `sd-control` interface allows for the management and control of SD cards on certain devices using the DualSD driver.


## Developer details

**{ref}`Auto-connect <explanation-interfaces-interface-auto-connection>`**: no</br>
**{ref}`Super-privileged <reference-operations-interfaces-super-privileged-interfaces>`**: yes</br>

The main DualSD device node (`/dev/DualSD`) is used to control certain aspects of SD cards on the system.

Requires snapd version _2.51.3+_.

<h3 id='heading-code'>Code examples</h3>

The source code for this interface is in the *snapd* repository:
<https://github.com/canonical/snapd/blob/master/interfaces/builtin/sd_control.go>
