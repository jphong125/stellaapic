# Get Balance

## Overview
Using this method Operator can get the current balance of the player in the Lucky Monaco.

## Request
Requested get balance API URL will be notified individually, for security reasons.

### Request Parameters

| Name        |Data Type| Description                                                    | Remark   |
|:------------|:---:|:---------------------------------------------------------------|----------|
| secureLogin |string| partner name for authentication in the Casino Game API service | Required |
| userId   |string| Id of the user within the Operator system.                     | Required |
| currency    |    string  | Currency of the user.                                          |      Required |
| uuid        |  string   | A unique ID for each request                                   | Required |
| token       |string| Token of the Partner from Authenticate response                 | Required |

### Examples

METHOD

``` http
POST
```

URL

``` http
https://<API URL>/transfer/GetBalance
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
    "userId": "tester",
    "currency": "USD",
    "uuid": "<uuid>"
}
```

## Response

Example of successful response from LuckyMonaco API servers.

###  Response Parameters 

| Name        |Data Type| Description                                            | Remark  |
|:------------|:---:|:-------------------------------------------------------|---|
| balance     |string| Current user’s balance within the Lucky Monaco system. |  Required |
| error       |  string   | code of error.                                         | Required |
| description |decimal| Response status short description.                     | Optional |


### Example of Json BODY

``` json
{
    "error": 0,
    "description": "success",
    "balance": "1000"
}
