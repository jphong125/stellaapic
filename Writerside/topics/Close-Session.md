# Close Session

## Overview

This method terminates active game sessions of the player.Operator has the option to remove player’s history,so that the 
incomplete game rounds can not be finished by another player (usually this is relevant for terminals).To close only game 
session for specific game Operator may send game id parameter in the request.

## Usage

Close session can be executed as per your request through individual API URL.

## API URL

Requested game session API URL will be notified individually, for security reasons.

Request parameters

| Name         |Data Type| Description                                                                                                                                                                                                                                                     |  Remark  |
|:-------------|:---:|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:--------:|
| secureLogin  |string| User name for authentacation in the Casino Game API service                                                                                                                                                                                                     | Required |
| gameId       |string| Id of the game. This is optional parameter,which has to be sent by Operator if only the session for specific game should be closed.                                                                                                                             | optional |
| clearHistory |string| Specifies whether to clear the history of the round or not. default value is 0.  <br/>May have the following values: <br/>1 – history should be removed, so that the last game round cannot be completed anymore <br/>0 – last game round can be completed | optional |
| hash         |string| Hash code of request.                                                                                                                                                                                                                                           | Required |
### Examples

METHOD

``` http
POST
```

URL

``` http
https://<API URL>/V4/closesession?MEMB_ID=<Partner ID>&HASH=<TOKEN>
```

HEADER

``` http
Content-Type: application/json
```

## Successful response 

### Example of body

``` json
{
  "error": 0,
  "description": "Success"
}
```

## Failure response for getting Game List ( response )

Example of failure response from LuckyMonaco API servers.

In case of failure, LuckyMonaco servers will return  'HTTP status 4XX' or 'HTTP status 5XX' and following response body.

### Example of body2

``` json
{
    "error": {
        "code": "G.1",
        "message": "INVALID GAME TYPE"
    }
}
```

### Error codes

Error codes are classified into following categories.

* G - Generic failures
* V - Validation of input parameters failed

|Code|Description (omitting error codes)|
|:---|:---:|
|G.01|Invalid game type|

Error codes will be additionally updated

Start typing here...
Start typing here...Start typing here...