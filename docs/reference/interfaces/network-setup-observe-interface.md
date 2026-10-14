---
myst:
  html_meta:
    description: The network-setup-observe interface lets a snap use snapd to read network setup configuration files containing system network details.
---

(interfaces-network-setup-observe-interface)=
#  network-setup-observe interface

`network-setup-observe` allows read-only access to network setup configuration files. This is restricted because it gives access to system network configuration which can contain network security details.

**Auto-connect**: no

