# Plugins

One of the fundamental concepts of [photos.network](https://photos.network) is the separation of concerns combined
with the flexibility of customization.

Plugins are binary blobs loaded at runtime to decouple its development from the core system.
It uses FFI[^1] for dynamic loading provided by the [:fontawesome-brands-github: abi_stable](https://github.com/rodrimati1992/abi_stable_crates) crate.

Except the core system, all features are bundled in plugins. 




## Create a plugin
Each plugin needs to depend on the [plugin_interface](https://github.com/photos-network/plugin_interface) of Photos.network and needs to implement the [Plugin trait](https://github.com/photos-network/plugin_interface/blob/development/src/lib.rs#L32):

``` rust
pub trait Plugin {
    fn on_core_init(&self) -> RResult<RString, Error>;
    fn on_core_started(&self) -> RResult<RString, Error>;
}
```


## Use the plugin

The plugin binary needs to be copied into the `core/plugins` directory and added to the configuration file.

```shell
core/
└── plugins/
    ├── libplugin_metadata.d
    └── libplugin_metadata.dylib
```

Plugin block in the [configuration](/core/configuration) file
```json
{
  "plugins": [
    {
      "name": "metadata",
    }
  ]
}
```

[^1]: Foreign Function Interface
