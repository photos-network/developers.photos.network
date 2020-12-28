# Addons

One of the fundamental concepts of [photos.network](https://photos.network) is the separation of concerns combined
with the flexibility of customization.

Except the core system, all features are bundled in addons. 

## Create an addon
Each addon is encapsulated in a separate directory wich have to contain at least two files:

- `addon.json` with detailed informations and requirements
- `__init__.py` with an async setup function


#### addon.json
In th `addon.json` developers need to specify a domain for their addon, this domain will be used in the [configuration]() 
file. python requirements can be specified as list either by name or with exact version info.

!!! Hint
    The **core** version is not used yet. It will keep track of the required core version for backward compatibility.

```json
{
  "domain": "unique_addon",
  "name": "This is my fancy addon",
  "requirements": [
    "exif==1.0.4",
    "torch"
  ],
  "core": "0.1.0"
}
```

#### __init__.py
In the `__init__.py` at least an async setup function need to be provided. 
Additional files and packages can be loaded here as well.

The return of the `async_setup` indicates if the setup process was successful.
``` python
async def async_setup(core: ApplicationCore, config: dict) -> bool:
    return True
```
