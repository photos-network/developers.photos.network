---
hide:
- toc
---
# Structure
Since the core system is responsible for multiple tasks,
it is mandatory to keep the file structure clean and well arranged.

The project itself has a default application structure with some internal crates.
```shell
core/
├── src/
    ├── main.rs
    └── lib.rs
├── tests/
├── crates/
    ├── accounts/
    ├── activity_pub/
    ├── common/
    ├── database/
    ├── media/
    ├── oauth_authentication/
    ├── oauth_authorization_server/
    └── plugin_interface/
└── Cargo.toml
```
   
| File    | Description |
| ------  | --- |
| main.rs | is the entry point of the application and will only load `lib.rs`. |
| lib.rs  | will read the configuration, create necessary folders, create an application instance and loads **plugins**. |
| tests   | contains integration test for the whole application. |
| creates/account | handles all account related endpoints for user management. |
| creates/activity_pub | Adds support for fediverse. |
| creates/common | shared code like re-usable structs. |
| creates/database | abstracts the database persistency for the application. |
| creates/media | media related endpoints |
| creates/oauth_authentication | OAuth/OpenID endpoints to support 3rd party login. |
| creates/oauth_authorization_server | OAuth server to provide a standalone and offline capable login. |
| creates/plugin_interface | Interfaces used by the plugin system. |
