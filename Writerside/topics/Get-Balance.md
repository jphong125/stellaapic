# Get Balance

Using this method Operator can get the current balance of the player in the Lucky Monaco

## Requested by LuckyMonaco

### Parameters

| Name             |Data Type| Description                                                 | Remark   |
|:-----------------|:---:|:------------------------------------------------------------|----------|
| secureLogin      |string| User name for authentication in the Casino Game API service | Required |
| externalPlayerId |string| Id of the player within the Operator system.                | Required |
| currency         |    string  | Currency of the player.                                 |      Required |
| hash             |string| Hash code of request.                                       | Required |

### Example of URL

``` http
https://<API URL>/user/balance?authToken=<TOKEN>
```

### Example of HTTP BODY

``` json
{
    "externalplayerid": "tester",
    "currency": "USD",
    "hash": "<hash>"
}
```

## Response from partner

### Parameters 2

| Name     |Data Type| Description                                              | Required |
|:---------|:---:|:---------------------------------------------------------|---|
| balance |string| Current player’s balance within the Lucky Monaco system. |  Required |



### Example of HTTP BODY 2

``` json
{
    "error": "0",
    "description": "success",
    "balance": 1000,
}
