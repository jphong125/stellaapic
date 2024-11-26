# Session Expired  (Reserved for future development)0

## Overview

Using this method the Lucky Monaco system will notify Casino Operator that player’s session has expired in Lucky Monaco
system due to long inactivity or game closing.

The method is optional and is not sent to the Casino Operator by default. In case Casino Operator needs this method to be
sent, they should ask the Lucky Monaco’s team member when performing the integration.


## Request

Requested "Session Expired" API URL will be notified individually, for security reasons.

### Request parameters

| Name       |Data Type| Description                                   |  Remark  |
|:-----------|:---:|:----------------------------------------------|:--------:|
| providerId |  string   | Game Provider id.                                                                                                                    | Required |
| sessionId  |string| User’s game session id on Lucky Monaco side   | Required |
| userId   |string| Id of the User within the operator’s system.  | Required |
| uuid                |  string   | A unique ID for each request                  | Required |

### Examples

METHOD

``` http
POST
```

URL

``` http
https://<API URL>/v4/SessionExpired
```

HEADER

``` http
Content-Type: application/json
```
### Example of request BODY

``` http
{
 "providerId": "Luckymonaco",
 "sessionId": "6fd2d6f3bb8f4c5a9fadf15d81206af2",
 "userId": "123456",
 "uuid": "4a5d375ac1311b04fba2ea66d067b8e5"
}
```
## Response

Example of successful response from Partner API servers.

## Response parameters

| Name  |Data Type| Description                        |Remark  |
|:------|:---:|:-----------------------------------|----------|
| error |string| Error code.                        | Required |
| description |string| Response status short description. | Optional |

### Example of Json BODY

``` json
{
  "error": 0,
  "description": "Success"
}
```

