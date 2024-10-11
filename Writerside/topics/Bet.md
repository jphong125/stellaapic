# Bet

## Overview
Using this method Lucky Monaco system will check the player balance on Casino Operator side to ensure they still have the
funds to cover the bet. Amount of the bet must be subtracted from player balance in Casino Operator system.

Important: The call is idempotent, i.e. sending bet again only creates one transaction.

## API URL

Requested bet API URL will be notified individually, for security reasons.

### Parameters

| Name                  | Data Type | Description                                                              | Required |
|:----------------------|:---------:|:-------------------------------------------------------------------------|----------|
| hash                  |  string   | Hash code of the request                                                 | Required |
|userid               |  string   | Player's ID, specified by Partner when creating a game session.          | Required |
| gameId               |  string   | Id of the game.                                                          | Required |
|  roundId  |  string   | Id of the round.                                                         | Required |
| amount  |  decimal  | Amount of the bet.                                                       | Required |
| reference             |  string   | Unique reference of this transaction.                                    | Required |
| providerId                |  string   | Game Provider id.                                                        | Required |
|  timestamp           |  string   | Date and time when the transaction is processed on the Lucky Monaco side | Required |
|  roundDetails        |  string   | Additional information about the currentgame round.                                      | Required |
| bonusCode             |  string   |  Id of the bonus in Casino Operator system.                                            | Optional |              
| platform    |  string   | The platform type (channel) on which the game is played.                                              | Optional |
| language                  |  string   | Language on which the game was opened.                                            | Optional |
|  jackpotContribution                 |  string   | Amount of the contribution tothe jackpot. If there is a multi-tier jackpot, contain the total amount of contributions to all jackpots.                                            | Optional |
|   jackpotDetails                 |  string   | Amounts of the contribution for multi-tierjackpot, separated by tiers.                                             | Optional |
|    jackpotId                 |  string   |  Id of the active jackpot to contribute.                                          | Optional |
|    token                 |  string   |  Token of the player from Authenticate response.                                         | Optional |
|     ipAddress                  |  string   |   IP address of the player.                                         | Optional |

### Example of URL

``` http
https://<Partner website(Domain)/Bet?authToken=<TOKEN>
```

### Example of HTTP BODY

``` json
{
    "roundDetails": "spin",
    "reference": "585c1306f89c56f5ecfc2f5d",
    "gameId": "Im_60_tumblefortune",
    "amount": 100,
    "providerId": "luckymonaco",
    "userid": "421",
    "roundid" : "5103188801"
    "hash": "4a5d375ac1311b04fba2ea66d067b8e5"
    "timestamp": "1482429190374"
}
```

## Response from partner(s)

### Parameters 2

| Name         |Data Type| Description                                                                                                                                                                                                                                                                                                                               | Required |
|:-------------|:---:|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----|
| transactionId|string| Id of the transaction in wallet.                                                                                                                                                                                                                                                                                                          | Required |
| cash         |decimal| Currency of the player.                                                                                                                                                                                                                                                                                                                   | Required |
| bonus        |decimal| Bonus balance of the player.                                                                                                                                                                                                                                                                                                               | Required |
| usedPromo    |decimal| Amount was used from the bonus balance. | Required |

### Example of HTTP BODY 2

``` json
{
 "transactionId": 1482429190474,
 "currency": "USD",
 "cash": 99899.99,
 "bonus": 99.99,
 "usedPromo": 0,
 "error": 0,
 "description": "Success"
 }

```
