# Result

## Overview
Using this method the Lucky Monaco system will send to Casino Operator the winning result of a bet. **The Casino Operator
will change the balance of the player in accordance with this request and return the updated balance.**

Result request may contain a prize that the player is awarded with during the game round, if there is an active promotional 
campaigns like PrizeDrop. Parameters related to the PrizeDropprizes are optional and should be configured by
Lucky Monaco team based on Operator’s request.

Important:The call is idempotent, i.e. sending result again with the same reference number creates only one
transaction.

## API URL

Requested result API URL will be notified individually, for security reasons.

### Parameters

| Name              | Data Type | Description                                                                 | Required |
|:------------------|:---------:|:----------------------------------------------------------------------------|----------|
| uuid                |string| A unique ID for each request                                                                                                           | Required |
| userId            |  string   | Player's ID, specified by Partner when creating a game session.             | Required |
| gameId            |  string   | Id of the game.                                                             | Required |
| roundId           |  string   | Id of the round.                                                            | Required |
| amount            |  decimal  | Amount of the bet.                                                          | Required |
| reference         |  string   | Unique reference of this transaction.                                       | Required |
|currency|string| Currency of the player                                       | Required |
| providerId        |  string   | Game Provider id.                                                           | Required |
| timestamp         |  string   | Date and time when the transaction is processed on the Lucky Monaco side    | Required |
| roundDetails      |  string   | Additional information about the currentgame round.                         | Required |
| sessionId        |string| Player’s game session id on Lucky Monaco system.                       | Required |


### Parameters 2 (Reserved for future development)

|Name|Data Type| Description                                                  | Remark   |
|:---|:---:|:-------------------------------------------------------------|----------|
| bonusCode         |  string   | Id of the bonus in Casino Operator system.                                  | Optional |
| promoWinAmount    |  string   | Prize amount that the player is awarded with during a promotional campaign. | Optional |
| promoWinReference |  string   | Unique reference of this transaction.                                       | Optional |
| promoCampaignID   |  string   | Id of the promotional campaign.                                             | Optional |
| promoCampaignType |  string   | Type of the promotional campaign.                                             | Optional |

### Example of URL

``` http
https://<API URL>/V4/Result
```

### Example of HTTP BODY

``` json
{
    "providerId": "luckymonaco",
    "userId": "421",
    "sessionId": "sid"
    "currency": "USD",
    "amount": 10.0,
    "roundDetails": "spin",
    "roundid" : "5103188801"
    "reference": "585c1306f89c56f5ecfc2f5d",
    "gameId": "Im_60_tumblefortune",
    "uuid": "4a5d375ac1311b04fba2ea66d067b8e5",
    "timestamp": "1482429190374"
}
```

## Response from partner(s)

### Parameters 3

| Name          |Data Type| Description                                                                                                                                                                                                                                                                                                                               | Required |
|:--------------|:---:|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----|
| transactionId |string| Id of the transaction in wallet.                                                                                                                                                                                                                                                                                                          | Required |
| currency      |string| Currency of the player. | Required |
| cash          |decimal| Currency of the player.                                                                                                                                                                                                                                                                                                                   | Required |


### Parameters 4 (Reserved for future development)

|Name|Data Type| Description                                                  | Remark   |
|:---|:---:|:-------------------------------------------------------------|----------|
| bonus         |decimal| Bonus balance of the player.                                                                                                                                                                                                                                                                                                               | Required |

### Example of HTTP BODY 2

``` json
{
 "transactionId": 1482429190474,
 "currency": "USD",
 "cash": 99899.99,
 "bonus": 99.99,
 "error": 0,
 "description": "Success"
 }

```
