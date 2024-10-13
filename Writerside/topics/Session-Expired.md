# Session Expired

## Overview

Using this method the Lucky Monaco system will notify Casino Operator that player’s session has expired in Lucky Monaco
system due to long inactivity or game closing.

The method is optional and is not sent to the Casino Operator by default. In case Casino Operator needs this method to be
sent, they should ask the Lucky Monaco’s Technical Support for additional configuration


## API URL

Requested session expired API URL will be notified individually, for security reasons.

### Request parameters

| Name       |Data Type| Description                                                                                                                                                                                                                                                |  Remark  |
|:-----------|:---:|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:--------:|
| providerId |string| Lucky Monaco provider id in Operator’s system                                                                                                                                                                                                              | Required |
| sessionId  |string| Player’s game session id on Lucky Monaco side                                                                                                                                                                                                              | Required |
| externalPlayerId   |string| Id of the player within the operator’s system. | Required |
| token      |string| Token of the player from Authenticate response                                                                                                                                            | Required |
| sessionId        |string| Player’s game session id on Lucky Monaco system.                       | Required |

### Examples

METHOD

``` http
POST
```

URL

``` http
https://<API URL>/V4/SessionExpired
```

HEADER

``` http
Content-Type: application/json
```
``` http
{
 "providerId": "luckymonaco"
 "sessionId": "6fd2d6f3bb8f4c5a9fadf15d81206af2"
 "externalPlayerId": "123456"
 "token" : "fSYFZMScpZ01FhR26r59GexREh1xHgEY"
}
```

## Response

### Example of body

``` json
{
  "error": 0,
  "description": "Success"
}
```

