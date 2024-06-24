# ADDRESS API SPEC

## create address

endpoint: POST /api/contacts/:contactId/addresses

request header :

- X-API-TOKEN : token

request body:

```json
{
  "street": "Jalan ...",
  "city": "Jakarta",
  "postal_code": "93211",
  "province": "DKI Jakarta",
  "country": "Indonesia",
}
```

response success:

```json
{
  "data": {
    "id": 1,
    "street": "Jalan ...",
    "city": "Jakarta",
    "postal_code": "93211",
    "province": "DKI Jakarta",
    "country": "Indonesia",
  }
}
```

response error:

```json
{
  "error": "country cannot be blank!, ..."
}
```

## get address

endpoint: GET /api/contacts/:contactId/addresses/:addressId

request header :

- X-API-TOKEN : token

response success:

```json
{
  "data": {
    "id": 1,
    "street": "Jalan ...",
    "city": "Jakarta",
    "postal_code": "93211",
    "province": "DKI Jakarta",
    "country": "Indonesia",
  }
}
```

response error:

```json
{
  "error": "address is not found!, ..."
}
```

## update address

endpoint: PUT /api/contacts/:contactId/addresses/:addressId

request header :

- X-API-TOKEN : token

request body:

```json
{
  "street": "Jalan ...",
  "city": "Jakarta",
  "postal_code": "93211",
  "province": "DKI Jakarta",
  "country": "Indonesia",
}
```

response success:

```json
{
  "data": {
    "id": 1,
    "street": "Jalan ...",
    "city": "Jakarta",
    "postal_code": "93211",
    "province": "DKI Jakarta",
    "country": "Indonesia",
  }
}
```

response error:

```json
{
  "error": "country cannot be blank!, ..."
}
```

## delete address

endpoint: DELETE /api/contacts/:contactId/addresses/:addressId

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
  "error": "address is not found!, ..."
}
```

## list address

endpoint: GET /api/contacts/:contactId/addresses/

request header :

- X-API-TOKEN : token

response success:

```json
{
  "data": [
    {
      "id": 1,
      "street": "Jalan ...",
      "city": "Jakarta",
      "postal_code": "93211",
      "province": "DKI Jakarta",
      "country": "Indonesia",
    },
    {
      "id": 2,
      "street": "Jalan ...",
      "city": "Jakarta",
      "postal_code": "93211",
      "province": "DKI Jakarta",
      "country": "Indonesia",
    }
  ]
}
```

response error:

```json
{
  "error": "contact is not found!, ..."
}
```
