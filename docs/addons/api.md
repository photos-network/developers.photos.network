# API
The REST API for communication with the [core](/core/) system is build as an addon too.
This makes it easy to customize the system by adding additional resources.

### Views
Views can be registered during the setup process

```python
async def async_setup(core: ApplicationCore, config: dict) -> bool:
    core.http.register_request(APIStatusView)
```

These views need to inherit from `core.webserver.request.RequestView`
and provide the properties `url` and `name`.
With an additional `requires_auth` property can be defined if the resource can be reached without authentication.

| Property        | Required | Description                          |
| -----------     | :--------: | ---------------------------------- |
| `url`           | :material-check: | path to the resource |
| `name`          | :material-check: | internal name of the resource. |
| `requires_auth` | :material-close: | enables the auth check |

### Methods
Each view can offer multiple methods to the given `url` property.

an async `get` method will handle `GET` requests
```python
async def get(self, core, request) -> web.Response:
    return self.json_message("respond with a json message.")
```

while an async `post` method will handle `POST` requests and so on.
```python
async def post(self, request, entity_id) -> web.Response:
    return self.json_message("entity has been created.")
```

### Response
Each view can define its own response.

Return a simple json
```python
    return self.json_message("simple json string")
```

Return a data as json
```python
    return self.json({"foo":"bar"})
```
