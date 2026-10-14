---
myst:
  html_meta:
    description: The network-setup-control interface lets a snap use snapd to read and write Netplan configuration files containing system network details.
---

(interfaces-network-setup-control-interface)=
#  network-setup-control interface

`network-setup-control` allows read/write access to Netplan configuration files. This is restricted because it gives access to system network configuration which can contain network security details.

**Auto-connect**: no

Requires snapd version _2.22+_.

