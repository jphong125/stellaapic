# Open History

## Overview
Using this method Casino Operator can get a link to the snapshot page with the game details at the whole round. The method returns URL that contains round id and a one-time password that the game server will use for validation of the request, for the security reason.

## Request
Requested open history API URL will be notified individually, for security reasons.

### Request Parameters

| Name        |Data Type| Description                                                    | Remark   |
|:------------|:---:|:---------------------------------------------------------------|----------|
| secureLogin  |string| partner Id for authentication in the Casino Game API service | Required |
|  userId     |string| Id of the user within the Operator system.                     | Required |
| roundId     |string| Unique identifier of the game round.                           | Required |
| uuid                |  string   | A unique ID for each request                                   | Required |
| token      |string| Token of the Partner from Authenticate response                 | Required |

### Examples

METHOD

``` http
POST
```

URL

``` http
https://<API URL>/history/OpenHistory
```
HEADER

``` http
Content-Type: application/json
```

### Example of HTTP BODY

``` json
{
    "secureLogin": "<partnerId>",
    "userId": "421",
    "roundId": "5108924498",
    "uuid": "980d06d3361f1e21a2f1550c6806ef52",
    "token": "token"
}
```

## Response

Example of successful response from LuckyMonaco API servers.

### Response Parameters
| Name        |Data Type| Description                                  | Remark   |
|:------------|:---:|:---------------------------------------------|----------|
| error       |string| Error code.                                  | Required |
| historyUrl  |string| URL for opening the snapshot page.           | Required |
| description |string| Id of the player within the Operator system. | Required |


### Example of Json BODY

``` json
{
   "error": "0",
   "description": "Success",
   "url":"http://192.168.0.225:5500/?token=84375e07-38c4-443d-9acd-d9e927d1e393"
}
```