# Cancel Bet

## Overview

Notifies the casino Operator that Canceled player’s bet.  <br />
This method will be used for cancellation of a bet. <br />
(i.e. Players connection was lost in any cases so Kyren will do retransmission 3 times, then do not receive any bet response.) <br />
Important : The sessionId of the cancel request is the same as the sessionId of the bet. Therefore, the cancel request must be accepted even if the player creates a new session.


## Request

Requested cancel round API URL will be notified individually, for security reasons.


###  Request parameters

| Name       |Data Type| Description                                                                                                                          |  Remark  |
|:-----------|:---:|:-------------------------------------------------------------------------------------------------------------------------------------|:--------:|
| userId     |  string   | User's ID, specified by Partner when creating a game session.                                                                        | Required |
| sessionId    |string| User’s game session id on Kyren system.                                    | Required |
| providerId |  string   | Game Provider id.                                                                                                                    | Required |
| gameName   |  string   | Name of the game.                                                                                                                    | Required |
| currency   |string| Currency of the User.                                                                                                                | Required |
| reference  |  string   | Unique reference of this transaction.                                                                                                | Required |
| roundId    |  string   | Id of the round.                                                           | Required |
| gameId     |string| Id of the game. This is optional parameter, which has to be sent by Operator if only the session for specific game should be closed. | Required |
| uuid       |string| A unique ID for each request.                                                                                                        | Required |


### Examples

METHOD

``` http
POST
```

URL

``` http
https://<API URL>/v1/Cancel
```

HEADER

``` http
Content-Type: application/json
```

### Example of HTTP BODY

``` json

{
    "providerId": "Kyren",
    "userId": "123456",
    "currency": "USD",
    "gameId": "6_speed_baccarat1",
    "gameName" : "SPEED BACCARAT1",
    "reference": "585c1306f89c56f5ecfc2f5d",
    "sessionId": "<sessionId>",
    "roundId" : "<roundId>",
    "uuid": "4a5d375ac1311b04fba2ea66d067b8e5"
}
```
## Response

Example of successful response from Partner API servers.

## Response parameters

| Name        | Data Type | Description                                          | Remark  |
|:------------|:---------:|:-----------------------------------------------------|----------|
| error       |  string   | Code of error.                                       | Required |
| description |string| Response status short description.                   | Optional |
| currency   |string| Currency of the User.                                                                                                                | Required |
| cash          |decimal| Real balance of the User.          | Required |
| transactionId |string| Id of the transaction within Casino Operator system. | Required |

### Example of Json BODY

``` json
{
  "error": 0,
  "description": "Success",
  "currency": "USD",
  "cash": "99899.99",
  "transactionId": "585c1306f89c56f5ecfc2f5d"
}
```

