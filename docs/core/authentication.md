---
hide:
- toc
---
# Authentication
The core system is using IndieAuth[^1] for authentication.

- restrict third-party apps to a limited subset of resources
- revoke access for a particular third party without changing credentials


## Scopes
The list of available scopes may change.

| Scope | Description |
| ---  | --- |
| openid[^2] | access the users public profile e.g.: username |
| profile[^2] | access the users personal profile information e.g.: firstname, lastname |
| email[^2] | access the users associated email address. |
| phone[^2] | access the users associated phone number. |
| library.read | *Read only* Grant the user to list all photos owned by the user. |
| library.append | *Limited write access* Grant the user to add new photos, create new albums. |
| library.edit | Grant the user to edit photos owned by the user. |
| library.write | Grant the user to add and edit photos, albums, tags. |
| library.share | Grant the user to create new shares (photos/videos/albums). |
| admin.users:read | Grant the user to list users on the system. |
| admin.users:invite | Grant the user to invite new users to the system. |
| admin.users:write | Grant the user to manage users on the system. |


*[IndieAuth]: IndieAuth builds upon the OAuth 2.0 

[^1]: OAuth specification can be found here: [RFC6749](https://tools.ietf.org/html/rfc6749)
[^2]: This is a default scope in OAuth 2.0
