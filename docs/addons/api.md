# API
The REST API for communication with the [core](/core/) system is build as an addon.
This makes it very easy to customize the system on low level.

### Views
New views can be registered during the setup process

```python
core.http.register_request(APIStatusView)
```

These views need to inherit from `core.webserver.request.Request`
and provide the properties `url` and `name`.

| Property        | Required | Description                          |
| -----------     | :--------: | ---------------------------------- |
| `url`           | :material-check: | path to the resource |
| `name`          | :material-check: | internal name of the resource. |
| `requires_auth` | :material-close: | enables the auth check |

