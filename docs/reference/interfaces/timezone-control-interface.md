---
myst:
  html_meta:
    description: The timezone-control interface lets a snap use snapd to configure the system timezone directly through systemd-timedated rather than core settings.
---

(interfaces-timezone-control-interface)=
#  timezone-control interface

`timezone-control` allows the setting of the system timezone via *systemd-timedated* and directly (and independently of `config core`).

**Auto-connect**: no

