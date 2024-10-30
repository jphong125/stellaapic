# Bet

## Overview
Using this method Lucky Monaco system will check the player balance on Casino Operator side to ensure they still have the
funds to cover the bet.<br/> **Amount of the bet must be subtracted from player balance in Casino Operator system.**

Important: The call is idempotent, i.e. sending bet again only creates one transaction.

## Request

Requested "Bet" API URL will be notified individually, for security reasons.

### Request Parameters

| Name         | Data Type | Description                                                                       | Remark   |
|:-------------|:---------:|:----------------------------------------------------------------------------------|----------|
| uuid         |string| A unique ID for each request                                                      | Required |
| userId       |  string   | User's ID, specified by Operator when creating a game session.                    | Required |
| gameId       |  string   | ID of the game.                                                                   | Required |
| gameName     |  string   | name of the game.                                                                 | Required |
| roundId      |  string   | ID of the round.                                                                  | Required |
| amount       |  decimal  | Amount of the bet.                                                                | Required |
| reference    |  string   | Unique reference of this transaction.                                             | Required |
| sessionId    |string| User’s game session id on Lucky Monaco system.                                    | Required |
| providerId   |  string   | Game Provider ID.                                                                 | Required |
| currency     |string| Currency of the User                                                              | Required |
| timeStamp    |  string   | Date and time when the transaction is processed on the Lucky Monaco system.       | Required |
| roundDetails |  string   | Additional information about the current game round. (i.e. "spin", "buyFreeSpin") | Required |
| sessionId    |string| User’s game session id on Lucky Monaco system.                                    | Required |

### Parameters  (Reserved for future development)

|Name|Data Type| Description                                                                                                                             | Remark   |
|:---|:---:|:----------------------------------------------------------------------------------------------------------------------------------------|----------|
| bonusCode           |  string   | Id of the bonus (i.e. FREE ROUND) in Casino Operator system.                                                                            | Optional |
| jackpotContribution |  string   | Amount of the contribution to the jackpot. If there is a multi-tier jackpot, contain the total amount of contributions to all jackpots. | Optional |
| jackpotDetails      |  string   | Amounts of the contribution for multi-tier jackpot, separated by tiers.                                                                 | Optional |
| jackpotId           |  string   | ID of the active jackpot to contribute.                                                                                                 | Optional |

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
    "sessionId": "<sessionId>",
    "currency": "USD",
    "amount": "100", 
    "roundDetails": "spin",
    "reference": "585c1306f89c56f5ecfc2f5d",
    "gameId": "Im_60_tumblefortune",  
    "gameName": "tumblefortune",
    "roundId" : "5103188801",
    "uuid": "4a5d375ac1311b04fba2ea66d067b8e5",
    "timeStamp": "1482429190374"
}
```

## Response

Example of successful response from Partner API servers.

### Response Parameters

| Name         |Data Type| Description                        | Remark  |
|:-------------|:---:|:-----------------------------------|-----|
| transactionId|string| ID of the transaction in wallet.   | Required |
| cash         |decimal| Real balance of the player.        | Required |
| error  |  string   | code of error.                     | Required |
| description |string| Response status short description. | Optional |

### Response Parameters  (Reserved for future development)

|Name|Data Type| Description                | Remark   |
|:---|:---:|:---------------------------|----------|
| bonus        |decimal| Bonus balance of the User. | Required |

### Example of Json BODY

``` json
{
 "transactionId": "<transactionId>",
 "currency": "USD",
 "cash": "99899.99",
 "error": 0,
 "description": "Success"
 }

```
