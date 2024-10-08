# ReFund

Lucky Monaco system may use this method to rollback a bet transaction on the Casino Operator side, in order to reverse
the transaction and adjust player’s balance. 
When receive a Refund request Operator have to return money back to player’s  balance.

- Important: The call is idempotent, i.e. sending refund for existing bet again only creates one transaction.

- Important: If bet transaction is not found then nothing should happen on the Casino Operator side and success (0)
or specific error code for this situation should be returned.

## Requested by LuckyMonaco

### Parameters

| Name           | Data Type | Description                                                                 | Required |
|:---------------|:---------:|:----------------------------------------------------------------------------|----------|
| hash           |  string   | Hash code of the request                                                    | Required |
| userid         |  string   | Player's ID, specified by Partner when creating a game session.             | Required |
| reference      |  string   | Unique reference of this transaction.                                       | Required |
| providerId     |  string   | Game Provider id.                                                           | Required |
| gameId         |  string   | Id of the game.                                                             | Optional |
| roundId        |  string   | Id of the round.                                                            | Optional |
| timestamp      |  string   | Date and time when the transaction is processed on the Lucky Monaco side    | Optional |
| roundDetails   |  string   | Additional information about the currentgame round.                         | Optional |
| amount         |  decimal  | Amount to be refunded.                                                          | Optional |
| bonusCode      |  string   | Id of the bonus in Casino Operator system.                                  | Optional |              
| platform       |  string   | The platform type (channel) on which the game is played.                    | Optional |
| token          |  string   | Token of the player from Authenticate response.                             | Optional |


### Example of URL

``` http
https://<Partner website(Domain)/refund?authToken=<TOKEN>
```

### Example of HTTP BODY

``` json
{
    "reference": "585c1306f89c56f5ecfc2f5d",
    "gameId": "Im_60_tumblefortune",
    "providerId": "luckymonaco",
    "userId": "421",
    "hash": "4a5d375ac1311b04fba2ea66d067b8e5"
}
```

## Response from partner(s)

### Parameters 2

| Name          |Data Type| Description                                                                                                                                                                                                                                                                                                                               | Required |
|:--------------|:---:|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----|
| transactionId |string| Id of the transaction in wallet.                                                                                                                                                                                                                                                                                                          | Required |


### Example of HTTP BODY 2

``` json
{
 "transactionId": "1482429190474",
 "error": "0",
 "description": "Success"
 }

```
