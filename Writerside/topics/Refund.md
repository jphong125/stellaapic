# Refund (Reserved for future development)

## Overview
Lucky Monaco system may use this method to rollback a bet transaction on the Casino Operator side, in order to reverse
the transaction and adjust player’s balance. <br/> 
When receive a Cancel request Operator have to return money back to player’s  balance.

**This method does not require a separate API construction.** It is sent to the Cancel API. The reason for displaying it separately is to explain the process of how to terminate an incomplete round.

- Important : The call is idempotent, i.e. sending refund for existing bet again only creates one transaction.

- Important : If bet transaction is not found then nothing should happen on the Casino Operator side and success (0)
or specific error code for this situation should be returned.
- Important : **It is automatically executed when the operator executes "cancel round"**.
- Important : By any reason, if the relevant response is not received from OP side for 90days after the bet was successful in the Lucky Monaco system, then the Lucky Monaco system will automatically initiate a refund process.


## Request

Requested "Refund" win API URL will be notified individually, for security reasons.

### Request Parameters

| Name       |Data Type| Description                                                                                                                          |  Remark  |
|:-----------|:---:|:-------------------------------------------------------------------------------------------------------------------------------------|:--------:|
| userId     |  string   | User's ID, specified by Partner when creating a game session.                                                                        | Required |
| providerId |  string   | Game Provider id.                                                                                                                    | Required |
| gameName   |  string   | Name of the game.                                                                                                                    | Required |
| currency   |string| Currency of the User.                                                                                                                | Required |
| reference  |  string   | Unique reference of this transaction.                                                                                                | Required |
| gameId     |string| Id of the game. This is optional parameter, which has to be sent by Operator if only the session for specific game should be closed. | Required |
| uuid       |string| A unique ID for each request.                                                                                                        | Required |

### Examples

METHOD

``` http
POST
```

URL

``` http
https://<API URL>/v4/Cancel
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
 "currency": "USD",
 "gameId": "Im_60_tumblefortune",
 "gameName" : "tumblefortune",
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
