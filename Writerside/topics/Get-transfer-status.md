# Get Transfer Info

## Overview
This method returns the status of a particular transaction that transferred the money in or out the player’s balance on the
Lucky Monaco side.

Important: This method will return player’s balance after successful transaction for all transactions. 

## Request
Requested get transfer status API URL will be notified individually, for security reasons.

### Request Parameters

| Name        |Data Type| Description                                                    | Remark   |
|:------------|:---:|:---------------------------------------------------------------|----------|
| secureLogin  |string| partner Id for authentication in the LuckyMonaco API service | Required |
| userId     |string| Id of the User within the Operator system.                     | Required |
| uuid        |  string   | A unique ID for each request                                   | Required |
| token       |string| Token of the Partner from Authenticate response                 | Required |

### Examples

METHOD

``` http
POST
```

### Example of URL

``` http
https://<API URL>/transfer/GetTransferInfo
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
    "uuid": "<uuid>"
}
```

## Response

Example of successful response from LuckyMonaco API servers.

###  Response Parameters 

| Name          |Data Type| Description                                                                                                             | Remark  |
|:--------------|:---:|:------------------------------------------------------------------------------------------------------------------------|---|
| TransactionId |string| Id of the transaction within Casino Operator system.           | Required |
| amount        |string| Amount added to user’s balance (positive value) or subtracted from user’s balance (negative value), in user’s currency. |  Required |
| balance       |string| user’s balance after successful transaction                                                                             |  Required |
| currency    |    string  | Currency of the user.                                                                                                   |      Required |
| error         |string| Error code.                                                                                                             |  Required |
| description         |string| Description of the error for troubleshooting.                                                                           |  Required |



### Example of Json BODY

``` json
{
    "error": 0,
    "description": "success",
    "transctionid": "ab4cee3-f73b-4631-9abf-b1a09c",
    "currency": "USD",
    "amount" : "1000",
    "balance": "1000"
}
