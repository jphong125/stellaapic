# Session Expired

## Overview

Using this method the Lucky Monaco system will notify Casino Operator that player’s session has expired in Lucky Monaco
system due to long inactivity or game closing.

The method is optional and is not sent to the Casino Operator by default. In case Casino Operator needs this method to be
sent, they should ask the Lucky Monaco’s Technical Support for additional configuration


## API URL

Requested game session API URL will be notified individually, for security reasons.

Request parameters

| Name       |Data Type| Description                                                                                                                                                                                                                                                |  Remark  |
|:-----------|:---:|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:--------:|
| providerId |string| Lucky Monaco provider id in Operator’s system                                                                                                                                                                                                              | Required |
| sessionId  |string| Player’s game session id on Lucky Monaco side                                                                                                                                                                                                              | Required |
| playerId   |string| Id of the player within the operator’s system. | Required |
| hash       |string| Hash code of request.                                                                                                                                                                                                                                      | Required |
| token      |string| Token of the player from Authenticate response. | Optional |

### Examples

METHOD

``` http
POST
```

URL

``` http
https://<API URL>/V4/sessionexpired?MEMB_ID=<Partner ID>&HASH=<TOKEN>
```

HEADER

``` http
Content-Type: application/json
{
 "providerId": "luckymonaco"
 "sessionId": "6fd2d6f3bb8f4c5a9fadf15d81206af2"
 "playerId": "123456"
 "hash": "c46d5b113e81d30 6831a06765e12067f"
}
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