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

## Response

Example of successful response from LuckyMonaco API servers.

### Response Parameters

| Name          |Data Type| Description                                                                                                                   | Remark  |
|:--------------|:---:|:------------------------------------------------------------------------------------------------------------------------------|---|
| limit_spin|number| Max possible Freeround Count (1~limit_spin) | Required |
| slot|array|List of support slot                                                                                                    |  Required |
| slot.No|string|slot no |  Required |
| slot.Name|string|slot name                                                                              |  Required |
|slot.ID|string|slot game id                                                                                                           |  Required |
| currency|array|List of support currency                                                                               |  Required |



### Example of Json BODY

``` json
    "error": 0,
    "description": "Success"
{
    "slot": [
        {
            "No": "1",
            "Name": "Pumpkin Farm",
            "ID": "lm_1_pumpkinfarm"
        },
        {
            "No": "2",
            "Name": "Kelly's Wheel Double",
            "ID": "lm_2_kellyswheeldouble"
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