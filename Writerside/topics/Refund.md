# Refund 

## Overview
Kyren system may use this method to rollback a round on the Casino Operator side, in order to reverse
the transaction and adjust player’s balance. <br/> 
When receive a refund request Operator have to return money back to player’s  balance.

- Important : The call is idempotent, i.e. sending refund for existing bet again only creates one transaction.

- Important : If bet transaction is not found then nothing should happen on the Casino Operator side and success (0)
or specific error code for this situation should be returned.
- Important : **It is automatically executed when the operator executes "cancel round"**.



## Request

Requested "Refund" win API URL will be notified individually, for security reasons.

### Request Parameters

| Name       |Data Type| Description                                                                                                                          |  Remark  |
|:-----------|:---:|:-------------------------------------------------------------------------------------------------------------------------------------|:--------:|
| userId     |  string   | User's ID, specified by Partner when creating a game session.                                                                        | Required |
| providerId |  string   | Game Provider id.                                                                                                                    | Required |
| gameName   |  string   | Name of the game.                                                                                                                    | Required |
| currency   |string| Currency of the User.                                                                                                                | Required |
| roundId     |string| Id of round to be refunded                                                                                                           | Required |
| reference  |  string   | Unique reference of this transaction.                                                                                                | Required |
| bonusCode           |  string   | Id of the bonus (i.e. FREE ROUND) in Casino Operator system.                                                                         | Optional |
| gameId     |string| Id of the game. This is optional parameter, which has to be sent by Operator if only the session for specific game should be closed. | Required |
| uuid       |string| A unique ID for each request.                                                                                                        | Required |

### Examples

METHOD

``` http
POST
```

URL

``` http
https://<API URL>/v1/Refund
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
 "roundId": "<roundId>",
 "reference": "585c1306f89c56f5ecfc2f5d",
 "uuid": "4a5d375ac1311b04fba2ea66d067b8e5"
}
```


## Response

Example of successful response from Partner API servers.

### Response Parameters 

| Name          |Data Type| Description                        | Remark   |
|:--------------|:---:|:-----------------------------------|----------|
| transactionId |string| Id of the transaction within Casino Operator system. | Required |
| error |string| error code.                        | Required |
| description |string| Response status short description. | Optional |

### Example of Json BODY

``` json
{
 "transactionId": "<transactionId>",
 "error": "0",
 "description": "Success"
 }

```
