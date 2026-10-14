---
myst:
  html_meta:
    description: The network-control interface lets a snap use snapd to configure network settings and namespaces with ip netns, granting broad privileged network access.
---

(interfaces-network-control-interface)=
#  network-control interface

`network-control` enables the configuration of networking and network namespaces via `ip netns`, providing a wide, privileged access to networking.

**Auto-connect**: no

Requires snapd version _2.20+_.

