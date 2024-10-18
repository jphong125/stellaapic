# Get Bet History

## Overview
Using this method Casino Operator can get a list of the game rounds played by the Partner during the certain day and (optionally) the specific hour.

## Request
Requested get game round API URL will be notified individually, for security reasons.

### Request Parameters

| Name        | Data Type | Description                                                                                                | Remark   |
|:------------|:---------:|:-----------------------------------------------------------------------------------------------------------|----------|
| secureLogin |  string   | User name for authentication in the Casino Game API service                                                | Required |
| startTime   | Datetime  | start time to report. i.e. 2014-10-11 00:00:00                                                             | Required |
| endTime     | Datetime  | End time to report. i.e. 2014-10-11 23:59:59                                                                | Required |
| rows        | interger  | Row per page. (deafalt 100, max 1000)                                                                      | Required |
| gameType    |  string   | Type of game portfolio (i.e. "RNG" : Main Portfolio games (video slots, etc), "lc" : Live Casino portfolio | Required |
| time        | interger  | 1= updated time, 2 = bet time                                                                              | Required |
| token       |  string   | Token of the player from Authenticate response                                                             | Required |

### Examples

METHOD

``` http
POST
```

URL

``` http
https://<API URL>/Getbethistory
```

HEADER

``` http
Content-Type: application/json
```

### Example of HTTP BODY

``` json
{
    "secureLogin": "<partnerId>",
    "starttime": "2016-12-23 00:00:00",
    "endtime": "2016-12-23 23:59:59",
    "row": "500",
    "gameType": ["RNG", "lc"],
    "time" : : "1"
    "token": "980d06d3361f1e21a2f1550c6806ef52"
}
```

## Response

Example of successful response from LuckyMonaco API servers.

### Response Parameters

| Name                              | Object       | Data Type | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 | Remark  |
|:----------------------------------|--------------|:---------:|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------|
| error                             |              |  string   |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             | Required |
| description                       |              |  string   | Description of the error for troubleshooting.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               | Required |
| total                             |              |  string   | Total number of rounds in the viewed periods                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                | Required |
| page                              |              |  string   | Total number of page in the viewed periods                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  | Required |
| rounds List of game rounds played |              |   array   | See below GamePlayed type description of the objects in the list.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           | Required |
|                                   | reportDate   | dateTime  | Date the report was requested, based on time zone of the user. The value is returned in Lucky Monaco’s server time zone (UTC/GMT+0).                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        | Required |
|                                   | gameTime     |  string   | Date and time when the round was played, based on time zone of the user. The value is returned in Lucky Monaco’s server time zone (UTC/GMT+0).                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | Required |
|                                   | gameId       |  string   | Symbolic unique identifier of the game.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     | Required |
|                                   | gameName     |  string   | Name of the game.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           | Required |
|                                   | gameType     |  string   | Type of game portfolio (i.e. "RNG" : Main Portfolio games (video slots, etc), "lc" : Live Casino portfolio                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  | Required |
|                                   | roundId      |  string   | Unique identifier of the game round.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        | Required |
|                                   | currency     |  string   | Player’s currency.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          | Required |
|                                   | betAmount    |  string   | Bet amount.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 | Required |
|                                   | winAmount    |  string   | Win amount.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 | Required |
|                                   | valid        |  string   | Changes in balance due to round results. (i.e. "win amount" - "bet amount")                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  | Required |
|                                   | balance      |  string   | Player’s balance after successful transaction                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               | Required |
|                                   | roundDatails |  string   | Additional information about the game round, such as “Free spin”, “Bonus”, etc.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             | Optional |
|                                   | userId       |  string   | Unique id for player on the Lucky Monaco side.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | Required |
|                                   | detailsUrl   |  string   | This parameter is not currently used and should be ignored by operators                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     | Required |



### Example of Json BODY

``` json
{
    "error": "0",
    "description": "success", 
    "total" : 100
    "page" : 1
    "rounds":
    [
    {
     "reportdate": "2024-10-10", 
     "gametime": "2024-10-10 01:11:22",
     "gameId": "Im_treasureofzeus",  -
     "gameName": "treasureofzeus",  - 
     "gameType": "RNG",  -
     "roundId": "5108924498",   -
     "currency": "USD",    -
     "betAmount": "0.1",    -
     "winAmount": "0.05",   -
     "valid" : "-0.05"   -
     "balance": "99711.59",    -
     "roundDetails": "spin", 
     "userId": "6638030",
     "detailsUrl": "url": "URL where you can check the snapshot"
}
,…,
```