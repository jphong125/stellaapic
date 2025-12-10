# Start Game

## Overview
In order to connect to servers, creates a game session for users.

After requesting "Start Game" with individually notified API URL, API servers will respond accordingly.

Redirect a user to received game session URL to entering to Stella system.

## Request

Requested "Start game" API URL will be notified individually, for security reasons.

## Request for a Start game 

Requesting "start game" to Stella API Servers.

### Request Parameters

| Name         | Data Type | Description                                                                                                                          |  Remark  |
|:-------------|:---------:|:-------------------------------------------------------------------------------------------------------------------------------------|:--------:|
| secureLogin  |  string   | Partner Id for authentication in the Stella API service                                                                              | Required |
| token        |  string   | Token of the Partner from Authenticate response.                                                                                     | Required |
| uuid         |  string   | A unique ID for each request.                                                                                                        | Required |
| userId       |  string   | Unique identifier of the player within the Casino Operator system.                                                                   | Required |
| userNickname |  string   | Nickname of the player within the Casino Operator system.                                                                            | Optional |
| gameId       |  string   | Symbolic unique identifier of the game within the Stella system.                                                                     | Required |
| sessionId    |  string   | User’s game session id on Stella system. (Issued by operater or platfom provider.)                                                   | Required |
| language     |  string   | Language to be displayed when the game is opened.                                                                                    | Required |
| betLimit     |  object   | How this is used is supplier specific, for example it might constitute a further restriction on limits already in place on the game. | Required |
| currency     |  string   | Currency to be used for playing game.                                                                                                | Required |
| cashierURL   |  string   | A URL to opening the Operator’s website Cashier page.                                                                                | optional |
| lobbyURL     |  string   | A URL to opening the Operator’s website lobby page.                                                                                  | optional |
| ipAddress    |  string   | IP address of the player.                                                                                                            | optional |

### Examples

METHOD

``` html
POST
```

URL

``` html
https://<API URL>/v1/StartGame
```

HEADER

``` html
Content-Type: application/json
```
### Example of HTTP BODY

``` json
{
    "secureLogin" : "<partnerId>",
    "uuid" : "fSYFZMScpZ01FhR26r59GexREh1xHgEY",
    "token" : "<token>",
    "userId" : "tester",
    "userNickname" : "Tester",
    "gameId" : "lm_1_speed_baccarat1",
    "sessionId" : "site_created_session",
    "language" : "EN",
    "currency" : "USD",
    "betLimit": [
      { "type": "defaultbet", "default": 1},
      { "type": "banker", "min": 1, "max": 5000 },
      { "type": "tie", "min": 1, "max": 1000 },
      { "type": "playerpair", "min": 1, "max": 1000 },
      { "type": "bankerpair", "min": 1, "max": 1000 }
    ],
    "cashierURL" : "url",
    "lobbyURL" : "url"
}
```

## Response 

Example of successful response from LuckyMonaco API servers. Use URL parameters.

### response parameter
|Name|Data Type|            Description             |Remark |
|:---|:---:|:----------------------------------:|---|
| error  |  string   |           Code of error.           | Required |
| description |string| Response status short description. | Optional |
|url|string|    Used for player redirection.    | Required|

### Example of Json BODY

``` json
{

  "error": 0,
  "description": "Success",
  "url": "http://192.168.0.227/game/index_3.html?token=af7f54f4-cd53-4c94-92eb-5de9cca86a47"
}
```

