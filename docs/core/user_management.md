# User Management
This user management does only provide some basic endpoints.

## Create / Update User
``` http
PUT /users/{userId} HTTP/1.1
Host: core.photos.network
Authorization: Bearer <ACCESS_TOKEN>

{
  "properties.email": "max.mustermann@photos.network",
  "properties.firstName": "Max",
  "properties.lastName": "Mustermann",
  "properties.password": "myS3curePa$$wor!"
}
```

| Properties              | Description                          |
| ----------------------- | ------------------------------------ |
| `properties.email`      | Must not be empty and must be unique within the service instance. |
| `properties.firstName`  | First name. |
| `properties.lastName`   | Last name. |
| `properties.password`   | User Password. If no value is provided, a default password is generated. |





#### Response
``` http
200 OK - User updated
201 CREATED - User created
```


## Get User
``` http
GET /users/{userId} HTTP/1.1
Host: core.photos.network
Authorization: Bearer <ACCESS_TOKEN>
```

#### Response
``` http
{
  "properties.email": "max.mustermann@photos.network",
  "properties.firstName": "Max",
  "properties.lastName": "Mustermann",
  "properties.registrationDate": "yyyy-MM-ddTHH:mm:ssZ",
  "properties.lastLogin": "yyyy-MM-ddTHH:mm:ssZ"
}
```



## Delete User
``` http
DELETE /users/{userId} HTTP/1.1
Host: core.photos.network
Authorization: Bearer <ACCESS_TOKEN>
```

#### Response
``` http
200 OK - The user were successfully deleted.
```



## Confirmation
Each password change needs to be confirmed by the user.

!!! hint "Not implemented yet?"
    This endpoint neither the requirement is implemented yet.

``` http
GET /users/{userId}/confirmations/{confirmationCode} HTTP/1.1
Host: core.photos.network
```
