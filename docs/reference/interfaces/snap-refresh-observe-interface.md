---
myst:
  html_meta:
    description: The snap-refresh-observe interface lets a snap use snapd to track refreshes and their inhibition as a refresh awareness client.
---

(interfaces-snap-refresh-observe-interface)=
#  snap-refresh-observe interface

The `snap-refresh-observe` interface permits tracking snap refreshes and their inhibition.

It is intended to be used _only_ to mark the existence of a refresh awareness client, such as [snapd-desktop-integration](https://snapcraft.io/install/snapd-desktop-integration/ubuntu) snap.


## Developer details

**{ref}`Auto-connect <explanation-interfaces-interface-auto-connection>`**: no</br>
**{ref}`Super-privileged <reference-operations-interfaces-super-privileged-interfaces>`**: yes</br>

<h3 id='heading--endpoint-access'>Endpoint access permissions</h3>
<ul>
<li>/v2/changes</li>
<li>/v2/changes/{id}</li>
<li>/v2/icons/{name}/icon</li>
<li>/v2/notices</li>
<li>/v2/notices/{id}</li>
<li>/v2/snaps</li>
<li>/v2/snaps/{name}</li>
</ul>

### Code examples

The test code can be found in the snapd repository: https://github.com/canonical/snapd/blob/master/interfaces/builtin/snap_refresh_observe_test.go

The source code for the interface is in the snapd repository: https://github.com/canonical/snapd/blob/master/interfaces/builtin/snap_refresh_observe.go
