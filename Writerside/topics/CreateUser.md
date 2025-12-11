# Create User

## Overview
Create User Account

## Usage
You can create a user on our server by calling the URL provided by Kyren.

## API URL
For security reasons, we will notify you individually.

## Request Example

METHOD

``` http
 POST
```

URL

``` http
https://<API URL>/user/create?partner_id=<Partner ID>&token=<TOKEN>
```

HEADER

``` http
Content-Type: application/json
```

### Request Parameters

| Name | Data Type  | Description                         |
|:-----|:----------:|:------------------------------------|
| id   | string(32) | User ID                             |
| name | string(32) | User Name                           |
| uuid | string(36) | A unique ID for each request(uuid4) |

### Example of Request Body

``` json
{
    "id": "tester",
    "name": "kim test",
    "uuid" : "ab64cee3-f73b-4631-9abf-b1a09c1f9c36"
}
```

## Response Example

### Response Parameters

| Name                | Data Type | Description                          |
|:--------------------|:---------:|:-------------------------------------|
| status              |  string   | OK or Failed                         |
| uuid(36)            |  string   | A unique ID for each response(uuid4) |
| code(Failed only)   |  number   | Failed Code                          |
| reason(Failed only) |  number   | Error Reason                         |

### Success Example

``` json
{
    "status": "OK",
    "uuid" : "ab64cee3-f73b-4631-9abf-b1a09c1f9c36"
}
```

### Failed Example

``` json
{
    "status": "Failed",
    "uuid" : "ab64cee3-f73b-4631-9abf-b1a09c1f9c36",
    "code" : 2,
    "reason" : "Duplicate ID"
}
````