---
myst:
  html_meta:
    description: The raw-input interface lets a snap use snapd to access raw input devices directly, for applications that need low-level device events.
---

(interfaces-raw-input-interface)=
#  raw-input interface

The `raw-input` interface allows access to raw input devices.

For further details on interfaces, see {ref}`How to connect interfaces <explanation-interfaces-all-about-interfaces>`.

## Developer details

**Auto-connect**: no

Requires snapd version _2.51+_.

### Code examples

The source code for this interface is in the *snapd* repository:
<https://github.com/canonical/snapd/blob/master/interfaces/builtin/raw_input.go>
