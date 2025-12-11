# Close Session

## Overview
Using this method Casino Operator terminates active game sessions of the player. <br/>Do not use normal active player. <br/>To close only game 
session for specific game Operator may send game id parameter in the request. 

Impotant : In principle, incomplete rounds are completed by the user reconnecting or auto-closing. 

## Request

Requested "Close Session" API URL will be notified individually, for security reasons.

###  Request Parameters

| Name         |Data Type| Description                                                                                                                                                                                                                                                                                                |  Remark  |
|:-------------|:---:|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:--------:|
| secureLogin  |string| partner Id for authentication in the Kyren API service                                                                                                                                                                                                                                               | Required |
| gameId       |string| Id of the game. This is optional parameter,which has to be sent by Operator if only the session for specific game should be closed.                                                                                                                                                                        | optional |
| userId     |string| Identifier of the user within the Casino Operator’s system.                                                                                                                                                                                                                                                | Required |
| token      |string| Token of the Partner from Authenticate response                                                                                                                                                                                                                                                            | Required |
| uuid                |  string   | A unique ID for each request                                                                                                                                                                                                                                                                               | Required |

### Examples

METHOD

``` http
POST
```

URL

``` http
https://<API URL>/v1/CloseSession
```

HEADER

``` http
Content-Type: application/json
```
### Example of HTTP BODY

``` json
{
    "secureLogin" : "<partnerId>",
    "gameId": "6_speed_baccarat1",
    "userId": "tester",
    "token" : "<token>",
    "uuid": "<uuid>"
}
```

## Response 

Example of successful response from Kyren API servers.

### Response parameters
|Name|Data Type|            Description             |Remark |
|:---|:---:|:----------------------------------:|---|
| error  |  string   |           Code of error            | Required |
| description |decimal| Response status short description. | Optional |

### Example of Json BODY

``` json
{
  "error": 0,
  "description": "Success"
}
```

