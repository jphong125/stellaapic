# Get Casino Games

## Overview
Using this method Casino Operator will get the list of casino games available for the integration.

## Request

Requested get casino games API URL will be notified individually, for security reasons.

###  Request Parameters

| Name        | Data Type | Description                                                  | Remark |
|:------------|:---------:|:-------------------------------------------------------------|:---------:|
| secureLogin  |string| Partner Id for authentication in the LuckyMonaco API service | Required |
| token      |  string   | Token of the Partner from Authenticate response.             | Required |
| uuid                |  string   | A unique ID for each request.                                | Required |

### Examples

METHOD

``` http
POST
```

URL

``` http
https://<API URL>/v1/GetCasinoGame
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

Example of successful response from Stella API servers.

###  Response parameters

|    Name     |                   | Data Type | Remark                                                                                                       |
|:-----------:|:-----------------:|:---------:|:-------------------------------------------------------------------------------------------------------------|
|    error    |                   |  string   | Code of error.                                                                                               |
| description |                   |  string   | Response status short description.                                                                           |
|  gameList   |                   |   array   | List of game information.                                                                                    |
|             |      gameId       |  string   | Symbolic unique identifier of the game provided by Stella.                                                   |
|             |     gameName      |  string   | Name of the game.                                                                                            |
|             |  typeDescription  |  string   | Short description of the game type. (i.e. "LB" : live baccarat, "vs" : video slot, "vp" : video poker)       |
|             |     platform      |  string   | Platform for which the game can be opened.                                                                   |
|             | demoGameAvailable |  boolean  | If true, a demo version of the game is available.                                                            |
|             |   gameIdNumeric   |  integer  | Numeric value of gameId.                                                                                     |
|             |   jurisdictions   |  string   | Jurisdiction of the player.                                                                                  |
|             |        rtp        |  string   | RTP of the game.                                                                                             |
|             |    tableLimits    |  string   | Casino Operator will get table bet limits, bet range, maxPlayer for the games.                               |
|             |     dataType      |  string   | Type of game portfolio. (i.e. "LC" : Live Casino portfolio, "RNG" : Main Portfolio games (video slots, etc)) |
|             |    tableImage     |  string   | Casino Operator will get casino icon (i.e. thumbnail) info for the games.                                    |
|             |  gameDescription  |  string   | Description of the game.                                                                                     |
|             |      release      |  boolean  | If true, the game is released and available to use.                                                          |
|             |    releaseDate    |  string   | Date of release of the game.                                                                                 |

### Example of Json BODY

``` json
{

  "error": 0,
  "description": "Success",
  "gameList": [
    {
      "gameId": "6_speed_baccarat1",
      "gameName": "Speed Baccarat1",
      "typeDescription": "LB",
      "platform": "MOBILE, PC",
      "demoGameAvailable": false,
      "gameIdNumeric": 1,
      "jurisdictions": "99",
      "rtp": "98.76%",
      "tableLimits":
        {
          "maxBef" : 5000.0, "maxPlayers": 1200, minBet: 0.2, ranges: [0.1, 0.2, 0.25,0.4, 0.5,1.0]
        },
      "dataType": "LC",
      "tableImage": "https://client.pragmaticplaylive.net/desktop/assets/snaps/pwnhicogrzeodk79/poster.jpg? V0.38990292533435056",
      "gameDescription": "Enjoy a fast-paced baccarat game streamed live with real guests from a luxury casino hotel.",
      "release": true,
      "releaseDate": "2025-12-11"
    },
    {
      "gameId": "7_speed_baccarat2",
      "gameName": "Speed Baccarat2",
      "typeDescription": "LB",
      "platform": "MOBILE, PC",
      "demoGameAvailable": false,
      "gameIdNumeric": 1,
      "jurisdictions": "99",
      "rtp": "98.76%",
      "tableLimits":
      {
        "maxBef" : 5000.0, "maxPlayers": 1200, minBet: 0.2, ranges: [0.1, 0.2, 0.25,0.4, 0.5,1.0]
      },
      "dataType": "LC",
      "tableImage": "https://client.pragmaticplaylive.net/desktop/assets/snaps/pwnhicogrzeodk79/poster.jpg? V0.38990292533435056",
      "gameDescription": "Enjoy a fast-paced baccarat game streamed live with real guests from a luxury casino hotel.",
      "release": true,
      "releaseDate": "2025-12-11"
    },,,,

```

