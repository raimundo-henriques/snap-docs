---
myst:
  html_meta:
    description: The optical-drive interface lets a snap use snapd to read optical media and optionally write CD, DVD, or Blu-ray discs on classic systems.
---

(interfaces-optical-drive-interface)=
#  optical-drive interface

`optical-drive` allows read/write access to optical drives, suitable for CD/DVD/Blu-Ray playback and burning. This interface is not currently available to use on Ubuntu Core, only classic systems can use this interface.

**Auto-Connect**: by default, yes; when `write: true`, no
**Attributes**:
 * `write`: `true|false`, defaults to `false`. 

`write` available in snap versions _2.33+_.

