# Authorization flow

## [Authorization Request](https://tools.ietf.org/html/rfc6749#section-4.1.1)
> The client (Frontend) initiates the Authorization Code Grant flow by directing the user to the authorization endpoint.

``` http
GET /oauth/authorize HTTP/1.1
Host: core.photos.network
Accept-Language: en-US,en;q=0.8

client_id=CLIENT_ID&redirect_uri=http://frontend.photos.network&scope=<SCOPES>&response_type=code&response_mode=query&state=<NONCE>
```

> The authorization server will show a login dialog with a list of requested scopes.

``` html
  =======
  username:
  password:
  =======
```

#### Login Request
> The resource owner (*User*) grants the client's (*Frontend*) access request by authenticating himself/herself with credentials (username / password) to the authorization server

``` http
POST /oauth/authorize HTTP/1.1
Host: core.photos.network

uname=test&password=secret
```

#### [Authorization Response](https://tools.ietf.org/html/rfc6749#section-4.1.2)
> The authorization server redirects the resource owner (*User*) to the client (*Frontend*) using the redirection URI provided in the Authorization Request

access denied
```
<REDIRECT_URI>
  error=access_denied&
  error_description=The user did not consent.
```

access granted
```
<REDIRECT_URI>
  code=zuzuRerfdg543ljf023&
  state=abcdef
```

---


## [Access Token Request](https://tools.ietf.org/html/rfc6749#section-4.1.3)
> The client (*Frontend*) requests an access token from the authorization server's token endpoint by including the authorization code

``` http
POST /oauth/token HTTP/1.1
Content-Type: application/x-www-form-urlencoded

client_id=<CLIENT_ID>client_secret=<CLIENT_SECRET>&grant_type=authorization_code&code=zuzuRerfdg543ljf023&
```

### [Access Token Response](https://tools.ietf.org/html/rfc6749#section-4.1.4)
> The authorization server responds an access token and a refresh token.

``` json
{
  "access_token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJleHAiOjE2MTMyMzM4Mjh9.8U4oXtAHEkYgZldFMduANu-ryhTN5RX69XslPzU7pnQ",
  "token_type": "Bearer",
  "expires_in": 3600,
  "refresh_token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJleHAiOjE2MTMyMzA4ODN9.4kFQD33F7-xQPUWSM9IxsDYqv30zAEa7WS7jpk8NtFU"
}
```

## [Refreshing an Access Token](https://tools.ietf.org/html/rfc6749#section-6)
> The client (*Frontend*) makes a refresh request to the authorization server's token endpoint

**Hint:** grant_type have to be `refresh_token`

``` http
POST /oauth/token HTTP/1.1
Content-Type: application/x-www-form-urlencoded

client_id=<CLIENT_ID>&client_secret=<CLIENT_SECRET>&grant_type=refresh_token&code=zuzuRerfdg543ljf023&
refresh_token=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJleHAiOjE2MTMyMzA4ODN9.4kFQD33F7-xQPUWSM9IxsDYqv30zAEa7WS7jpk8NtFU
```

## Access protected endpoints
``` http
GET /api/photo HTTP/1.1
Authorization: Bearer <ACCESS_TOKEN>
```
