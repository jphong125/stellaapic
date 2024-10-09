# Get transfer status

This method returns the status of a particular transaction that transferred the money in or out the player’s balance on the
Lucky Monaco side.

Important: This method will return player’s balance after successful transaction for all transactions 

## Requested by LuckyMonaco

### Parameters

| Name             |Data Type| Description                                                 | Remark   |
|:-----------------|:---:|:------------------------------------------------------------|----------|
| secureLogin      |string| User name for authentication in the Casino Game API service | Required |
| externalPlayerId |string| Id of the player within the Operator system.                | Required |
| hash             |string| Hash code of request.                                       | Required |

### Example of URL

``` http
https://<API URL>/user/balance/transfer?authToken=<TOKEN>
```

### Example of HTTP BODY

``` json
{
    "externalplayerid": "tester",
    "hash": "<hash>"
}
```

## Response from partner

### Parameters 2

| Name          |Data Type| Description                                                                                                                   | Required |
|:--------------|:---:|:------------------------------------------------------------------------------------------------------------------------------|---|
| transactionId |string| Id of the transaction within Lucky Monaco system.                                                                             | Required |
| status        |string| Status of the transaction.                                                                                                    |  Required |
| amount        |string| Amount added to player’s balance (positive value) or subtracted from player’s balance (negative value), in player’s currency. |  Required |
| balance       |string| Player’s balance after successful transaction                                                                                 |  Required |
| error         |string| Error code.                                                                                                                   |  Required |
| description         |string| Description of the error for troubleshooting.                                                                                 |  Required |



### Example of HTTP BODY 2

``` json
{
    "error": "0",
    "description": "success",
    "transctionid": "ab4cee3-f73b-4631-9abf-b1a09c",
    "currency": "USD",
    "amount" : 1000
    "balance": 1000,
}
