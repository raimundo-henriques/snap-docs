---
myst:
  html_meta:
    description: Reference documentation for dsp, which lets a snap control digital signal processors through snapd on supported devices with gadget hardware access.
---

(interfaces-dsp-interface)=
#  dsp interface

The `dsp` interface allows for the control of digital signal processors (DSPs) on specific devices and systems (such as specific _Ambarella_ devices)



## Developer details

**Auto-connect**: no

This interface allows privileged access to hardware and kernel drivers related to the digital signal processor and thus is only allowed on specific devices providing the slot via a gadget and is also not auto-connected.

Requires snapd version _2.51+_.

<h3 id='heading-code'>Code examples</h3>

The source code for this interface is in the *snapd* repository:
<https://github.com/canonical/snapd/blob/master/interfaces/builtin/dsp.go>
