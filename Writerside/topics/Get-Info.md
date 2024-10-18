# Get Info

## Overview
You can get information about the free round you can set by making a simple call via URL.

## Request
Requested get info API URL will be notified individually, for security reasons. 

### Request Parameters

| Name             |Data Type| Description                                                 | Remark   |
|:-----------------|:---:|:------------------------------------------------------------|----------|
| secureLogin      |string| User name for authentication in the Casino Game API service | Required |
| uuid                |  string   | A unique ID for each request                                             | Required |
| token      |string| Token of the player from Authenticate response              | Required |

### Examples

METHOD

``` http
POST
```

URL

``` http
https://<API URL>/api/getInfo
```
HEADER

``` http
Content-Type: application/json
```
### Example of HTTP BODY

``` json
{
    "secureLogin" : "<partnerId>",
    "token" : "<token>"
    "uuid": "<uuid>"
}
```

## Response

Example of successful response from LuckyMonaco API servers.

### Response Parameters

| Name          |Data Type| Description                                                                                                                   | Remark  |
|:--------------|:---:|:------------------------------------------------------------------------------------------------------------------------------|---|
| limit_spin|number| Max possible Freeround Count (1~limit_spin) | Required |
| slot|array|List of support slot                                                                                                    |  Required |
| gameIdNumeric|string|slot no |  Required |
| gameName|string|slot name                                                                              |  Required |
|gameId|string|slot game id                                                                                                           |  Required |
| currency|array|List of support currency                                                                               |  Required |



### Example of Json BODY

``` json
    "error": 0,
    "description": "Success"
{
    "slot": [
        {
            "gameIdNumeric": "1",
            "gameName": "Pumpkin Farm",
            "gameId": "lm_1_pumpkinfarm"
        },
        {
            "gameIdNumeric": "2",
            "gameName": "Kelly's Wheel Double",
            "gameId": "lm_2_kellyswheeldouble"
        },...
    ],
    "currency": [
        "IDX",
        "USD",
        "JPY",
        "CNY",
        "RUB",...
    ],
    "limit_spin": 999
}
```