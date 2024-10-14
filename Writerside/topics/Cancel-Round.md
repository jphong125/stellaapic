# Cancel Round

## Overview

CancelRound method initiates a refund request, which the Lucky Monaco system will send to the Operator’s remote wallet.
After  successful refund call the game round will be marked as Cancelled in the Lucky Monaco system.

## API URL

Requested cancel round API URL will be notified individually, for security reasons.

###  Request parameters

| Name         |Data Type| Description                                                                                                                          |  Remark  |
|:-------------|:---:|:-------------------------------------------------------------------------------------------------------------------------------------|:--------:|
| userId       |  string   | Player's ID, specified by Partner when creating a game session.                 | Required |
| providerId   |  string   | Game Provider id.                                                               | Required |
| gamename     |  string   | name of the game.                                                               | Required |
| currency     |string| Currency of the player                                                          | Required |
| reference    |  string   | Unique reference of this transaction.                                           | Required |
| gameId       |string| Id of the game. This is optional parameter, which has to be sent by Operator if only the session for specific game should be closed. | Required |
| uuid         |string| A unique ID for each request                                                    | Required |
| sessionId        |  string   | Player’s game session id on Lucky Monaco system.                         | Required |
### Examples

METHOD

``` http
POST
```

URL

``` http
https://<API URL>/V4/CancelRound
```

HEADER

``` http
Content-Type: application/json
```

### Example of HTTP BODY

``` json

{
    "providerId": "LuckyMonaco",
    "userId": "123456",
    "sessionId": "<sessionId>",
    "currency": "USD",
    "gameId": "Im_60_tumblefortune",
    "gameName" : "tumblefortune",
    "reference": "585c1306f89c56f5ecfc2f5d",
    "uuid": "4a5d375ac1311b04fba2ea66d067b8e5"
}
```

## Response

| Name   | Data Type | Description                                                     | Required |
|:-------|:---------:|:----------------------------------------------------------------|----------|
| eroor  |  string   | code of error                                                   | Required |
| description |decimal| Response status short description. | Optional |
| reference    |  string   | Unique reference of this transaction.                                           | Required |

### Example of body

``` json
{
  "error": 0,
  "description": "Success",
  "reference": "585c1306f89c56f5ecfc2f5d"
}
```

