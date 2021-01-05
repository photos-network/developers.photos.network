# Addons

One of the fundamental concepts of [photos.network](https://photos.network) is the separation of concerns combined
with the flexibility of customization.

Except the core system, all features are bundled in addons. 

## Create an addon
Each addon is encapsulated in a separate directory wich have to contain at least two files:

- `addon.json` with detailed informations and requirements
- `__init__.py` with an async setup function


#### addon.json
In `addon.json` developers need to specify a unique domain for their addon, this domain will be used in the [configuration](/core/configuration/) 
file. Python requirements can be specified as list, either by name optionally with an exact version specifier.

| identifier | required | description |
| ---------- | -------- | ----------- |
| domain | yes | unique identifier of the addon |
| name | yes | short description what the addon can be used for. |
| requirements | yes | python requirements to install before the addon setup |
| type | no | define the type of the addon: image, storage |
| core | no | min. version of the core system. |

!!! Hint
    The **core** version is not used yet. It will keep track of the required core version for backward compatibility.

#### example addon
```json
{
  "domain": "unique_image_addon",
  "name": "This is an image processing addon",
  "requirements": [
    "exif==1.0.4",
    "torch"
  ],
  "type": "image",
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
