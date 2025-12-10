# Balance

## Overview
A request to check wallet balance.

## Request

Requested "Balance" API URL will be notified individually, for security reasons. 

### Request Parameters

| Name       |Data Type| Description                                                 | Remark   |
|:-----------|:---:|:------------------------------------------------------------|----------|
| providerId |string| Game Provider identifier.                                   | Required |
| userId     |string| Identifier of the user within the Casino Operator’s system. | Required |
| currency   |string| Currency of the player.                                     | Required |
| sessionId  |string| User’s game session id on Lucky Monaco system.              | Required |
| uuid       |string| A unique ID for each request                                | Required |

### Examples

METHOD

``` http
POST
```
URL

``` http
https://<API URL>/v1/Balance
```
HEADER

``` http
Content-Type: application/json
```

### Example of HTTP BODY

``` json
{
    "providerId": "<Stella>",
    "userId": "<User ID>",
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
| error  |  string   | code of error.                                    | Required |
| description |string| Response status short description.                | Optional |

### Example of Json BODY

``` json
{
    "currency": "USD",
    "cash": "99999.99",
    "error": 0,
    "description":"Success"
}
