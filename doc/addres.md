# Address API Spec

## Create Address

Endpoint : POST /api/contact/:idContact/address

Request Header :

- X-API-TOKEN : token

Request Body :

```json
{
  "street": "jalan apa",
  "city": "kota apa",
  "province": "Provinsi apa",
  "country": "Negara apa",
  "postal_code": "23123"
}
```

Response Body (Success) :

```json
{
  "data": {
    "id": 1,
    "street": "jalan apa",
    "city": "kota apa",
    "province": "Provinsi apa",
    "country": "Negara apa",
    "postal_code": "23123"
  }
}
```

Response Body (failed)

```
{
    "errors" : "postal_code is required"
}
```


## Get Address

Endpoint : GET /api/contact/:idContact/address/:idAddress

Request Header :

- X-API-TOKEN : token


Response Body (Success) :

```json
{
  "data": {
    "id": 1,
    "street": "jalan apa",
    "city": "kota apa",
    "province": "Provinsi apa",
    "country": "Negara apa",
    "postal_code": "23123"
  }
}
```

Response Body (Failed) :

```json
{
    "errors" : "Address is not found"
}

```

## Update Address

Endpoint : PUT /api/contact/:idContact/address/:idAddress

Request Header :

- X-API-TOKEN : token

Request Body :

```json
{
  "street": "jalan apa",
  "city": "kota apa",
  "province": "Provinsi apa",
  "country": "Negara apa",
  "postal_code": "23123"
}
```

Response Body (Success) :

```json
{
  "data": {
    "id": 1,
    "street": "jalan apa",
    "city": "kota apa",
    "province": "Provinsi apa",
    "country": "Negara apa",
    "postal_code": "23123"
  }
}
```

Response Body (failed)

```
{
    "errors" : "postal_code is required"
}
```

## Remove Address

Endpoint : DELETE /api/contact/:idContact/address/:idAddress

Request Header :

- X-API-TOKEN : token

Response Body (Success) :

```json
{
  "data": "OK"
}
```

Response Body (failed)

```
{
    "errors" : "Address is not found"
}
```

## List Address

Endpoint : GET /api/contact/:idContact/address

Request Header :

- X-API-TOKEN : token

Response Body (Success) :

```json
{
  "data": [
    {
    "id": 1,
    "street": "jalan apa",
    "city": "kota apa",
    "province": "Provinsi apa",
    "country": "Negara apa",
    "postal_code": "23123"
  },
  {
    "id": 2,
    "street": "jalan apa",
    "city": "kota apa",
    "province": "Provinsi apa",
    "country": "Negara apa",
    "postal_code": "23123"
  }
  ]
}
```

Response Body (failed)

```
{
    "errors" : "Contact is not found"
}
```