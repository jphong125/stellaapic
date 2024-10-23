# Balance

## Overview
A request to check wallet balance.

## Request

Requested "Balance" API URL will be notified individually, for security reasons. 

### Request Parameters

| Name                  |Data Type| Description                                                 | Remark   |
|:----------------------|:---:|:------------------------------------------------------------|----------|
| providerid            |string| Game Provider identifier of the Operator's system.          | Required |
| userid             |string| Identifier of the user within the Casino Operator’s system. | Required |
|currency|string| Currency of the player.                                     | Required |
| sessionId        |string| User’s game session id on Lucky Monaco system.              | Required |
| uuid        |string| A unique ID for each request                                | Required |

### Examples

METHOD

``` http
POST
```
URL

``` http
https://<API URL>/V4/Balance
```
HEADER

``` http
Content-Type: application/json
```

### Example of HTTP BODY

``` json
{
    "providerid": "<Luckymonaco>",
    "userid": "<User ID>",
    "sessionId": "<sessionId>",
    "currency": "USD",
    "uuid": "<uuid>"
}
```

## Response

Example of successful response from Partner API servers.

### Response Parameter

|Name|Data Type| Description                                       | Remark   |
|:---|:---:|:--------------------------------------------------|----------|
|currency|string| Currency of the user.                             | Required |
|cash|decimal| Money balance that was deposited with real money. | Required |
| eroor  |  string   | code of error.                                    | Required |
| description |decimal| Response status short description.                | Optional |

### Response Parameter (Reserved for future development)

|Name|Data Type| Description                                                  | Remark   |
|:---|:---:|:-------------------------------------------------------------|----------|
|bonus|decimal| This is the balance of money that was won from the FREE ROUND feature. | Optional |

### Example of Json BODY

``` json
{
    "currency": "USD",
    "cash": "99999.99",
    "error": 0,
    "description":"Success"
}
