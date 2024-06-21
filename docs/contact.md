# CONTACT API SPEC

## create contact API

endpoint: POST /api/contacts

request header :

- X-API-TOKEN : token

request body:

```json
{
  "first_name": "masyhar",
  "last_name": "muharam",
  "email": "masyhar@example.com",
  "phone": "08012345678"
}
```

response success:

```json
{
  "data": {
    "id": 1,
    "first_name": "masyhar",
    "last_name": "muharam",
    "email": "masyhar@example.com",
    "phone": "08012345678"
  }
}
```

response error:

```json
{
  "error": "first_name cannot be blank!, ..."
}
```

## get contact API

endpoint: GET /api/contacts/:id

request header :

- X-API-TOKEN : token

response success:

```json
{
  "data": {
    "id": 1,
    "first_name": "masyhar",
    "last_name": "muharam",
    "email": "masyhar@example.com",
    "phone": "08012345678"
  }
}
```

response error:

```json
{
  "error": "contact is not found, ..."
}
```

## update contact API

endpoint: PUT /api/contacts/:id

request header :

- X-API-TOKEN : token

request body :

```json
{
  "first_name": "masyhar update",
  "last_name": "muharam update",
  "email": "masyharupdate@example.com",
  "phone": "08012345689"
}
```

response success:

```json
{
  "data": {
    "id": 1,
    "first_name": "masyhar update",
    "last_name": "muharam update",
    "email": "masyharupdate@example.com",
    "phone": "08012345689"
  }
}
```

response error:

```json
{
  "error": "first_name cannot be blank, ..."
}
```

## delete contact API

endpoint: DELETE /api/contacts/:id

request header :

- X-API-TOKEN : token

response success:

```json
{
  "data": "OK"
}
```

response error:

```json
{
  "error": "contact not found, ..."
}
```

## search contact API

endpoint: GET /api/contacts

query parameter :

- name : string, contact first_name or last_name, optional
- phone : string, contact phone, optional
- email : string, contact email, optional
- page : number, default 1
- size : number, default 10

request header :

- X-API-TOKEN : token

response success:

```json
{
  "data": [
    {
      "id": 1,
      "first_name": "masyhar",
      "last_name": "muharam",
      "email": "masyhar@example.com",
      "phone": "08012345678"
    },
    {
      "id": 2,
      "first_name": "masyhar",
      "last_name": "muharam",
      "email": "masyhar@example.com",
      "phone": "08012345678"
    }
  ],
  "paging": {
    "page": 1,
    "total_page": 10,
    "size": 10
  }
}
```

response error:

```json
{
  "error": "unauthorize, ..."
}
```
