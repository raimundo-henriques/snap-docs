---
myst:
  html_meta:
    description: Reference documentation for hardware-random-control, which lets a snap read and write the hardware random generator through snapd at /dev/hwrng.
---

(interfaces-hardware-random-control-interface)=
#  hardware-random-control interface

`hardware-random-control` enables control over the hardware random number generator by allowing read/write access to `/dev/hwrng`.

**Auto-connect**: no

Requires snapd version _2.25+_.

