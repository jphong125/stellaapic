# Free Round


## Overview

Retrieve the game list from LuckyMonaco to proceed a specific game.

## Usage

Game list can be retrieved as per your request through individual API URL.

## API URL

Requested game session API URL will be notified individually, for security reasons.

Request parameters

| Name        |Data Type| Description                                                                                                                                                        | Remark |
|:------------|:---:|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------|:---------:|
| secureLogin |string| User name for authentacation in the Casino Game API service                                                                                                        | Required | 
| options     |string| List of settings. By including it, operator can get additional information about<br/>possible valeues are : <br/>. GetFrbDetails<br/>. GetLines<br/>. GetDataTypes | Optional |
| hash        |string| Hash code of request.                                                                                                                                              | Required |
### Examples

METHOD

``` http
POST
```

URL

``` http
https://<API URL>/V4/getcasinogame?MEMB_ID=<Partner ID>&HASH=<TOKEN>
```

HEADER

``` http
Content-Type: application/json
```

## Successful response for getting Game List

Response parameters

|        Name         |                   | Data Type | Description                                                                           |
|:-------------------:|:-----------------:|:---------:|:--------------------------------------------------------------------------------------|
|      Gamelist       |                   |   array   | List of game information.                                                             |
|                     |      gameId       |  string   | Symbolic unique identifier of the game provided by Lucky Monaco.                      |
|                     |     gameName      |  string   | Name of the game.                                                                     |
|                     |    gameNameZh     |  string   | Chines name of the game.                                                              |
|                     |    gameName-Tw    |  string   | Chines (Traditional) name of the game.                                                |
|                     |  typeDescription  |  string   | Short description of the game type.                                                   |
|                     |     platform      |  string   | Platform for which the game can be opened.                                            |
|                     | demoGameAvailable |  boolean  | If true, a demo version of the game is available.                                     |
|                     |    aspectRatio    |  string   | Describes the proportional relationship between the width and the height of the game. |
|                     |   gameIdNumeric   |  number   | Numeric value of gameId                                                               |
|                     |   jurisdictions   |  string   | Jurisdiction of the player                                                            |
|                     |   frbAvailable    |  boolean  | Boolean If true, a free round bonus of the game is available.                         |
|                     |       lines       |  string   | Number of available pay lines in the game                                             |
|                     |     rowreels      |  string   | Layout of the game                                                                    |
|                     |        rtp        |  string   | Rtp of the game                                                                       |
|                     |     dataType      |  string   | Type of game portfolio                                                                |
|                     |  gameDescription  |  string   | Description of the game                                                               |
|                     |      release      |  boolean  | If true, the game is available.                                                       |
|                     |    releaseDate    |  string   | Date of release of the game                                                           |

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

## Failure response for getting Game List ( response )

Example of failure response from LuckyMonaco API servers.

In case of failure, LuckyMonaco servers will return  'HTTP status 4XX' or 'HTTP status 5XX' and following response body.

### Example of body2

``` json
{
    "error": {
        "code": "G.1",
        "message": "INVALID GAME TYPE"
    }
}
```

### Error codes

Error codes are classified into following categories.

* G - Generic failures
* V - Validation of input parameters failed

|Code|Description (omitting error codes)|
|:---|:---:|
|G.01|Invalid game type|

Error codes will be additionally updated

Start typing here...