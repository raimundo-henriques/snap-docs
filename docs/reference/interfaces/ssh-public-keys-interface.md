---
myst:
  html_meta:
    description: The ssh-public-keys interface lets a snap use snapd to read a user's non-sensitive SSH configuration and public keys for remote authentication.
---

(interfaces-ssh-public-keys-interface)=
#  ssh-public-keys interface

`ssh-public-keys` allows a user's SSH (Secure Socket Shell) non-sensitive configuration to be read, along with their public keys.

**{ref}`Auto-connect <explanation-interfaces-interface-auto-connection>`**: no</br>

Requires snapd version _2.31+_.

