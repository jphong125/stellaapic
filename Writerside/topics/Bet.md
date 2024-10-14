# Bet

## Overview
Using this method Lucky Monaco system will check the player balance on Casino Operator side to ensure they still have the
funds to cover the bet. **Amount of the bet must be subtracted from player balance in Casino Operator system.**

Important: The call is idempotent, i.e. sending bet again only creates one transaction.

## API URL

Requested bet API URL will be notified individually, for security reasons.

### Parameters

| Name         | Data Type | Description                                                                     | Remark   |
|:-------------|:---------:|:--------------------------------------------------------------------------------|----------|
| uuid         |string| A unique ID for each request                                                    | Required |
| userId       |  string   | Player's ID, specified by Partner when creating a game session.                 | Required |
| gameId       |  string   | Id of the game.                                                                 | Required |
| gamename     |  string   | name of the game.                                                               | Required |
| roundId      |  string   | Id of the round.                                                                | Required |
| amount       |  decimal  | Amount of the bet.                                                              | Required |
| reference    |  string   | Unique reference of this transaction.                                           | Required |
| sessionId    |string| Player’s game session id on Lucky Monaco system.                                | Required |
| providerId   |  string   | Game Provider id.                                                               | Required |
| currency     |string| Currency of the player                                                          | Required |
| timeStamp    |  string   | Date and time when the transaction is processed on the Lucky Monaco side        | Required |
| roundDetails |  string   | Additional information about the currentgame round. (ex. "spin", "buyFreeSpin") | Required |
| sessionId        |string| Player’s game session id on Lucky Monaco system.                                                                                       | Required |

### Parameters 2 (Reserved for future development)

|Name|Data Type| Description                                                  | Remark   |
|:---|:---:|:-------------------------------------------------------------|----------|
| bonusCode           |  string   | Id of the bonus in Casino Operator system.                                                                                             | Optional |
| jackpotContribution |  string   | Amount of the contribution tothe jackpot. If there is a multi-tier jackpot, contain the total amount of contributions to all jackpots. | Optional |
| jackpotDetails      |  string   | Amounts of the contribution for multi-tierjackpot, separated by tiers.                                                                 | Optional |
| jackpotId           |  string   | Id of the active jackpot to contribute.                                                                                                | Optional |

### Examples

METHOD

``` http
POST
```

URL

``` http
https://<API URL>/V4/Bet
```
HEADER

``` http
Content-Type: application/json
```

### Example of HTTP BODY

``` json
{
    "providerId": "luckymonaco",
    "userId": "421",
    "sessionId": "<sessionId>"
    "currency": "USD"
    "amount": 100, 
    "roundDetails": "spin",
    "reference": "585c1306f89c56f5ecfc2f5d",
    "gameId": "Im_60_tumblefortune",  
    "gamename": "tumblefortune",
    "roundId" : "5103188801",
    "uuid": "4a5d375ac1311b04fba2ea66d067b8e5",
    "timeStamp": "1482429190374"
}
```

## Response from partner

### Parameters 3

| Name         |Data Type| Description                                                                                                                                                                                                                                                                                                                               | Required |
|:-------------|:---:|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----|
| transactionId|string| Id of the transaction in wallet.                                                                                                                                                                                                                                                                                                          | Required |
| cash         |decimal| Currency of the player.                                                                                                                                                                                                                                                                                                                   | Required |

### Parameters 4 (Reserved for future development)

|Name|Data Type| Description                                                  | Remark   |
|:---|:---:|:-------------------------------------------------------------|----------|
| bonus        |decimal| Bonus balance of the player.           | Required |
| usedPromo    |decimal| Amount was used from the bonus balance. | Required |

### Example of HTTP BODY 2

``` json
{
 "transactionId": "<transactionId>",
 "currency": "USD",
 "cash": 99899.99,
 "error": 0,
 "description": "Success"
 }

```
