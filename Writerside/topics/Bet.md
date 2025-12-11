# Bet

## Overview
Using this method Kyren system will check the player balance on Casino Operator side to ensure they still have the
funds to cover the bet.<br/> **Amount of the bet must be subtracted from player balance in Casino Operator system.** <br/>  Players connection was lost in any cases so Kyren will do retransmission 3 times, then do not receive any bet response. Kyren will request a cancel bet. 

Important: The call is idempotent, i.e. sending bet again only creates one transaction.

## Request

Requested "Bet" API URL will be notified individually, for security reasons.

### Request Parameters

| Name         | Data Type | Description                                                                                                                    | Remark   |
|:-------------|:---------:|:-------------------------------------------------------------------------------------------------------------------------------|----------|
| uuid         |string| A unique ID for each request                                                                                                   | Required |
| userId       |  string   | User's ID, specified by Operator when creating a game session.                                                                 | Required |
| gameId       |  string   | ID of the game.                                                                                                                | Required |
| gameName     |  string   | name of the game.                                                                                                              | Required |
| roundId      |  string   | ID of the round.                                                                                                               | Required |
| amount       |  decimal  | Amount of the bet.                                                                                                             | Required |
| bonusCode           |  string   | Id of the bonus (i.e. FREE ROUND) in Casino Operator system.                                                                   | Optional |
| reference    |  string   | Unique reference of this transaction.                                                                                          | Required |
| sessionId    |string| User’s game session id on Kyren system.                                                                                       | Required |
| providerId   |  string   | Game Provider ID.                                                                                                              | Required |
| currency     |string| Currency of the User                                                                                                           | Required |
| timeStamp    |  string   | Date and time when the transaction is processed on the Kyren system.                                                    | Required |
| roundDetails |  string   | Additional information about the current game round. (i.e. "type:bet,desc:[{banker:10},{tie:1},{playerpair:1},{bankerpair:1}]" | Required |

### Examples

METHOD

``` http
POST
```

URL

``` http
https://<API URL>/v1/Bet
```
HEADER

``` http
Content-Type: application/json
```

### Example of HTTP BODY

``` json
{
    "providerId": "Kyren",
    "userId": "421",
    "sessionId": "<sessionId>",
    "currency": "USD",
    "amount": "13", 
    "roundDetails": {"type": "bet","desc": [{"banker":10}, {"tie":1}, {"playerpair":1}, {"bankerpair":1}]},
    "reference": "585c1306f89c56f5ecfc4s5d",
    "gameId": "6_speed_baccarat1",  
    "gameName": "SPEED BACCARAT1",
    "roundId" : "5103188801",
    "uuid": "4a5d375ac1311b04fba2ea66d067b8e5",
    "timestamp": "1482429190374"
}
```

## Response

Example of successful response from Partner API servers.

### Response Parameters

| Name          |Data Type| Description                                          | Remark  |
|:--------------|:---:|:-----------------------------------------------------|-----|
| currency     |string| Currency of the User                                                                                                           | Required |
| transactionId |string| Id of the transaction within Casino Operator system. | Required |
| cash          |decimal| Real balance of the player.                          | Required |
| error         |  string   | Code of error.                                       | Required |
| description   |string| Response status short description.                   | Optional |

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
