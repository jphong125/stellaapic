# Get Balance

## Overview
Using this method Operator can get the current balance of the player in the Lucky Monaco

## API URL
Requested get balance API URL will be notified individually, for security reasons.

### Parameters

| Name        |Data Type| Description                                                 | Remark   |
|:------------|:---:|:------------------------------------------------------------|----------|
| secureLogin |string| User name for authentication in the Casino Game API service | Required |
| userId   |string| Id of the player within the Operator system.                | Required |
| currency    |    string  | Currency of the player.                                 |      Required |
| uuid        |  string   | A unique ID for each request                                             | Required |
| token       |string| Token of the player from Authenticate response              | Required |

### Examples

METHOD

``` http
POST
```

URL

``` http
https://<API URL>/getBalance
```
HEADER

``` http
Content-Type: application/json
```

### Example of HTTP BODY

``` json
{
    "userId": "tester",
    "currency": "USD",
    "hash": "<hash>"
}
```

## Response from partner

### Parameters 2

| Name     |Data Type| Description                                              | Required |
|:---------|:---:|:---------------------------------------------------------|---|
| balance |string| Current player’s balance within the Lucky Monaco system. |  Required |
| eroor  |  string   | code of error                                                   | Required |
| description |decimal| Response status short description. | Optional |


### Example of HTTP BODY 2

``` json
{
    "error": "0",
    "description": "success",
    "balance": 1000,
}
