# Get Balance Per Game

## Overview
The method allows Lucky Monaco to get player’s balance available for certain games. This method is applicable to
operators that needs different amount of money to be available in the game client depending on the game type and the
policy within  Casino Operator system.

## API URL

Requested get balance per game API URL will be notified individually, for security reasons.

### Parameters

| Name       |Data Type| Description                                                                                                                      | Remark   |
|:-----------|:---:|:---------------------------------------------------------------------------------------------------------------------------------|----------|
| providerid |string| Game Provider identifier                                                                                                         | Required |
| userid     |string| Identifier of the user within the Casino Operator’s system.                                                                      | Required |
| gameidList |string| The list of games for which player’s balance should be returned. It is a string contains gameid separated by comma.              | Required |
| uuid        |string| A unique ID for each request                                                                                                                                              | Required |
| platform   |string| The platform type (channel) on which thegame is played                                                                           | Optional |
| token      |string| Token of the player from Authenticate response.                                                                                  | Optional |


### Example of URL

``` http
https://<API URL>/V4/GetBalancePerGame
```

### Example of HTTP BODY

``` json
{
    "providerid": "<Luckymonaco>",
    "userid": "<User ID>",
    "gameIdList": 
    [
    "Im_31_sambatrio",
    "Im_60_tumblefortune"
    ]
}
```

## Response from partner

### Parameters 2

| Name         |Data Type| Description                                                                                                                                                                               | Remark   |
|:-------------|:---:|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------|
| gameBalances |string| The list of player’s balances per game. Contains data structures with the following fields: <br/>gameID – id of the game <br/>cash – Real balance of the player <br/>bonus – Bonus balance of the player | Required |



### Example of HTTP BODY 2

``` json
{
 "gamesBalances": [
 {"gameID":"vs20cd","cash":25.02,"bonus":0.00},
 {"gameID":"vs9c","cash":12.02,"bonus":0.00}
 ]
 }