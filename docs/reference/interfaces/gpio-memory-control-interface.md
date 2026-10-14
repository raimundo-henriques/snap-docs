---
myst:
  html_meta:
    description: Reference documentation for gpio-memory-control, which lets a snap write all GPIO memory through snapd using the privileged /dev/gpiomem device.
---

(interfaces-gpio-memory-control-interface)=
#  gpio-memory-control interface

`gpio-memory-control` allows write access to all GPIO memory, via `/dev/gpiomem`. This interface is restricted because it provides privileged access to all GPIO devices.

**Auto-connect**: no

Requires snapd version _2.24+_.

