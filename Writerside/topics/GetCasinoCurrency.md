# Get Casino Currency

## Overview
Using this method Casino Operator will retrieve the currencies that are available in LuckyMonaco games to proceed a specific game.

## Request

Requested "Get Casino Currency" URL will be notified individually, for security reasons.

###  Request Parameters

| Name        |Data Type| Description                                                 | Remark |
|:------------|:---:|:------------------------------------------------------------|:---------:|
| secureLogin  |string| partner Id for authentication in the LuckyMonaco API service | Required |
| token      |string| Token of the Partner from Authenticate response              | Required |
| uuid                |  string   | A unique ID for each request                                             | Required |


### Examples

METHOD

``` http
POST
```

URL

``` http
https://<API URL>/V4/GetCasinoCurrency
```

HEADER

``` http
Content-Type: application/json
```
### Example of HTTP BODY

``` json
{
    "secureLogin" : "<partnerId>",
    "token" : "<token>",
    "uuid": "<uuid>"
}
```

## Response

Example of successful response from LuckyMonaco API servers.

### Response parameters

|     Name      |          | Data Type | Remark                          |
|:-------------:|:--------:|:---------:|:--------------------------------|
| error  |          |        string                                          | code of error                          |
| description |          | string    | Response status short description.                      |
| Currency list |          |   array   | List of Currency information.   |
|               | Currency |  string   | Player's ISO 4217 currency code |


### Example of Json BODY

``` json
{

  "error": 0,
  "description": "Success",
  "CurrencyList": [

    "KRW",
    "USD"
  ]
}
```

