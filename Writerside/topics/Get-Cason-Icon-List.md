# Get Cason Icon List

## Overview
Using this method Casino Operator will get icons list for the games :

## API URL
Requested get a list of game URL will be notified individually, for security reasons.

###  Request parameters

| Name        |Data Type| Description                                                            | Remark |
|:------------|:---:|:-----------------------------------------------------------------------|:---------:|
| secureLogin |string| User name for authentacation in the Casino Game API service            | Required |
| token      |string| Token of the player from Authenticate response                         | Required |
| id          |string| Icon size consisting of width and height (can get Get Casino Icon Info | Required |
| language    |string| Language of icon                                                       | Required |

### Example of URL
METHOD

``` http
POST
```

URL

``` http
https://<API URL>/V4/GetCasinoIconList
```

HEADER

``` http
Content-Type: application/json
```

### Example of HTTP BODY

``` json
{
    "secureLogin" : "S100",
    "token" : "fSYFZMScpZ01FhR26r59GexREh1xHgEY",
    "id": "300x300_ZH",
    "language" : "ZH-TW"
}
```
## Response

###  Response parameters

| Name  |                   | Data Type | Description                                                      |
|:-----:|:-----------------:|:---------:|:-----------------------------------------------------------------|
| Icons |                   |   array   | List of game information.                                        |
|       |      gameId       |  string   | Symbolic unique identifier of the game provided by Lucky Monaco. |
|       |        url        |  string   | Url of icon                                                      |


### Example of body

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
    },
```



## Result of URL Link

![Tumble Fortune](https://r2.lmgamelab.com/icons/lm_60_tumblefortune/60_340x340.png)