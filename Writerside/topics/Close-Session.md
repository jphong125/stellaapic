# Close Session

## Overview
This method terminates active game sessions of the player. Operator has the option to remove player’s history, so that the 
incomplete game rounds can not be finished by another player (usually this is relevant for terminals).To close only game 
session for specific game Operator may send game id parameter in the request.


## API URL

Requested close session API URL will be notified individually, for security reasons.

###  Request parameters

| Name         |Data Type| Description                                                                                                                                                                                                                                                |  Remark  |
|:-------------|:---:|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:--------:|
| secureLogin  |string| User name for authentication in the Casino Game API service                                                                                                                                                                                                | Required |
| gameId       |string| Id of the game. This is optional parameter,which has to be sent by Operator if only the session for specific game should be closed.                                                                                                                        | optional |
| clearHistory |string| Specifies whether to clear the history of the round or not. default value is 0.  <br/>May have the following values: <br/>1 – history should be removed, so that the last game round cannot be completed anymore <br/>0 – last game round can be completed | optional |
| token      |string| Token of the player from Authenticate response                                                                                                                                                                                                             | Required |
### Examples

METHOD

``` http
POST
```

URL

``` http
https://<API URL>/V4/CloseSession
```

HEADER

``` http
Content-Type: application/json
```
### Example of HTTP BODY

``` json
{
    "secureLogin" : "<partnerId>",
    "gameId" : "lm_1_pumpkinfarm",
    "clearHistory" : 0
    "token" : "<token>"
}
```

## Response 
|Name|Data Type|Description|Ramrk|
|:---|:---:|:---:|---|
| eroor  |  string   | code of error                                                   | Required |
| description |decimal| Response status short description. | Optional |

### Example of body

``` json
{
  "error": 0,
  "description": "Success"
}
```

