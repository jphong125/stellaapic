# End Round

## Overview
Every time a game round is over, the Lucky Monaco system will call EndRound method, so that Operator can finalize the
game round transactions on their side in real time.

If Operator does not need to finalize transactions in real time it is strongly recommended to disable EndRound
functionality on the Lucky Monaco side. 

Important: EndRound request may be sent more than once. (When Lucky Monaco do not received response) If the game round is already finalized, Operator
should  ignore the EndRound request and return the success response.


## Request

Requested "End round" API URL will be notified individually, for security reasons.

### Request Parameters

| Name       | Data Type | Description                                                                | Remark  |
|:-----------|:---------:|:---------------------------------------------------------------------------|----------|
| uuid       |string| A unique ID for each request.                                              | Required |
| userId     |  string   | User's ID, specified by Partner when creating a game session.              | Required |
| gameId     |  string   | Id of the game.                                                            | Required |
| roundId    |  string   | Id of the round.                                                           | Required |
| providerId |  string   | Game Provider id.                                                          | Required |
| sessionId        |string| User’s game session id on Lucky Monaco system.                             | Required |
| currency     |  string   | Currency of the User.                                                                     | Required |
| win        |  string   | Win amount in round. Intended to notify Operator about amount won in round | Optional |

### Examples

METHOD

``` http
POST
```


### Example of URL

``` http
https://<API URL>/V4/EndRound
```

HEADER

``` http
Content-Type: application/json
```

### Example of HTTP BODY

``` json
{
    "gameId": "Im_60_tumblefortune",
    "providerId": "luckymonaco",
    "userId": "421",
    "roundid" : "5103188801"
    "currency" : "USD",
    "win" : "15.4",
    "uuid": "4a5d375ac1311b04fba2ea66d067b8e5",
    "sessionid": "<sessionId>"
}
```

## Response

Example of successful response from Partner API servers.

### Response Parameters 

| Name          |Data Type| Description                        | Remark |
|:--------------|:---:|:-----------------------------------|-----|
| transactionId |string| Id of the transaction in wallet.   | Required |
| currency      |string| Currency of the User.              | Required |
| cash          |decimal| Real balance of the User.          | Required |
| bonus         |decimal| Bonus balance of the User.         | Required |
| error  |  string   | code of error                      | Required |
| description |decimal| Response status short description. | Optional |

### Example of Json BODY

``` json
{
 "transactionId": "<transactionId>",
 "currency" : "USD",
 "cash": "99899.99",
 "bonus": "99.99",
 "error": 0,
 "description": "Success"
 }

```
