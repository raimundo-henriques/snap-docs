---
myst:
  html_meta:
    description: Reference documentation for io-ports-control, which lets a snap use snapd to access and modify all I/O port permissions through /dev/port.
---

(interfaces-io-ports-control-interface)=
#  io-ports-control interface

`io-ports-control` allows access to all I/O ports, including the ability to write to `/dev/port` to change the I/O port permissions, the privilege level of the calling process, and disabling interrupts.

**Auto-connect**: no

Requires snapd version _2.21+_.

