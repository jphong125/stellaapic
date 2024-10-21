# Cancel Round by Operator

## Overview
CancelRound method initiates a refund request, which the Lucky monaco system will send to the Operator’s remote wallet. <br/>After  successful refund call the game round will be marked as Cancelled in the Lucky Monaco system.<br/>
This method Operator can use any time they want to close player’s round forcefully
- due to a retention policy on the Operator’s system or according to requirements for regulated markets.
- If the operator wants to cancel a bet in an **only incomplete round**. (Can't cancel complete round)


## Request

Requested "Cancel Round" API URL will be notified individually, for security reasons.

###  Request Parameters

| Name        |Data Type| Description                                                                                                                         |  Remark  |
|:------------|:---:|:------------------------------------------------------------------------------------------------------------------------------------|:--------:|
| secureLogin |string| Partner name for authentication in the Casino Game API service                                                                      | Required |
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
https://<API URL>/V4/Cancleround
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
|Name|Data Type|Description|Remark |
|:---|:---:|:---:|---|
| eroor  |  string   | code of error                                                   | Required |
| description |decimal| Response status short description. | Optional |

### Example of Json BODY

``` json
{
  "error": 0,
  "description": "Success"
}
```

