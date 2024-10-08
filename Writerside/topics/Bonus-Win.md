# Bonus Win

Using this method a Lucky Monaco system will send to Casino Operator winning result of all rounds played on Free Round
Bonus. Casino Operator will change a player balance in appliance with this request and will return an updated balance.

Important:The call is idempotent, i.e. sending result again with the same reference number creates only one
transaction.


## Requested by LuckyMonaco

### Parameters

| Name       | Data Type | Description                                                                 | Required |
|:-----------|:---------:|:----------------------------------------------------------------------------|----------|
| hash       |  string   | Hash code of the request                                                    | Required |
| userid     |  string   | Player's ID, specified by Partner when creating a game session.             | Required |
| gameId     |  string   | Id of the game.                                                             | Required |
| roundId    |  string   | Id of the round.                                                            | Required |
| amount     |  decimal  | Amount of the bet.                                                          | Required |
| reference  |  string   | Unique reference of this transaction.                                       | Required |
| providerId |  string   | Game Provider id.                                                           | Required |
| timestamp  |  string   | Date and time when the transaction is processed on the Lucky Monaco side    | Required |
| bonusCode  |  string   |  Id of the bonus in Casino Operator system.                   | Optional |
| platform   |  string   | The platform type (channel) on which the game is played.                    | Optional |
| roundId    |  string   | Id of the last played round in Free Round Bonus                 | Optional |
| token      |  string   | Token of the player from Authenticate response.                             | Optional |


### Example of URL

``` http
https://<Partner website(Domain)/bonuswin?authToken=<TOKEN>
```

### Example of HTTP BODY

``` json
{
    "reference": "585c1306f89c56f5ecfc2f5d",
    "gameId": "Im_60_tumblefortune",
    "amount": 1.0,
    "providerId": "luckymonaco",
    "userId": "421",
    "hash": "4a5d375ac1311b04fba2ea66d067b8e5"
    "timestamp": "1482429190374"
}
```

## Response from partner(s)

### Parameters 2

| Name          |Data Type| Description                                                                                                                                                                                                                                                                                                                               | Required |
|:--------------|:---:|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----|
| transactionId |string| Id of the transaction in wallet.                                                                                                                                                                                                                                                                                                          | Required |
| currency      |string| Currency of the player. | Required |
| cash          |decimal| Currency of the player.                                                                                                                                                                                                                                                                                                                   | Required |
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
