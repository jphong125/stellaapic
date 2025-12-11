# Get Info

## Overview
You can get information about the free round you can set by making a simple call via URL.

## Request
Requested get info API URL will be notified individually, for security reasons. 

### Request Parameters

| Name             |Data Type| Description                                                  | Remark   |
|:-----------------|:---:|:-------------------------------------------------------------|----------|
| secureLogin  |string| Partner Id for authentication in the Kyren API service | Required |
| uuid                |  string   | A unique ID for each request                                 | Required |
| token      |string| Token of the Partner from Authenticate response              | Required |

### Examples

METHOD

``` http
POST
```

URL

``` http
https://<API URL>/freeround/getInfo
```
HEADER

``` http
Content-Type: application/json
```
### Example of HTTP BODY

``` json
{
    "secureLogin" : "<partnerId>",
    "token" : "<token>",
    "uuid": "<uuid>"
}
```

## Response

Example of successful response from Kyren API servers.

### Response Parameters

| Name          | Data Type | Description                                 | Remark  |
|:--------------|:---------:|:--------------------------------------------|---|
| limit_spin| interger  | Max possible Freeround Count (1~limit_spin) | Required |
| slot|   array   | List of support slot                        |  Required |
| gameIdNumeric|  string   | Slot no                                     |  Required |
| gameName|  string   | Slot name                                   |  Required |
|gameId|  string   | Slot game id                                |  Required |
| currency|   array   | List of support currency                    |  Required |



### Example of Json BODY

``` json
    "error": 0,
    "description": "Success"
{
    "slot": [
        {
            "gameIdNumeric": "1",
            "gameId": "lm_1_speed_baccarat1",
            "gameName" : "SPEED BACCARAT1"
        },
        {
            "gameIdNumeric": "2",
            "gameId": "lm_2_speed_baccarat2",
            "gameName" : "SPEED BACCARAT2",
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