# Get Game Rounds

## Overview
Using this method Casino Operator can get a list of the game rounds played by the player during the certain day and (optionally) the specific hour.

## API URL
Requested get game round API URL will be notified individually, for security reasons.

### Parameters

| Name        |Data Type| Description                                                 | Remark   |
|:------------|:---:|:------------------------------------------------------------|----------|
| secureLogin |string| User name for authentication in the Casino Game API service | Required |
| playerId    |string| Id of the player within the Operator system.                | Required |
| dateplayed  |string| Date, based on the time zone of the user.                   | Required |
| timeZone    |string| Time zone of the user. Example: GMT, GMT+8, GMT+04:00                                     | Required |
| gameId      |string| Symbolic unique identifier of the game.                | Required |
| hour        |string| A number of hour then rounds were played (optional)                | Required |
| token      |string| Token of the player from Authenticate response                                                                                                                                            | Required |

### Example of URL

``` http
https://<API URL>/GetGameRounds
```

### Example of HTTP BODY

``` json
{
    "secureLogin": "username"
    "playerId": "421"
    "datePlayed": :2016-12-23"
    "timeZone": "GMT+00:00"
    "playerId": "Im_2_kellywheeldouble"
    "hour": 10
    "token": "980d06d3361f1e21a2f1550c6806ef52"
}
```

## Response from partner

### Parameters 2

| Name                       | Object       |  Data Type  | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 | Required |
|:----------------------------|--------------|:-----------:|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---|
| rounds List of game rounds played |              |   string    | See below GamePlayed type description of the objects in the list.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           | Required |
|                             | dateTime     |string| Date and time when the round was played, based on time zone of the user. The value is returned in Lucky Monaco’s server time zone (UTC/GMT+0).                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |  Required |
|                             | gameId       |string| Symbolic unique identifier of the game.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |  Required |
|                             | gameName     |  string   | Name of the game.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |  Required |
|                             | roundId      |  string   | Unique identifier of the game round.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |  Required |
|                             | currency     |  string   | Player’s currency.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |  Required |
|                             | betAmount    |  string   | Bet amount.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |  Required |
|                             | winAmount    |  string   | Win amount.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |  Required |
|                             | balance      |  string   | Player’s balance after successful transaction                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |  Required |
|                             | roundDatails |  string   | Additional information about the game round, such as “Free spin”, “Bonus”, etc.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |  Required |
|                             | playerid     |  string   | Unique id for player on the Lucky Monaco side.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |  Required |
|                             | securelogin  |  string   | Unique id for brand on the Lucky Monaco side.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |  Required |
|                             | detailsUrl   |  string   | This parameter is not currently used and should be ignored by operators                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |  Required |
|                             | roundstatus  |  string   | Status of the game round. May have the following values:<br/>-In progress : game round was started but not finished yet by the player<br/>-Completed : game round has been completed by the player<br/>-Cancelled : game round has been closed automatically by the game round finalization process<br/>-CompleteInProcess : game round is marked as Completed in the db; BetResult or EndRound requests is in asynchronous transaction queue and the system tries to send it to Operator <br/>-CancelInProcess : game round is marked as Cancelled in the db; Refund is in asynchronous queue  and being sent to Operator. | Required     |
|                             | error        |  string   | Error code.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |  Required |
|                             | description  |  string   | Description of the error for troubleshooting.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |  Required |



### Example of HTTP BODY 2

``` json
{
    "error": "0",
    "description": "OK", "rounds":
    [
    {
     "dateTime": "2016-12-23 05:50:35.0", 
     "gameId": "Im_treasureofzeus",
     "gameName": "treasureofzeus", 
     "roundId": "5108924498",
     "currency": "USD",
     "betAmount": "0.1",
     "winAmount": "0.05",
     "balance": "99711.59",
     "roundDetails": "spin", 
     "playerid": 6638030,
     "detailsUrl": "url": "URL where you can check the snapshot"
}
,…,
{
     "dateTime": "2016-12-23 05:54:28.0", 
     "gameId": "Im_treasureofzeus",
     "gameName": "treasureofzeus",
     "roundId": "5108946371",
     "currency": "USD",
     "betAmount": "2.5",
     "winAmount": "0.0",
     "balance": "99710.04",
     "roundDetails": null,
     "playerid": 6638030,
     "detailsUrl": "url": "URL where you can check the snapshot"
      }
]
}
```