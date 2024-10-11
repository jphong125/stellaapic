# Get Casino Language


## Overview
Using this method Casino Operator will get the game language from LuckyMonaco to proceed a specific game.


## API URL

Requested get casino language URL will be notified individually, for security reasons.

###  Request parameters

| Name        |Data Type| Description                                                                                                                                                        | Remark |
|:------------|:---:|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------|:---------:|
| secureLogin |string| User name for authentacation in the Casino Game API service                                                                                                        | Required |
| hash        |string| Hash code of request.                                                                                                                                              | Required |
### Examples

METHOD

``` http
POST
```

URL

``` http
https://<API URL>/V4/getcasinolanguage?MEMB_ID=<securelogin>&HASH=<TOKEN>
```

HEADER

``` http
Content-Type: application/json
```

## Successful response

###  Response parameters

|     Name      |                   | Data Type | Description                                                                           |
|:-------------:|:-----------------:|:---------:|:--------------------------------------------------------------------------------------|
| Language list |                   |   array   | List of language information.                                                         |
|               |     language      |  string   |  Language code in ISO 639-1 standard                      |


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

