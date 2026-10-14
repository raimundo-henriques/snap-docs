---
myst:
  html_meta:
    description: The power-control interface lets a snap use snapd to read system power settings and configure device wake-up events and runtime power management.
---

(interfaces-power-control-interface)=
#  power-control interface

The `power-control` interface allows the reading and setting of system power settings.

This interface is primarily intended to be used with {ref}`Ubuntu Core <ref-glossary_ubuntu-core>`.


## Developer details

**Auto-connect**: no

This interface enables:
- reading of all power settings:
`/sys/devices/**/power/`
- setting wake-up events for supported devices:
`/sys/devices/**/power/wakeup`
- configuring power management for supported devices at runtime:
 `/sys/devices/**/power/control`


### Code examples

The test code can be found in the snapd repository: https://github.com/canonical/snapd/blob/master/interfaces/builtin/power_control_test.go

The source code for the interface is in the snapd repository: https://github.com/canonical/snapd/blob/master/interfaces/builtin/power_control.go
