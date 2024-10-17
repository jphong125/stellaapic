# Check

## Overview
A request to check whether player can bet or not.

## Request

Requested "Check" API URL will be notified individually, for security reasons.

### Request Parameters

| Name       |Data Type| Description                                                              | Remark   |
|:-----------|:---:|:-------------------------------------------------------------------------|----------|
| providerId |string| Game Provider identifier                                                 | Required |
| userId     |string| Identifier of the user within the Casino Operator’s system.              | Required |
|currency|string| Currency of the player        | Required |
| sessionId  |string| Player’s game session id on Lucky Monaco system.                       | Required |
| uuid       |string| A unique ID for each request                                                                                                                                              | Required |

### Examples

METHOD

``` http
POST
```

URL

``` http
https://<API URL>/V4/Check
```
HEADER

``` http
Content-Type: application/json
```

### Example of HTTP BODY

``` json
{
    "providerId": "<Luckymonaco>",
    "userId": "<UserID>",
    "currency" : "<USD>,
    "sessionId": "<sessionId>",
    "uuid": "<uuid>"
}
```

## Response 

Example of successful response from Partner API servers.

### Response Parameter 

| Name  |Data Type| Description                  | Remark   |
|:------|:---:|:-----------------------------|----------|
| error |decimal| error code                   | Required |
| description |decimal| Response status short description. | Optional |


### Example of Json BODY

``` json
{    
    "error": 0,
    "description":"Success"
}
