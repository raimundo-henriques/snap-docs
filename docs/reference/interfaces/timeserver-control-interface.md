---
myst:
  html_meta:
    description: The timeserver-control interface lets a snap use snapd to configure system time synchronisation servers through systemd-timedated.
---

(interfaces-timeserver-control-interface)=
#  timeserver-control interface

`timeserver-control` allows the setting of system time synchronisation servers via *systemd-timedated* and directly (and independently of `config core`).

**Auto-connect**: no

