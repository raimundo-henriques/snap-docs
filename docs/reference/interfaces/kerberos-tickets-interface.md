---
myst:
  html_meta:
    description: Reference documentation for kerberos-tickets, which lets a snap access Kerberos tickets in /tmp through snapd while the feature develops.
---

(ref-kerberos-tickets-interface_kerberos-tickets-interface)=
#  kerberos-tickets interface

The `kerberos-tickets` interface enables access to [Kerberos tickets](https://web.mit.edu/kerberos/krb5-latest/doc/user/tkt_mgmt.html) in `/tmp`

**This interface is under development and is not currently available for general use** .

## Developer details

**{ref}`Auto-connect <explanation-interfaces-interface-auto-connection>`**: no</br>

### Code examples

The test code can be found in the snapd repository: [https://github.com/canonical/snapd/blob/master/interfaces/builtin/kerberos_tickets_test.go](https://github.com/canonical/snapd/blob/master/interfaces/builtin/kerberos_tickets_test.go)

The source code for the interface is in the snapd repository:[ https://github.com/canonical/snapd/blob/master/interfaces/builtin/kerberos_tickets.go](https://github.com/canonical/snapd/blob/master/interfaces/builtin/kerberos_tickets.go)
