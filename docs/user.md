# USER API SPEC

## register user API

endpoint: POST /api/users

request body:

```json
{
  "username": "masyhar@example.com",
  "password": "password123",
  "name": "masyhar"
}
```

response success:

```json
{
  "data": {
    "username": "masyhar@example.com",
    "name": "masyhar"
  }
}
```

response error:

```json
{
  "error": "username cannot be blank!, ..."
}
```

## login user api

endpoint: POST /api/users/login

request body:

```json
{
  "username": "masyhar@example.com",
  "password": "password123",
}
```

response success:

```json
{
  "data": {
    "username": "masyhar@example.com",
    "name": "masyhar",
    "token": "token-uuid"
  }
}
```

response error:

```json
{
  "error": "username or password wrong!"
}
```

## get current user API

endpoint: GET /api/users/current

request header:

- X-API-TOKEN: token

response success:

```json
{
  "data": {
    "username": "masyhar@example.com",
    "name": "masyhar",
  }
}
```

response error:

```json
{
  "error": "unauthorized!"
}
```

## update current user API

endpoint: PATCH /api/users/current

request header:

- X-API-TOKEN: token

request body:

```json
{
  "password": "password123update", // optional
  "name": "masyhar update" // optional
}
```

response success:

```json
{
  "data": {
    "username": "masyhar@example.com",
    "name": "masyhar update",
  }
}
```

response error:

```json
{
  "error": "unauthorized!"
}
```

## logout user API

endpoint: DELETE /api/users/current

request header:

- X-API-TOKEN: token

response success:

```json
{
  "data": "OK"
}
```

response error:

```json
{
  "error": "unauthorized!"
}
```
