---
hide:
- toc
---
# Configuration File
To run an instance of the core system will require a configuration file.
It will define the place to write and read data from or wich addons should be loaded on startup.

Some addons still needed to be configured by the users itself.

### Minimal configuration
```json
{
  "internal_url": "192.168.0.1",
  "external_url": "external.url.com",
  "data_dir": "data",
  "addons": []
}
```

### Configuration with addons
```json
{
  "internal_url": "192.168.0.1",
  "external_url": "external.url.com",
  "data_dir": "data",
  "addons": [
    {
      "name": "api",
      "config": {
        "cors": false
      }
    },
    {
      "name": "sqlite",
      "config": {
        "database_file": "test.sqlite"
      }
    }
  ]
}
```