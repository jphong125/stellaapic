# Create User

Using this method Casino Operator will create player’s account within the Lucky Monaco system. This method should be called
before player is sent to the Lucky Monaco’s games.


## Requested by LuckyMonaco

### Parameters

| Name             |Data Type| Description                                                 | Remark   |
|:-----------------|:---:|:------------------------------------------------------------|----------|
| secureLogin      |string| User name for authentication in the Casino Game API service | Required |
| externalPlayerId |string| Id of the player within the Operator system.                | Required |
| nickname         |string| nickname of the player within the Operator system.           | Optional |
| hash             |string| Hash code of request.                                       | Required |

### Example of URL

``` http
https://<API URL>/user/create_user?authToken=<TOKEN>
```

### Example of HTTP BODY

``` json
{
    "externalplayerid": "tester",
    "nickname": "tester1",
    "hash": "<hash>"
}
```

## Response from partner

### Parameters 2

| Name     |Data Type| Description                                      | Required |
|:---------|:---:|:-------------------------------------------------|---|
| playerid |string| Id of the player within the Lucky Monaco system. |  Required |



### Example of HTTP BODY 2

``` json
{
    "error": "0",
    "description": "success",
    "playerId": "64749175",
}
