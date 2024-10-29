# Get Casino Language


## Overview
Using this method Casino Operator will get the game language from LuckyMonaco to proceed a specific game.


## Request

Requested "Get Casino Language" URL will be notified individually, for security reasons.

###  Request Parameters

| Name        |Data Type| Description                                                 | Remark |
|:------------|:---:|:------------------------------------------------------------|:---------:|
| secureLogin  |string| partner Id for authentication in the Casino Game API service | Required |
| token      |string| Token of the Partner from Authenticate response              | Required |
| uuid                |  string   | A unique ID for each request                                             | Required |

### Examples

METHOD

``` http
POST
```

URL

``` http
https://<API URL>/V4/GetCasinoLanguage
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

###  Response parameters

|     Name     |          | Data Type | Remark                               |
|:------------:|:--------:|:---------:|:-------------------------------------|
| error  |          |        string                                            | code of error                        |
| description |          |string  | Response status short description.   |
| languageList |          |   array   | List of language information.        |
|              | language |  string   | Language code in ISO 639-1 standard. |


### Example of Json BODY

``` json
{

  "error": 0,
  "description": "Success",
  "LanguageList": [

    "EN",
    "JA",
    "KO"
  ]
}
```

