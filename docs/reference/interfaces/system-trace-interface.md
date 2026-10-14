---
myst:
  html_meta:
    description: The system-trace interface lets a snap use snapd to monitor and control programs through kernel tracing facilities on trusted systems.
---

(interfaces-system-trace-interface)=
#  system-trace interface

`system-trace` enables the monitoring and control of any running program, via kernel tracing facilities. This interface is restricted because it gives privileged access to all processes on the system and should only be used with trusted apps.

**Auto-connect**: no

