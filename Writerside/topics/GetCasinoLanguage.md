# Get Casino Language


## Overview
Using this method Casino Operator will get the game language from LuckyMonaco to proceed a specific game.


## API URL

Requested get casino language URL will be notified individually, for security reasons.

###  Request parameters

| Name        |Data Type| Description                                                 | Remark |
|:------------|:---:|:------------------------------------------------------------|:---------:|
| secureLogin |string| User name for authentication in the Casino Game API service | Required |
| token      |string| Token of the player from Authenticate response              | Required |
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
    "token" : "<token>"
}
```

## Response

###  Response parameters

|     Name     |          | Data Type | Remark                              |
|:------------:|:--------:|:---------:|:------------------------------------|
| eroor  |          |        string                                            | code of error  |
| description |          |string  | Response status short description. |
| languageList |          |   array   | List of language information.       |
|              | language |  string   | Language code in ISO 639-1 standard |


### Example of body

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

