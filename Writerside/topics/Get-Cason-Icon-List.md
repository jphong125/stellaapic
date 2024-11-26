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
    "id": "340x340",
    "language" : "EN",
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
  "error":0,
  "description":"Success",
  "Icons":[
    {"game_id":"lm_32_jungleking","url":"https://r2.lmgamelab.com/icons/lm_32_jungleking/32_340x340.png"},
    {"game_id":"lm_37_piggymoney","url":"https://r2.lmgamelab.com/icons/lm_37_piggymoney/37_340x340.png"},
    {"game_id":"lm_49_blazingwild","url":"https://r2.lmgamelab.com/icons/lm_49_blazingwild/49_340x340.png"},
    {"game_id":"lm_60_tumblefortune","url":"https://r2.lmgamelab.com/icons/lm_60_tumblefortune/60_340x340.png"},
    {"game_id":"lm_43_jackpotstar","url":"https://r2.lmgamelab.com/icons/lm_43_jackpotstar/43_340x340.png"},
    {"game_id":"lm_10_kellyswheelsingle","url":"https://r2.lmgamelab.com/icons/lm_10_kellyswheelsingle/10_340x340.png"},
    {"game_id":"lm_41_buffalofreedom","url":"https://r2.lmgamelab.com/icons/lm_41_buffalofreedom/41_340x340.png"},
    {"game_id":"lm_52_cleopatratumble","url":"https://r2.lmgamelab.com/icons/lm_52_cleopatratumble/52_340x340.png"},
    {"game_id":"lm_2_kellyswheeldouble","url":"https://r2.lmgamelab.com/icons/lm_2_kellyswheeldouble/2_340x340.png"},
    {"game_id":"lm_53_jellyjelly","url":"https://r2.lmgamelab.com/icons/lm_53_jellyjelly/53_340x340.png"},
    {"game_id":"lm_34_giantslamp","url":"https://r2.lmgamelab.com/icons/lm_34_giantslamp/34_340x340.png"},
    {"game_id":"lm_8_treasureofzeus","url":"https://r2.lmgamelab.com/icons/lm_8_treasureofzeus/8_340x340.png"},
    {"game_id":"lm_14_childofsuccess","url":"https://r2.lmgamelab.com/icons/lm_14_childofsuccess/14_340x340.png"},
    {"game_id":"lm_19_childofhappiness","url":"https://r2.lmgamelab.com/icons/lm_19_childofhappiness/19_340x340.png"},
    {"game_id":"lm_55_clashofslot","url":"https://r2.lmgamelab.com/icons/lm_55_clashofslot/55_340x340.png"},
    {"game_id":"lm_13_wildkelly","url":"https://r2.lmgamelab.com/icons/lm_13_wildkelly/13_340x340.png"},
    {"game_id":"lm_40_ninejackpots","url":"https://r2.lmgamelab.com/icons/lm_40_ninejackpots/40_340x340.png"},
    {"game_id":"lm_44_cabaretcash","url":"https://r2.lmgamelab.com/icons/lm_44_cabaretcash/44_340x340.png"},
    {"game_id":"lm_25_goldbonus","url":"https://r2.lmgamelab.com/icons/lm_25_goldbonus/25_340x340.png"},
    {"game_id":"lm_47_godofthunder","url":"https://r2.lmgamelab.com/icons/lm_47_godofthunder/47_340x340.png"},
    {"game_id":"lm_27_shootthecannon","url":"https://r2.lmgamelab.com/icons/lm_27_shootthecannon/27_340x340.png"},
    {"game_id":"lm_28_buffalogold","url":"https://r2.lmgamelab.com/icons/lm_28_buffalogold/28_340x340.png"},
    {"game_id":"lm_31_sambatrio","url":"https://r2.lmgamelab.com/icons/lm_31_sambatrio/31_340x340.png"},
    {"game_id":"lm_26_greenhatfairy","url":"https://r2.lmgamelab.com/icons/lm_26_greenhatfairy/26_340x340.png"},
    {"game_id":"lm_30_goldenfish","url":"https://r2.lmgamelab.com/icons/lm_30_goldenfish/30_340x340.png"},
    {"game_id":"lm_42_medusaqueen","url":"https://r2.lmgamelab.com/icons/lm_42_medusaqueen/42_340x340.png"},
    {"game_id":"lm_15_childoffortune","url":"https://r2.lmgamelab.com/icons/lm_15_childoffortune/15_340x340.png"},
    {"game_id":"lm_4_egyptianbeauty","url":"https://r2.lmgamelab.com/icons/lm_4_egyptianbeauty/4_340x340.png"},
    {"game_id":"lm_35_burningseven","url":"https://r2.lmgamelab.com/icons/lm_35_burningseven/35_340x340.png"},
    {"game_id":"lm_11_threelittlepigs","url":"https://r2.lmgamelab.com/icons/lm_11_threelittlepigs/11_340x340.png"},
    {"game_id":"lm_1_pumpkinfarm","url":"https://r2.lmgamelab.com/icons/lm_1_pumpkinfarm/1_340x340.png"},
    {"game_id":"lm_3_killerwhale","url":"https://r2.lmgamelab.com/icons/lm_3_killerwhale/3_340x340.png"},
    {"game_id":"lm_7_dancingladybug","url":"https://r2.lmgamelab.com/icons/lm_7_dancingladybug/7_340x340.png"},
    {"game_id":"lm_17_goldenagent","url":"https://r2.lmgamelab.com/icons/lm_17_goldenagent/17_340x340.png"},
    {"game_id":"lm_9_roadtomysticoz","url":"https://r2.lmgamelab.com/icons/lm_9_roadtomysticoz/9_340x340.png"},
    {"game_id":"lm_33_kingsknight","url":"https://r2.lmgamelab.com/icons/lm_33_kingsknight/33_340x340.png"}
  ]
}
```



## Result of URL Link

![Tumble Fortune](https://r2.lmgamelab.com/icons/lm_60_tumblefortune/60_300x300_CN2.png)