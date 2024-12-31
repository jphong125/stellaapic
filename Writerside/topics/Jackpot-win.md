# Jackpot Win (Reserved for future development)

## Overview
Using this method a Pragmatic Play system will notify Casino Operator about Jackpot winning. Operator should handle the transaction in their system and send the jackpot win transaction id back to the Lucky Monaco.

Important: The call is idempotent, i.e. sending result again with the same reference number creates only one transaction. For retries actual player's balance should be returned.

Important: Please pay attention that in slot Jackpots, progressive and non-progressive wins are sent together inside the amount field in jackpotWin method.
Lucky Monaco pays just progressive wins to operator. To receive info on progressive and non-progressive win parts separately, Operator can ask the Lucky Monaco Technical Support to enable optional parameter jackpotDetails in jackpotWin request
In this case jackpotDetails will be sent like this progressive:XX, non-progressive:YY For example: amount: 150 jackpotDetails: progressive: 100, non-progressive:50

## Request

Requested "Jackpot win" API URL will be notified individually, for security reasons.

### Request Parameters

| Name             | Data Type | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                | Remark  |
|:-----------------|:---------:|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------|
| uuid             |string| A unique ID for each request.                                                                                                                                                                                                                                                                                                                                                                                                                              | Required |
| providerId       |  string   | Game Provider id.                                                                                                                                                                                                                                                                                                                                                                                                                                          | Required |
| timestamp        |  string   | Date and time when the transaction is processed on the Lucky Monaco side.                                                                                                                                                                                                                                                                                                                                                                                  | Required |
| userId           |  string   | User's ID, specified by Partner when creating a game session.                                                                                                                                                                                                                                                                                                                                                                                              | Required |
| gameId           |  string   | Id of the game.                                                                                                                                                                                                                                                                                                                                                                                                                                            | Required |
| roundId          |  string   | Id of the round.                                                                                                                                                                                                                                                                                                                                                                                                                                           | Required |
| jackpotId        |  string   | Id of the jackpot.                                                                                                                                                                                                                                                                                                                                                                                                                                         | Required |
| jackpotDetails   |  string   | Detailed information about the won jackpots in the round. <br/> Example : "{"progressive":130.34375, "non-progressive":3125.0}"                                                                                                                                                                                                                                                                                                                            | Optional |
| amount           |  decimal  | Total amount of all jackpot winnings in the round.                                                                                                                                                                                                                                                                                                                                                                                                         | Required |
| reference        |  string   | Unique reference of this transaction.                                                                                                                                                                                                                                                                                                                                                                                                                      | Required | 
| platform         |  string   | The platform type (channel) on which the game is played.                                                                                                                                                                                                                                                                                                                                                                                                   | Optional |
| sessionId        |  string   | User’s game session id on Lucky Monaco system.                                                                                                                                                                                                                                                                                                                                                                                                             | Optional |
| balanceBeforeWin |  string   | balanceBeforeWin is calculated either by won tier only or by all JP tiers	Optional depending on the option selected. <br/>  Options list: <br/> -calculation by tier <br/> balanceBeforeWin = winning amount of the won tier (including progressive and community wins) <br/> -Calculation by JP <br/> balanceBeforeWin = sum of balances of all tiers (except WON) + winning amount of the won tier (including progressive and community wins, except JP baby) | Optional |
| instanceId       |  string   | Instance id of the won tier. The first instance starts from the "1" identifier.<br/> If several brands or operators participate in the same jackpot, instance is incremented globally per jackpot, not individually per brand or operator.                                                                                                                                                                                                                       | Optional |

### Examples

METHOD

``` http
POST
```

URL

``` http
https://<API URL>/v4/JackPotWin
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
    "roundId" : "5103188801",
    "uuid": "4a5d375ac1311b04fba2ea66d067b8e5",
    "timestamp": "1482429190374",
    "sessionId": "<sid>"
}
```

## Response

Example of successful response from Partner API servers.

### Response Parameters 

| Name          |Data Type| Description                                          | Remark  |
|:--------------|:---:|:-----------------------------------------------------|-----|
| transactionId |string| Id of the transaction within Casino Operator system. | Required |
| currency      |string| Currency of the player.                              | Required |
| cash          |decimal| Real balance of the player.                          | Required |
| bonus         |decimal| Bonus balance of the player.                         | Required |
| error  |  string   | Code of error.                                       | Required |
| description |string| Response status short description.                   | Required |

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
