# Open History

## Overview
Using this method Casino Operator can get a link to the page with the game details at the end of the round. The method returns URL that contains round id and a one-time password that the game server will use for validation of the request, for the security reason.

## API URL
Requested open history API URL will be notified individually, for security reasons.

### Parameters

| Name        |Data Type| Description                                                 | Remark   |
|:------------|:---:|:------------------------------------------------------------|----------|
| secureLogin |string| User name for authentication in the Casino Game API service | Required |
| playerId    |string| Id of the player within the Operator system.                | Required |
| roundId     |string| Unique identifier of the game round.                  | Required |
| token      |string| Token of the player from Authenticate response                                                                                                                                            | Required |

### Example of URL

``` http
https://<API URL>/OpenHistory
```

### Example of HTTP BODY

``` json
{
    "secureLogin": "username"
    "playerId": "421"
    "roundId": "5108924498"
    "token": "980d06d3361f1e21a2f1550c6806ef52"
}
```

## Response from partner

### Parameters 2
| Name        |Data Type| Description                                                 | Remark   |
|:------------|:---:|:------------------------------------------------------------|----------|
| error       |string| Error code. | Required |
| historyUrl  |string| URL for opening the game screen page. | Required |
| description |string| Id of the player within the Operator system.                | Required |


### Example of HTTP BODY 2

``` json
{
   "error": "0",
   "description": "OK",
   "url":
   "https://{game_server_domain}/gameHistoryDetailForApi.do?otp=9KngwmdYVw6YLViPVIjU9eEMFslzlALnwtoZygNWTMB7SqAApl8ERLysn7Xp26p0&playSessionId=5108924498"
}
```