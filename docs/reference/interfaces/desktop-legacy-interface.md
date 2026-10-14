---
myst:
  html_meta:
    description: Reference documentation for desktop-legacy, which lets a graphical snap use snapd access to legacy desktop methods and input frameworks.
---

(interfaces-desktop-legacy-interface)=
#  desktop-legacy interface

`desktop-legacy` allows privileged access to desktop legacy methods, including but not limited to support for input method frameworks(ibus/fcitx).

**Auto-connect**: yes
**Transitional**: yes

Requires snapd version _2.28+_.

See The desktop interfaces for further details.

**Condition to Connect**:
* If your snap has a graphical interface, you *should* connect to this interface.
* If your snap is expected to receive text input from CJKV(Chinese, Japanese, Korean, Vietnamese etc.) users, you **must** connect to this interface, *failing to do so will cause frustration to these users*.

