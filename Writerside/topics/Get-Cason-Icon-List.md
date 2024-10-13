# Get Cason Icon List

## Overview
Using this method Casino Operator will get icons list for the games :

## API URL
Requested get a list of game URL will be notified individually, for security reasons.

###  Request parameters

| Name          |Data Type| Description                                                                                                                                                        | Remark |
|:--------------|:---:|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------|:---------:|
| gameid        |string| Symbolic unique identifier of the game within the Lucky Monaco system.                                                                                                       | Required | 
| gameIdnumeric |string| Numeric value of gameId | Required |

### Examples

METHOD

``` http
POST
```

URL

``` http
https://<API URL>/V4/GetCasinoIconInfo
```

HEADER

``` http
Content-Type: application/json
```

###  Response parameters

|   Name   |                   | Data Type | Description                                                                           |
|:--------:|:-----------------:|:---------:|:--------------------------------------------------------------------------------------|
| gameList |                   |   array   | List of game information.                                                             |
|          |      gameId       |  string   | Symbolic unique identifier of the game provided by Lucky Monaco.                      |
|          |     gameName      |  string   | Name of the game.                                                                     |
|          |    gameNameZh     |  string   | Chines name of the game.                                                              |
|          |    gameName-Tw    |  string   | Chines (Traditional) name of the game.                                                |
|          |  typeDescription  |  string   | Short description of the game type.                                                   |
|          |     platform      |  string   | Platform for which the game can be opened.                                            |
|          | demoGameAvailable |  boolean  | If true, a demo version of the game is available.                                     |
|          |    aspectRatio    |  string   | Describes the proportional relationship between the width and the height of the game. |
|          |   gameIdNumeric   |  number   | Numeric value of gameId                                                               |
|          |   jurisdictions   |  string   | Jurisdiction of the player                                                            |
|          |   frbAvailable    |  boolean  | Boolean If true, a free round bonus of the game is available.                         |
|          |       lines       |  string   | Number of available pay lines in the game                                             |
|          |     rowReels      |  string   | Layout of the game                                                                    |
|          |        rtp        |  string   | Rtp of the game                                                                       |
|          |     dataType      |  string   | Type of game portfolio                                                                |
|          |  gameDescription  |  string   | Description of the game                                                               |
|          |      release      |  boolean  | If true, the game is available.                                                       |
|          |    releaseDate    |  string   | Date of release of the game                                                           |

### Example of body

``` json
{

  "error": 0,
  "description": "Success",
  "gameList": [

    {

      "gameId": "lm_1_pumpkinfarm",
      "gameName": "Pumpkin Farm",
      "gameNameZh": "南瓜农场",
      "gameName-Tw": "南瓜農場",
      "typeDescription": "vs",
      "platform": "MOBILE, PC",
      "demoGameAvailable": true,
      "aspectRatio": "16:9",
      "gameIdNumeric": 1,
      "jurisdictions": "99",
      "frbAvailable": true,
      "lines": "25",
      "rowreels": "5x3",
      "rtp": "96.08%",
      "dataType": "RNG",
      "gameDescription": "Hard working farmer is living with animals and farming pumpkin patch. \nIn the bonus game, you can select and earn something valuable from this special pumpkin farm.",
      "release": true,
      "releaseDate": "2023-01-11"
    },
    {

      "gameId": "lm_2_kellyswheeldouble",
      "gameName": "Kelly's Wheel Double",
      "gameNameZh": "凯利双轮",
      "gameName-Tw": "凱利雙輪",
      "typeDescription": "vs",
      "platform": "MOBILE, PC",
      "demoGameAvailable": true,
      "aspectRatio": "16:9",
      "gameIdNumeric": 2,
      "jurisdictions": "99",
      "frbAvailable": true,
      "lines": "5",
      "rowreels": "3x3",
      "rtp": "96.03%",
      "dataType": "RNG",
      "gameDescription": "Enjoy the big win from 3x3, \n5-line machine slot in Kelly's Wheel Double. \nNot only that, you can count on a great chance in the bonus game \nwhere two wheels are spinning.",
      "release": true,
      "releaseDate": "1899-12-30"
    },
```



## Successful response

![Tumble Fortune](https://r2.lmgamelab.com/icons/lm_60_tumblefortune/60_340x340.png)