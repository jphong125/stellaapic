# Get Played Games

## Overview
Using this method Casino Operator can get a list of the games played by the player during the day.

## API URL
Requested "Get Played Game" API URL will be notified individually, for security reasons.

### Parameters

| Name        |Data Type| Description                                                 | Remark   |
|:------------|:---:|:------------------------------------------------------------|----------|
| secureLogin |string| User name for authentication in the Casino Game API service | Required |
| playerId    |string| Id of the player within the Operator system.                | Required |
| dateplayed  |string| Date, based on the time zone of the user.                   | Required |
| timeZone    |string| Time zone of the user. Example: GMT, GMT+8, GMT+04:00                                     | Required |
| uuid                |  string   | A unique ID for each request                                             | Required |
| token      |string| Token of the player from Authenticate response              | Required |

### Examples

METHOD

``` http
POST
```


URL

``` http
https://<API URL>/GetPlayedGame
```
HEADER

``` http
Content-Type: application/json
```

### Example of HTTP BODY

``` json
{
    "secureLogin": "<partnerId>",
    "playerId": "421",
    "datePlayed": :2016-12-23",
    "timeZone": "GMT+00:00",
    "uuid": "980d06d3361f1e21a2f1550c6806ef52"
}
```

## Response from partner

### Parameters 2

| Name                       | Object      | Data Type | Description                                                                                                                   | Required |
|:----------------------------|-------------|:---------:|:------------------------------------------------------------------------------------------------------------------------------|---|
| error |             |string|                                                                                                    | Required |
| description |             |string| Description of the error for troubleshooting.                                                                                                                                                                                                                                                                                                        | Required |
| games List of games played |             |   array   | See below GamePlayed type description of the objects in the list.                                                                          | Required |
|                             | gameId      |  string   | Symbolic unique identifier of the game.                                                                                                   |  Required |
|                             | gameName    |  string   | Name of the game. |  Required |
|                             | balance     |  string   | Player’s balance after successful transaction                                                                                 |  Required |
|                             | error       |  string   | Error code.                                                                                                                   |  Required |
|                             | description |  string   | Description of the error for troubleshooting.                                                                                 |  Required |



### Example of HTTP BODY 2

``` json
{
    "error": "0",
    "description": "OK",
    "games": [
                {
                 "gameId": "Im_14_childofsuccess",
                 "gameName": "Child of success" },
                {
                 "gameId": "Im_60_tumblefortune",
                 "gameName": "tumblefortune" }
]
}
