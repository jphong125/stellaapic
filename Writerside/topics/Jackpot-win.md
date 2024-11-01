# Jackpot Win (Reserved for future development)

## Overview
Using this method a Lucky Monaco system will notify Casino Operator about Jackpot winning. <br/>Notification is asynchronous
and may come to the operator with a short delay after game round is over. <br/>Operator should handle the transaction in their
system and send the jackpot win transaction id back to the Lucky Monaco.

Important : The call is idempotent, i.e. sending result again with the same reference number creates only one
transaction.

## Request

Requested "Jackpot win" API URL will be notified individually, for security reasons.

### Request Parameters

| Name       | Data Type | Description                                                               | Remark  |
|:-----------|:---------:|:--------------------------------------------------------------------------|----------|
| uuid       |string| A unique ID for each request.                                             | Required |
| userId     |  string   | User's ID, specified by Partner when creating a game session.             | Required |
| gameId     |  string   | Id of the game.                                                           | Required |
| roundId    |  string   | Id of the round.                                                          | Required |
| amount     |  decimal  | Amount of the bet.                                                        | Required |
| reference  |  string   | Unique reference of this transaction.                                     | Required |
| providerId |  string   | Game Provider id.                                                         | Required |
| timestamp  |  string   | Date and time when the transaction is processed on the Lucky Monaco side. | Required |
| jackpotId  |  string   | Id of the jackpot.                                                        | Required | 
| platform   |  string   | The platform type (channel) on which the game is played.                  | Optional |
| sessionId        |  string   | User’s game session id on Lucky Monaco system.                            | Optional |

### Examples

METHOD

``` http
POST
```

URL

``` http
https://<API URL>/V4/JackPotWin
```
HEADER

``` http
Content-Type: application/json
```

### Example of HTTP BODY

``` json
{
    "reference": "585c1306f89c56f5ecfc2f5d",
    "gameId": "Im_60_tumblefortune",
    "amount": 55.0,
    "jackpotId": "568",
    "providerId": "luckymonaco",
    "userId": "421",
    "roundid" : "5103188801",
    "uuid": "4a5d375ac1311b04fba2ea66d067b8e5",
    "timestamp": "1482429190374",
    "sessionid": "<sid>"
}
```

## Response

Example of successful response from Partner API servers.

### Response Parameters 

| Name          |Data Type| Description                                          | Remark  |
|:--------------|:---:|:-----------------------------------------------------|-----|
| TransactionId |string| Id of the transaction within Casino Operator system. | Required |
| currency      |string| Currency of the player.                              | Required |
| cash          |decimal| Real balance of the player.                          | Required |
| bonus         |decimal| Bonus balance of the player.                         | Required |
| error  |  string   | Code of error.                                       | Required |
| description |string| Response status short description.                   | Optional |

### Example of Json BODY

``` json
{
 "transactionId": "<transactiondId>",
 "currency": "USD",
 "cash": "99899.99",
 "bonus": "99.99",
 "error": 0,
 "description": "Success"
 }

```
