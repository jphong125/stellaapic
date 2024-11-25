# Get Casino Icon List

## Overview
Using this method Casino Operator will get icons list for the games.

## Request
Requested get a list of game URL will be notified individually, for security reasons.

###  Request Parameters

| Name        |Data Type| Description                                                              | Remark |
|:------------|:---:|:-------------------------------------------------------------------------|:---------:|
| secureLogin  |string| Partner Id for authentication in the LuckyMonaco API service             | Required |
| token      |string| Token of the Partner from Authenticate response.                         | Required |
| id          |string| Icon size consisting of width and height. (can get Get Casino Icon Info) | Required |
| language    |string| Language of icon.                                                        | Required |
| uuid                |  string   | A unique ID for each request.                                            | Required |

### Example of URL
METHOD

``` http
POST
```

URL

``` http
https://<API URL>/v4/GetCasinoIconList
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
    "id": "300x300_ZH",
    "language" : "ZH-TW",
    "uuid": "<uuid>"
}
```
## Response

Example of successful response from LuckyMonaco API servers.

###  Response parameters

|    Name     |        | Data Type | Description                                                      |
|:-----------:|:------:|:---------:|:-----------------------------------------------------------------|
|    error    |        |              string                                    | code of error.                                                   |
| description |        |  string | Response status short description.                               |
|    icons    |        |   array   | List of game information.                                        |
|             | gameId |  string   | Symbolic unique identifier of the game provided by Lucky Monaco. |
|             |  url   |  string   | Url of icon.                                                     |


### Example of Json BODY

``` json
{

  "error": 0,
  "description": "Success",
  "Icons": [

    {

      "game_id": "lm_60_tumblefortune",
      "url": "https://r2.lmgamelab.com/icons/lm_60_tumblefortune/60_300x300_CN2.png"
    },
    {

      "game_id": "lm_55_clashofslot",
      "url": "https://r2.lmgamelab.com/icons/lm_55_clashofslot/55_300x300_CN2.png"
    },
    {

      "game_id": "lm_53_jellyjelly",
      "url": "https://r2.lmgamelab.com/icons/lm_53_jellyjelly/53_300x300_CN2.png"
    },
    {

      "game_id": "lm_52_cleopatratumble",
      "url": "https://r2.lmgamelab.com/icons/lm_52_cleopatratumble/52_300x300_CN2.png"
    },
    {

      "game_id": "lm_49_blazingwild",
      "url": "https://r2.lmgamelab.com/icons/lm_49_blazingwild/49_300x300_CN2.png"
    },,,,
```



## Result of URL Link

![Tumble Fortune](https://r2.lmgamelab.com/icons/lm_60_tumblefortune/60_300x300_CN2.png)