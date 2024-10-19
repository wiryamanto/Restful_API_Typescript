# User APi Spec

## Register User

Endpoint : POST /api/users

Request Body : 

```json
{
    "username" : "Wiryamanto",
    "password" : "Secret",
    "name" : "Ragil Wiryamanto"
}
```

Response Body (Success)

```json
{
    "data": {
        "username": "Wiryamanto",
        "name" : "Ragil Wiryamanto"
    }
}
```

Response Body (Failed) : 

```json
{
    "errors" : "Username must not blank, ..."
}
```

## Login User

Endpoint : POST /api/users/login

Request Body : 

```json
{
    "username" : "Wiryamanto",
    "password" : "Secret",
}
```

Response Body (Success)

```json
{
    "data": {
        "username": "Wiryamanto",
        "name" : "Ragil Wiryamanto",
        "token" : "uuid"
    } 
}
```

Response Body (Failed) : 

```json
{
    "errors" : "wrong username or Password"
}
```

## Get User

Endpoint : GET /api/current

Request Header : 
- X-API-TOKEN : token

Response Body (Success)

```json
{
    "data": {
        "username": "Wiryamanto",
        "name" : "Ragil Wiryamanto"
    }
}
```

Response Body (Failed) : 

```json
{
    "errors" : "Unauthorized"
}
```

## Update User

Endpoint : PATCH /api/users/current

Request Header : 
- X-API-TOKEN : token

Request Body : 

```json
{
    "password" : "Secret", // tidak wajib
    "name" : "Ragil Wiryamanto" // tidak wajib
}
```

Response Body (Success)

```json
{
    "data": {
        "username": "Wiryamanto",
        "name" : "Ragil Wiryamanto"
    }
}
```

Response Body (Failed) : 

```json
{
    "errors" : "Unatuhorize"
}
```

## Logout User

Endpoint : DELETE /api/users/current

Request Header : 
- X-API-TOKEN : token


Response Body (Success)

```json
{
    "data": "OK"
}
```

Response Body (Failed) : 

```json
{
    "errors" : "Unatuhorized, ..."
}
```