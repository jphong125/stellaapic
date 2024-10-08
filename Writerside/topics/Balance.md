# Balance

A request to check wallet balance

## Requested by LuckyMonaco

### Parameters

| Name                  |Data Type| Description                                                              | Remark   |
|:----------------------|:---:|:-------------------------------------------------------------------------|----------|
| providerid            |string| Game Provider identifier                                                 | Required |
| userid                |string| Identifier of the user within the Casino Operator’s system.              | Required |
| token                 |string| Token of the player from Authenticate response.| Required |
| hash         |string| Hash code of request.                                             | Required|

### Example of URL

``` http
https://<API URL>/Balance?authToken=<TOKEN>
```

### Example of HTTP BODY

``` json
{
    "providerid": "<Luckymonaco>",
    "userid": "<User ID>",
    "token": "<token>"
    "hash": "<hash>"
}
```

## Response from partner

### Parameters 2

|Name|Data Type| Description                  | Required |
|:---|:---:|:-----------------------------|---|
|currency|string| Currency of the player       |  Required |
|cash|decimal| Real balance of the player.  |  Required |
|bonus|decimal| Bonus balance of the player. |  Required |


### Example of HTTP BODY 2

``` json
{
    "currency": "USD",
    "cash": 99999.99,
    "bonus": 99.99,
    "error": 0,
    "description":"Success"
}
