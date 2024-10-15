# Bonus Win (Reserved for future development)

## Overview

Using this method a Lucky Monaco system will send to Casino Operator winning result of all rounds played on Free Round
Bonus. **Casino Operator will change a player balance in appliance with this request and will return an updated balance.**

Important : The call is idempotent, i.e. sending result again with the same reference number creates only one
transaction.


## API URL

Requested "Bonus win" API URL will be notified individually, for security reasons.

### Parameters

| Name       | Data Type | Description                                                                 | Required |
|:-----------|:---------:|:----------------------------------------------------------------------------|----------|
| uuid       |string| A unique ID for each request                                                                                                                                              | Required |
| userId     |  string   | Player's ID, specified by Partner when creating a game session.             | Required |
| gameId     |  string   | Id of the game.                                                             | Required |
| roundId    |  string   | Id of the round.                                                            | Required |
| amount     |  decimal  | Amount of the bet.                                                          | Required |
| reference  |  string   | Unique reference of this transaction.                                       | Required |
| providerId |  string   | Game Provider id.                                                           | Required |
| timestamp  |  string   | Date and time when the transaction is processed on the Lucky Monaco side    | Required |
| bonusCode  |  string   |  Id of the bonus in Casino Operator system.                   | Optional |
| platform   |  string   | The platform type (channel) on which the game is played.                    | Optional |
| roundId    |  string   | Id of the last played round in Free Round Bonus                 | Optional |
| sessionId        |string| Player’s game session id on Lucky Monaco system.                       | Required |

### Examples

METHOD

``` http
POST
```

URL

``` http
https://<API URL>/V4/BonusWin
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
    "amount": 1.0,
    "providerId": "Luckymonaco",
    "userId": "421",
    "uuid": "4a5d375ac1311b04fba2ea66d067b8e5"
    "timestamp": "1482429190374",
    "sessionId": "<sessionId>"
}
```

## Response from partner

### Parameters 2

| Name          |Data Type| Description                                                                                                                                                                                                                                                                                                                               | Required |
|:--------------|:---:|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----|
| transactionId |string| Id of the transaction in wallet.                                                                                                                                                                                                                                                                                                          | Required |
| currency      |string| Currency of the player. | Required |
| cash          |decimal| Real balance of the player.                                                                                                                                                                                                                                                                                                        | Required |
| bonus         |decimal| Bonus balance of the player.                                                                                                                                                                                                                                                                                                               | Required |
| eroor  |  string   | code of error                                                   | Required |
| description |decimal| Response status short description. | Optional |

### Example of HTTP BODY 2

``` json
{
 "transactionId": "transactionId",
 "currency": "USD",
 "cash": 99899.99,
 "bonus": 99.99,
 "error": 0,
 "description": "Success"
 }

```
