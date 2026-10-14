---
myst:
  html_meta:
    description: Reference documentation for desktop-launch, which lets a strictly confined snap use snapd to identify and launch desktop apps in other snaps.
---

(interfaces-desktop-launch-interface)=
#  desktop-launch interface

The `desktop-launch` interface allows {ref}`strictly confined <explanation-security-snap-confinement>` snaps to identify and launch desktop applications in (or from) other snaps.


## Developer details

**{ref}`Auto-connect <explanation-interfaces-interface-auto-connection>`**: no</br>
**{ref}`Super-privileged <reference-operations-interfaces-super-privileged-interfaces>`**: yes</br>

<h3 id='heading--endpoint-access'>Endpoint access permissions</h3>
<ul>
<li>/v2/snaps/{name}</li>
<li>/v2/snaps</li>
<li>/v2/icons/{name}/icon</li>
</ul>


Requires snapd version _2.52+_.

<h3 id='heading-code'>Code examples</h3>

The source code for this interface is in the *snapd* repository:
<https://github.com/canonical/snapd/blob/master/interfaces/builtin/desktop_launch.go>
