---
hide:
- toc
---
# Configuration File

A default configuration file will be created in **config/core.json``` on the first startup of the core instance.
Additional infos especially to configure plugins, require a restart.

Some addons still needed to be configured by the users itself.

### Minimal configuration
```json
{
  "internal_url": "192.168.0.1",
  "external_url": "external.url.com",
  "clients": [],
  "plugins": []
}
```

### Configuration with plugins
```json
{
  "internal_url": "192.168.0.1",
  "external_url": "demo.photos.network",
  "database": {
    "driver": "PostgreSQL",
    "url": "protocol://username:password@host/database"
  },
  "auth_provider": [
    {
      "name": "Google",
      "url": "https://accounts.google.com",
      "client_id": "123456789012-11iI1Iabcdef1abcde12abcd2e8bko3h.apps.googleusercontent.com",
      "client_secret": "A1BCDE-ABCDEFG12_ABCDEF123-123456ABC",
      "redirect_url": "http://demo.photos.network/callback"
    }
  ],
  "clients": [
    {
      "name": "Web Frontend",
      "client_id": "",
      "client_secret": "",
      "redirect_uris": [
          "https://demo.photos.network/callback",
          "http://127.0.0.1:7777/callback"
      ]
    },
    {
      "name": "Android",
      "client_id": "XXAABBCCDDZZeeffggiijj",
      "client_secret": "abcdefg123456ijklmno987654",
      "redirect_uris": [
          "photosapp://authenticate"
      ]
    }
  ],
  "plugins": [
    {
      "name": "metadata"
    }
	]
}
```
