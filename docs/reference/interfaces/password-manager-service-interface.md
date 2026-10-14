---
myst:
  html_meta:
    description: The password-manager-service interface lets a snap use snapd to access desktop password managers such as Secret Service and KWallet.
---

(interfaces-password-manager-service-interface)=
#  password-manager-service interface

`password-manager-service` provides access to the global password manager services provided by popular desktop environments, such as Secret Service and KWallet, for example. This interface obviously gives privileged access to sensitive information stored in the user's session.


**{ref}`Auto-connect <explanation-interfaces-interface-auto-connection>`**: no</br>
**Transitional**: yes

Requires snapd version _2.27+_.

