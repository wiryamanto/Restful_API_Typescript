# Contact API Spec

## Create Contact

Endpoint : POST /api/contacts 

Request Header : 
- X-API-TOKEN : token

Request body : 

```json
{
    "first_name" : "Ragil",
    "Last_name" : "Wiryamanto",
    "email" : "ragil@xample.com",
    "phone" : "08999999"
}
```
Request Body (Success) : 

```json
{
    "data" : {
        "first_name" : "Ragil",
        "Last_name" : "Wiryamanto",
        "email" : "ragil@xample.com",
        "phone" : "08999999"
    }
}
```

Response Body (Failed)

```json
{
    "error" : "firs_name must not blank"
}

```

## Get Contact

Endpoint : Get /api/contacts/:id

Request Header : 
- X-API-TOKEN : token


Request Body (Success) : 

```json
{
    "data" : {
        "first_name" : "Ragil",
        "Last_name" : "Wiryamanto",
        "email" : "ragil@xample.com",
        "phone" : "08999999"
    }
}
```

Response Body (Failed)

```json
{
    "error" : "Contact is not found"
}

```

## Update Contact

Endpoint : PUT /api/contacts/:id

Request Header : 
- X-API-TOKEN : token

Request body : 

```json
{
    "first_name" : "Ragil",
    "Last_name" : "Wiryamanto",
    "email" : "ragil@xample.com",
    "phone" : "08999999"
}
```
Request Body (Success) : 

```json
{
    "data" : {
        "first_name" : "Ragil",
        "Last_name" : "Wiryamanto",
        "email" : "ragil@xample.com",
        "phone" : "08999999"
    }
}
```

Response Body (Failed)

```json
{
    "error" : "firs_name must not blank"
}

```

## Remove Contact

Endpoint : DELETE /api/contacts/:id

Request Header : 
- X-API-TOKEN : token


Request Body (Success) : 

```json
{
    "data" : "OK"
}
```

Response Body (Failed)

```json
{
    "error" : "Contact is not Found"
}

```

## Search Contact

Endpoint : Get /api/contacts

Query Parameter : 
- name : string, contact first name or contact last name, optional
- phone : string, contact phone, optional
- email : string, contact email, optional
- page : number, default 1
- size : number, default 10 

Request Header : 
- X-API-TOKEN : token

Request Body (Success) : 

```json
{
    "data" : [
        {
        "id" : 1,
        "first_name" : "Ragil",
        "Last_name" : "Wiryamanto",
        "email" : "ragil@xample.com",
        "phone" : "08999999"
    },
    {
        "id" : 2,
        "first_name" : "Ragil",
        "Last_name" : "Wiryamanto",
        "email" : "ragil@xample.com",
        "phone" : "08999999"
    }
    ],
    "paging": {
        "current_page" : 1,
        "total_page" : 10,
        "size" : 10
    }
}

```

Response Body (Failed)

```json
{
    "error" : "Unauthorized "
}

```