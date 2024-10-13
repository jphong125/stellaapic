# Balance

## Overview
A request to check wallet balance

## API URL

Requested balance API URL will be notified individually, for security reasons. 

### Parameters

| Name                  |Data Type| Description                                                              | Remark   |
|:----------------------|:---:|:-------------------------------------------------------------------------|----------|
| providerid            |string| Game Provider identifier                                                 | Required |
| userid             |string| Identifier of the user within the Casino Operator’s system.              | Required |
| sessionId        |string| Player’s game session id on Lucky Monaco system.                       | Required |
| uuid        |string| A unique ID for each request                                                                                                                                              | Required |

### Example of URL

``` http
https://<API URL>/V4/Balance
```

### Example of HTTP BODY

``` json
{
    "providerid": "<Luckymonaco>",
    "userid": "<User ID>",
    "sessionId": "<sessionId>",
    "uuid": "<uuid>"
}
```

## Response from partner

### Parameters 2

|Name|Data Type| Description                                                  | Required |
|:---|:---:|:-------------------------------------------------------------|----------|
|currency|string| Currency of the player                                       | Required |
|cash|decimal| Real balance of the player.                                  | Required |
|bonus|decimal| Bonus balance of the player. (when a FRB has occurred.) | Optional |


### Example of HTTP BODY 2

``` json
{
    "currency": "USD",
    "cash": 99999.99,
    "error": 0,
    "description":"Success"
}
