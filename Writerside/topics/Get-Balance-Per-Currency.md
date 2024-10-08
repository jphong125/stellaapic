# Get Balance Per Currency

The method allows Lucky Monaco to get player’s balance available for certain games. This method is applicable to
operators that needs different currency amount of money to be available in the game client depending on the game type and the
policy within  Casino Operator system.

## Requested by LuckyMonaco

### Parameters

| Name         |Data Type| Description                                                                                                                    | Remark   |
|:-------------|:---:|:-------------------------------------------------------------------------------------------------------------------------------|----------|
| providerid   |string| Game Provider identifier                                                                                                       | Required |
| userid       |string| Identifier of the user within the Casino Operator’s system.                                                                    | Required |
| currencyList |string| The list of currecy amount for which player’s balance should be returned. It is a string contains currency separated by array. | Required |
| hash         |string| Hash code of request.                                                                                                          | Required |
| platform     |string| The platform type (channel) on which thegame is played                                                                         | Optional |
| token        |string| Token of the player from Authenticate response.                                                                                | Optional |


### Example of URL

``` http
https://<API URL>/getbalancepercurrency?authToken=<TOKEN>
```

### Example of HTTP BODY

``` json
{
    "providerid": "<Luckymonaco>",
    "userid": "<User ID>",
    "currency": 
    [
    "USD", 
    "GOLD"
    ]
}
```

## Response from partner

### Parameters 2

| Name             |Data Type| Description                                                                                                                                                                                                   | Remark   |
|:-----------------|:---:|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------|
| currencyBalances |string| The list of player’s balances per currency.  | Required |



### Example of HTTP BODY 2

``` json
{
 "currencyBalances": [
 {"USD":"cash":25.02,"bonus":0.00},
 {"GOLD":"cash":1001,"bonus":0.00}
 ]
 }