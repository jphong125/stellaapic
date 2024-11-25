# Cancel Round by Operator

## Overview
Using this method Casino Operator Cancels in progress game round   <br/>After  successful cancel call the game round will be marked as Cancelled in the Lucky Monaco system.<br/>
This method Operator can use any time they want to close player’s round forcefully
- due to a retention policy on the Operator’s system or according to requirements for regulated markets.
- **This circumstance only applies to the bet which has not been completed by any reasons.** Cancel Round cannot be executed on the round that has been completed.
- Impotant : In principle, incomplete rounds are completed by the user reconnecting or auto-closing. To deal with malicious users, we recommend canceling only when a user complains with **clear evidence.**

## Request

Requested "Cancel Round" API URL will be notified individually, for security reasons.

###  Request Parameters

| Name        |Data Type| Description                                                                                                                         |  Remark  |
|:------------|:---:|:------------------------------------------------------------------------------------------------------------------------------------|:--------:|
| secureLogin  |string| partner Id for authentication in the LuckyMonaco API service | Required |
| gameId      |string| Id of the game. This is optional parameter,which has to be sent by Operator if only the session for specific game should be closed. | optional |
| userId      |string| Identifier of the user within the Casino Operator’s system.                                                                         | Required |
| roundId     |string| Id of round                                                                                                                         | Required |
| token       |string| Token of the Partner from Authenticate response                                                                                     | Required |
| uuid        |  string   | A unique ID for each request                                                                                                        | Required |

### Examples

METHOD

``` http
POST
```

URL

``` http
https://<API URL>/v4/CancelRound
```

HEADER

``` http
Content-Type: application/json
```
### Example of HTTP BODY

``` json
{
    "secureLogin" : "<partnerId>",
    "gameId" : "lm_1_pumpkinfarm",
    "userId": "tester",
    "roundId" : "123456",
    "token" : "<token>",
    "uuid": "<uuid>"
}
```

## Response

Example of successful response from LuckyMonaco API servers.

### Response parameters
|Name|Data Type|                     Description                      |Remark |
|:---|:---:|:----------------------------------------------------:|---|
| error  |  string   |                    Code of error                     | Required |
| description |string|          Response status short description.          | Optional |
| currency     |string|                 Currency of the User                 | Required |
| amount       |  decimal  |                Amount to be refunded.                | Required |
| transactionId |string| Id of the transaction within Casino Operator system. | Required |

### Example of Json BODY

``` json
{
  "error": 0,
  "description": "Success",
  "currency": "USD"
  "amount": 100,
  "transactionId" : "<bet transactionId> 
}
```

