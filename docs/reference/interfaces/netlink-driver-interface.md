---
myst:
  html_meta:
    description: The netlink-driver interface lets a snap use snapd to expose a kernel module to user space through Netlink for kernel-to-process data transfer.
---

(interfaces-netlink-driver-interface)=
#  netlink-driver interface

The `netlink-driver` interface allows a kernel module to expose itself to user-space via the Netlink protocol, typically to transfer information between the kernel and user-space processes.

See also {ref}`netlink-audit <interfaces-netlink-audit-interface>` and {ref}`netlink-connector <interfaces-netlink-connector-interface>`.


## Developer details

**Auto-connect**: no

Further confinement for particular families/protocols is implemented via Seccomp filtering network Netlink.

Requires snapd version _2.51.1+_.

<h3 id='heading-code'>Code examples</h3>

The source code for this interface is in the *snapd* repository:
<https://github.com/canonical/snapd/blob/master/interfaces/builtin/netlink_driver.go>
