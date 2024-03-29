---
hide:
- toc
---
# Authentication
The core system is using OAuth 2.0[^1] for authentication and acting as authorization server.

- restrict third-party apps to a limited subset of resources.
- revoke access for a particular third-party without changing credentials


## Scopes
The list of available scopes may change.

| Scope | Description |
| ---  | --- |
| openid[^2] | access the users public profile e.g.: username |
| profile[^2] | access the users personal profile information e.g.: firstname, lastname |
| email[^2] | access the users associated email address. |
| phone[^2] | access the users associated phone number. |
| library:read | *Read only* access the list of all photos owned by the user. |
| library:append | *Limited write access* access to add new photos, create new albums. |
| library:edit | access to edit photos owned by the user. |
| library:write | access to add and edit photos, albums, tags. |
| library:share | access to create new shares (photos/videos/albums). |
| admin.users:read | access to list users on the system. |
| admin.users:invite | access to invite new users to the system. |
| admin.users:write | access to manage users on the system. |



[^1]: OAuth specification can be found here: [RFC6749](https://tools.ietf.org/html/rfc6749)
[^2]: This is a default scope in OAuth 2.0
