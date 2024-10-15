# Session Expired

## Overview

Using this method the Lucky Monaco system will notify Casino Operator that player’s session has expired in Lucky Monaco
system due to long inactivity or game closing.

The method is optional and is not sent to the Casino Operator by default. In case Casino Operator needs this method to be
sent, they should ask the Lucky Monaco’s team member when performing the integration.


## API URL

Requested "Session Expired" API URL will be notified individually, for security reasons.

### Request parameters

| Name       |Data Type| Description                                                                                                                                                                                                                                                |  Remark  |
|:-----------|:---:|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:--------:|
| secureLogin  |string| User name for authentication in the Casino Game API service                                                                                                                                                                                                | Required |
| providerId |string| Lucky Monaco provider id in Operator’s system                                                                                                                                                                                                              | Required |
| sessionId  |string| Player’s game session id on Lucky Monaco side                                                                                                                                                                                                              | Required |
| PlayerId   |string| Id of the player within the operator’s system. | Required |
| token      |string| Token of the player from Authenticate response                                                                                                                                            | Required |
| sessionId        |string| Player’s game session id on Lucky Monaco system.                       | Required |
| token      |string| Token of the player from Authenticate response                                                                                                                                                                                                             | Required |
| uuid                |  string   | A unique ID for each request                                             | Required |

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
 "providerId": "Luckymonaco"
 "sessionId": "6fd2d6f3bb8f4c5a9fadf15d81206af2"
 "PlayerId": "123456"
 "token" : "<token>"
}
```

## Response

| Name  |Data Type| Description                  | Required |
|:------|:---:|:-----------------------------|----------|
| error |string| error code                   | Required |
| description |string| Response status short description. | Optional |

### Example of body

``` json
{
  "error": 0,
  "description": "Success"
}
```

