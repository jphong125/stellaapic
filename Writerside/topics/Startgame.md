# Start game

## Overview
In order to connect to servers, creates a game session for users.

After requesting "Start Game" with individually notified API URL, API servers will respond accordingly.

Redirect a user to received game session URL to entering to LuckyMonaco system.

## API URL

Requested "Start game" API URL will be notified individually, for security reasons.

## Request for a Start game 

Requesting "start game" to LuckyMonaco API Servers.

### Request parameters

| Name         |Data Type| Description                                                            |  Remark  |
|:-------------|:---:|:-----------------------------------------------------------------------|:--------:|
| secureLogin  |string| User name for authentication in the Casino Game API service            | Required |
| uuid         |string| A unique ID for each request                                           | Required |
| userId       |string| Unique identifier of the player within the Casino Operator system.     | Required |
| userNickname |string| Nickname of the player within the Casino Operator system.              | Optional |
| gameId       |string| Symbolic unique identifier of the game within the Lucky Monaco system. | Required |
| sessionId    |string| Player’s game session id on Lucky Monaco system.                       | Required |
| language     |string| Language to be displayed when the game is opened.                      | Required |
| currency     |string| Currency to be used for playing game.                                  | Required |
| region       |string| The region where the player is located. (select "Asia" or "Europe")    | Optional |
| cashierURL   |string| A URL to opening the Operator’s website Cashier page.                  | optional |
| lobbyURL     |string| A URL to opening the Operator’s website lobby page.                    | optional |
| ipAddress    |string| IP address of the player.                   | optional |

### Examples

METHOD

``` html
POST
```

URL

``` html
https://<API URL>/api/V4/StartGame
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
    "UserId" : "tester",
    "UserNickname" : "Tester",
    "gameId" : "lm_9_roadtomysticoz",
    "sessionId" : "site_created_session",
    "language" : "EN",
    "region" : "ASIA" 
    "currency" : "USD",
    "cashierURL" : "",
    "lobbyURL" : ""
}
```

## Response 

Example of successful response from LuckyMonaco API servers. Use URL parameters.

### response parameter
|Name|Data Type|Description|Ramrk|
|:---|:---:|:---:|---|
| eroor  |  string   | code of error                                                   | Required |
| description |string| Response status short description. | Optional |
|url|string|used for player redirection.| Required|

### Example of response BODY

``` json
{

  "error": 0,
  "description": "Success",
  "url": "http://192.168.0.227/game/index_3.html?token=af7f54f4-cd53-4c94-92eb-5de9cca86a47"
}
```

