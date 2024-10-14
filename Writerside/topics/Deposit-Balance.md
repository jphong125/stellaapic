# Deposit Balance

## Overview
**This method transfers funds in to player’s balance (i.e. deposit) within
Lucky Monaco system.** 

Important: In cases where transfer call fails due to : 

∙ network error (HTTP status ≠ 200) 

∙ error: 1 (description: “internal error”) in response

Operator should send idempotent retry calls (with the same externalTransactionId).
Recommended actions are specified in Error codes

Important: The call is idempotent, i.e. sending it again only creates one transaction.



## API URL

Requested deposit balance API URL will be notified individually, for security reasons.

### Parameters

| Name                  |Data Type| Description                                                 | Remark   |
|:----------------------|:---:|:------------------------------------------------------------|----------|
| secureLogin           |string| User name for authentication in the Casino Game API service | Required |
| PlayerId              |string| Id of the player within the Operator system.                | Required |
| currency              |string| Currency of the player.           | Required |
| TransactionId |string|  Id of the transaction within Casino Operator system.                                    | Required |
| amount                |string|   Amount to be added to player’s balance                                    | Required |
| uuid                |  string   | A unique ID for each request                                             | Required |
| token      |string| Token of the player from Authenticate response              | Required |
### Examples

METHOD

``` http
POST
```
URL

``` http
https://<API URL>/charge
```
HEADER

``` http
Content-Type: application/json
```

### Example of HTTP BODY

``` json
{
    "playerid": "tester",
    "TransactionId": "12345678",
    "currency": "USD",
    "amount": 1000,
    "uuid": "<uuid>"
}
```

## Response from partner

### Parameters 2

| Name          |Data Type| Description                                       | Required |
|:--------------|:---:|:--------------------------------------------------|---|
| currency      |string| Currency of the player.                           | Required |
| transactionId |string| Id of the transaction within Lucky Monaco system. | Required |
| balance       |string| Player’s balance after successful transaction.    | Required |



### Example of HTTP BODY 2

``` json
{
    "error": "0",
    "description": "success",
    "transactionId": "1908759",
    "balance": 1000
}
