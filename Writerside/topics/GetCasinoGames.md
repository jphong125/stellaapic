# Get Casino Games

## Overview
Using this method Casino Operator will get the list of casino games available for the integration.

## API URL

Requested get casino games API URL will be notified individually, for security reasons.

###  Request parameters

| Name        |Data Type| Description                                                 | Remark |
|:------------|:---:|:------------------------------------------------------------|:---------:|
| secureLogin |string| User name for authentication in the Casino Game API service | Required |
| token      |string| Token of the player from Authenticate response              | Required |
| uuid                |  string   | A unique ID for each request                                             | Required |

### Examples

METHOD

``` http
POST
```

URL

``` http
https://<API URL>/V4/GetCasinoGame
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

|   Name   |                   | Data Type | Remark                                                                                                     |
|:--------:|:-----------------:|:---------:|:-----------------------------------------------------------------------------------------------------------|
| eroor  |                   |                              string                        | code of error                                                                                              |
| description |                   | decimal| Response status short description.                                                                         |
| gameList |                   |   array   | List of game information.                                                                                  |
|          |      gameId       |  string   | Symbolic unique identifier of the game provided by Lucky Monaco.                                           |
|          |     gameName      |  string   | Name of the game.                                                                                          |
|          |    gameNameZh     |  string   | Chinese name of the game.                                                                                  |
|          |   gameNameZh-Tw   |  string   | Chinese (Traditional) name of the game.                                                                    |
|          |  typeDescription  |  string   | Short description of the game type. (i.e. "vs" : video slot, "vp" : video poker                            |
|          |     platform      |  string   | Platform for which the game can be opened.                                                                 |
|          | demoGameAvailable |  boolean  | If true, a demo version of the game is available.                                                          |
|          |    aspectRatio    |  string   | Describes the proportional relationship between the width and the height of the game.                      |
|          |   gameIdNumeric   |  number   | Numeric value of gameId                                                                                    |
|          |   jurisdictions   |  string   | Jurisdiction of the player                                                                                 |
|          |   frbAvailable    |  boolean  | Boolean if true, FREE ROUND bonus feature is available to this particular game.                            |
|          |       lines       |  string   | Number of available pay lines in the game                                                                  |
|          |     rowReels      |  string   | Layout of the game                                                                                         |
|          |        rtp        |  string   | RTP of the game                                                                                            |
|          |     dataType      |  string   | Type of game portfolio (i.e. "RNG" : Main portfolil games (video slots, etc), "lc" : Live Casino portfolio |
|          |  gameDescription  |  string   | Description of the game                                                                                    |
|          |      release      |  boolean  | If true, the game is released and available to use                                                         |
|          |    releaseDate    |  string   | Date of release of the game                                                                                |

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
      "gameNameZh-Tw": "南瓜農場",
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
      "gameNameZh-Tw": "凱利雙輪",
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
      "releaseDate": "2023-01-11"
    },
```

