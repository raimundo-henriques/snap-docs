---
myst:
  html_meta:
    description: The snap-themes-control interface lets a snap use snapd's theme installation API to manage desktop themes and related change requests.
---

(interfaces-snap-themes-control-interface)=
#  snap-themes-control interface

The `snap-themes-control` interface permits the use of snapd's theme installation API.


## Developer details

**{ref}`Auto-connect <explanation-interfaces-interface-auto-connection>`**: no</br>
**{ref}`Super-privileged <reference-operations-interfaces-super-privileged-interfaces>`**: yes</br>

<h3 id='heading--endpoint-access'>Endpoint access permissions</h3>
<ul>
<li>/v2/accessories/changes/{id}</li>
<li>/v2/accessories/themes</li>
</ul>

### Code examples

The test code can be found in the snapd repository: https://github.com/canonical/snapd/blob/master/interfaces/builtin/snap_themes_control_test.go

The source code for the interface is in the snapd repository: https://github.com/canonical/snapd/blob/master/interfaces/builtin/snap_themes_control.go
