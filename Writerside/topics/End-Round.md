# End Round

## Overview
Every time a game round is over, the Lucky Monaco system will call EndRound method, so that Operator can finalize the
game round transactions on their side in real time.

If Operator does not need to finalize transactions in real time it is strongly recommended to disable EndRound
functionality on the Lucky Monaco side. Instead, Data Feed API can be used for transaction finalization, in order
to decrease the number of requests to the Operator system and keep traffic between two systems as light as
possible.

Important: EndRound request may be sent more than once. If the game round is already finalized, Operator
should  ignore the EndRound request and return the success response.


## API URL

Requested promo win API URL will be notified individually, for security reasons.

### Parameters

| Name       | Data Type | Description                                                                | Required |
|:-----------|:---------:|:---------------------------------------------------------------------------|----------|
| uuid       |string| A unique ID for each request                                                                                                                                              | Required |
| userId     |  string   | Player's ID, specified by Partner when creating a game session.            | Required |
| gameId     |  string   | Id of the game.                                                            | Required |
| roundId    |  string   | Id of the round.                                                           | Required |
| providerId |  string   | Game Provider id.                                                          | Required | 
| platform   |  string   | The platform type (channel) on which the game is played.                   | Optional |
| sessionId        |string| Player’s game session id on Lucky Monaco system.                       | Required |
| win        |  string   | Win amount in round. Intended to notify Operator about amount won in round | Optional |


### Example of URL

``` http
https://<API URL>/V4/EndRound
```

### Example of HTTP BODY

``` json
{
    "gameId": "Im_60_tumblefortune",
    "providerId": "luckymonaco",
    "userId": "421",
    "roundid" : "5103188801"
    "uuid": "4a5d375ac1311b04fba2ea66d067b8e5"
}
```

## Response from partner

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
 "cash": 99899.99,
 "bonus": 99.99,
 "error": 0,
 "description": "Success"
 }

```
