# Deposit Balance

## Overview
**This method transfers funds in to player’s balance (i.e. deposit) within
Lucky Monaco system.** 

Important: In cases where transfer call fails due to : 

∙ network error (HTTP status ≠ 200) 

∙ error: 1 (description: “internal error”) in response

Operator should send idempotent retry calls (with the same externalTransactionId).
Recommended actions are specified in Error codes.

Important: The call is idempotent, i.e. sending it again only creates one transaction.



## Request

Requested deposit balance API URL will be notified individually, for security reasons.

### Request Parameters

| Name          |Data Type| Description                                                    | Remark   |
|:--------------|:---:|:---------------------------------------------------------------|----------|
| secureLogin   |string| partner name for authentication in the Casino Game API service | Required |
| userId       |string| Id of the user within the Operator system.                     | Required |
| currency      |string| Currency of the user.                                          | Required |
| TransactionId |string| Id of the transaction within Casino Operator system.           | Required |
| amount        |string| Amount to be added to player’s balance                         | Required |
| uuid          |  string   | A unique ID for each request                                   | Required |
| token         |string| Token of the Partner from Authenticate response                 | Required |

### Examples

METHOD

``` http
POST
```
URL

``` http
https://<API URL>/transfer/DepositBalance
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
    "TransactionId": "12345678",
    "currency": "USD",
    "amount": 1000,
    "uuid": "<uuid>"
}
```

## Response

Example of successful response from LuckyMonaco API servers. 

###  Response Parameters 

| Name          |Data Type| Description                                       | Remark  |
|:--------------|:---:|:--------------------------------------------------|---|
| currency      |string| Currency of the User.                             | Required |
| transactionId |string| Id of the transaction within Lucky Monaco system. | Required |
| balance       |string| User’s balance after successful transaction.      | Required |
| error         |  string   | code of error.                                    | Required |
| description   |decimal| Response status short description.                | Optional |


### Example of Json BODY

``` json
{
    "error": 0,
    "description": "success",
    "transactionId": "1908759",
    "currency": "USD",
    "balance": "1000"
}
