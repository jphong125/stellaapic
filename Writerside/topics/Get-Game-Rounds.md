# Get Game Rounds

## Overview
Using this method Casino Operator can get a list of the game rounds played by the player or operator during the certain day.
If you do not specify an option value, all play data for the partner's specified search time will be displayed.
The option values are userId and gameId, and the two option values are "and" conditions.
Therefore, you can adjust the option values according to your partner's needs to see the desired results.

## Request
Requested get game round API URL will be notified individually, for security reasons.

### Request Parameters

| Name        |Data Type| Description                                                    | Remark |
|:------------|:---:|:---------------------------------------------------------------|--------|
| secureLogin |string| Partner name for authentication in the Casino Game API service | Required |
| userId      |string| Id of the user within the Operator system.                     | Optional |
| gameId      |  string   | ID of the game.                                                | Optional       |
| dateStart   |string| Date to start, based on the time zone of the user.             | Required |
| dateEnd     |string| Date to end, based on the time zone of the user.               | Required |
| timeZone    |string| Time zone of the user. Example: GMT, GMT+8, GMT+04:00          | Required |
| page        |string| Page number (default value 1)                                  | Required |
| limit       |string| row per page (max 1000)                                        | Required |
| uuid        |  string   | A unique ID for each request                                   | Required |
| token       |string| Token of the Partner from Authenticate response                | Required |

### Examples

METHOD

``` http
POST
```

URL

``` http
https://<API URL>/history/GetGameRounds
```

HEADER

``` http
Content-Type: application/json
```

### Example of HTTP BODY

``` json

{
    "secureLogin" : "S100",
    "token" : "fSYFZMScpZ01FhR26r59GexREh1xHgEY",
    "userId": "hwa10",
    "gameId": "lm_13_wildkelly",
    "dateStart": "2024-10-21 00:00:01",
    "dateEnd": "2024-10-24 23:00:00",
    "timeZone": "GMT+09:00",
    "page" : 1,
    "limit" : 10,
    "uuid": "980d06d3361f1e21a2f1550c6806ef52"
}
```

## Response

Example of successful response from LuckyMonaco API servers.

### Response Parameters

| Name                              | Object       | Data Type | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 | Remark  |
|:----------------------------------|--------------|:---------:|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------|
| error                             |              |  string   | Error code                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  | Required |
| description                       |              |  string   | Description of the error for troubleshooting.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               | Required |
| total round                       |              |  string   | Total rounds searched                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       | Required |
| rounds List of game rounds played |              |  string   | See below GamePlayed type description of the objects in the list.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           | Required |
|                                   | dateTime     | datetime  | Date and time when the round was played, based on time zone of the user. The value is returned in Lucky Monaco’s server time zone (UTC/GMT+0).                                                                                                                                                                                                                                                                                                                                                                                                                                              | Required |
|                                   | gameId       |  string   | Symbolic unique identifier of the game.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     | Required |
|                                   | gameName     |  string   | Name of the game.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           | Required |
|                                   | roundId      |  string   | Unique identifier of the game round.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        | Required |
|                                   | currency     |  string   | User’s currency.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            | Required |
|                                   | betAmount    |  string   | Bet amount.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 | Required |
|                                   | winAmount    |  string   | Win amount.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 | Required |
|                                   | balance      |  string   | User’s balance after successful transaction                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 | Required |
|                                   | uerId        |  string   | Unique id for player on the Lucky Monaco side.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | Required |
|                                   |roundDetails |   array   | Additional information about the current game round. <br/>**If the result is 0, the result value is not displayed.** <br/> **If there are multiple wins, the win type and amount for each are displayed.**  <br/> "bet" : "type of bet" (i.e. "spin" or "BuyFreeSpin")<br/> "type of result" (i.e. "winspin", "minigame", "freespin") : "win amount" (i.e "10.0")                                                                                                                                                                                                                                                                                                            | Required |
|                                   |roundStatus  |string| Status of the game round <br/>o InProgress – game round was started but not finished yet by the user <br/>o Completed – game round has been completed by the user<br/>o Cancelled – game round has been closed automatically by the game round finalization process<br/>o CompleteInProcess – game round is marked as Completed in the db; BetResult or EndRound requests is in asynchronous transaction queue and the system tries to send it to Operator<br/>o CancelInProcess – game round is marked as Cancelled in the db; Refund is in asynchronous queue and being sent to Operator. | Required |

### Example of Json BODY

``` json
{

  "error": 0,
  "description": "Success",
  "totalRounds": 5,
  "rounds": [

    {

      "dateTime": "2024-10-24 02:59:20",
      "gameId": "lm_13_wildkelly",
      "gameName": "WILD Kelly",
      "roundId": 1602530,
      "userId": "hwa10",
      "currency": "USD",
      "betAmount": "7.2",
      "winAmount": "0",
      "balance": "0.16",
      "roundStatus": "Completed",
      "roundDetails": {

        "spin": "BuyFreeSpin"
      }
    },
    {

      "dateTime": "2024-10-24 02:59:06",
      "gameId": "lm_13_wildkelly",
      "gameName": "WILD Kelly",
      "roundId": 1602529,
      "userId": "hwa10",
      "currency": "USD",
      "betAmount": "0.09",
      "winAmount": "0.15",
      "balance": "7.36",
      "roundStatus": "Completed",
      "roundDetails": {

        "spin": "Spin",
        "winSpin": "0.15"
      }
    },
    {

      "dateTime": "2024-10-24 02:58:54",
      "gameId": "lm_13_wildkelly",
      "gameName": "WILD Kelly",
      "roundId": 1602527,
      "userId": "hwa10",
      "currency": "USD",
      "betAmount": "0.9",
      "winAmount": "0",
      "balance": "7.3",
      "roundStatus": "Completed",
      "roundDetails": {

        "spin": "Spin"
      }
    },
    {

      "dateTime": "2024-10-24 02:58:40",
      "gameId": "lm_13_wildkelly",
      "gameName": "WILD Kelly",
      "roundId": 1602526,
      "userId": "hwa10",
      "currency": "USD",
      "betAmount": "0.9",
      "winAmount": "0",
      "balance": "8.2",
      "roundStatus": "Completed",
      "roundDetails": {

        "spin": "Spin"
      }
    },
    {

      "dateTime": "2024-10-24 02:58:21",
      "gameId": "lm_13_wildkelly",
      "gameName": "WILD Kelly",
      "roundId": 1602525,
      "userId": "hwa10",
      "currency": "USD",
      "betAmount": "0.9",
      "winAmount": "0",
      "balance": "9.1",
      "roundStatus": "Completed",
      "roundDetails": {

        "spin": "Spin"
      }
    },
    {

      "dateTime": "2024-10-24 02:58:40",
      "gameId": "lm_13_wildkelly",
      "gameName": "WILD Kelly",
      "roundId": 1602526,
      "userId": "hwa10",
      "currency": "USD",
      "betAmount": "0.9",
      "winAmount": "0",
      "balance": "8.2",
      "roundStatus": "Completed",
      "roundDetails": {

        "spin": "Spin"
      }
    },
  ]
}
```