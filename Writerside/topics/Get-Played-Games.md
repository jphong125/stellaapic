# Get Played Games

## Overview
Using this method Casino Operator can get a list of the games played by the player during the day.

## Request
Requested "Get Played Game" API URL will be notified individually, for security reasons.

### Request Parameters

| Name        |Data Type| Description                                             | Remark   |
|:------------|:---:|:--------------------------------------------------------|----------|
| secureLogin  |string| Partner Id for authentication in the Kyren API service | Required |
|  userId    |string| Id of the user within the Operator system.              | Required |
| dateplayed  |string| Date, based on the time zone of the user.               | Required |
| timeZone    |string| Time zone of the user. Example: UTC, UTC+8, UTC+04:00   | Required |
| uuid                |  string   | A unique ID for each request                            | Required |
| token      |string| Token of the Partner from Authenticate response         | Required |

### Examples

METHOD

``` http
POST
```


URL

``` http
https://<API URL>/history/GetPlayedGame
```
HEADER

``` http
Content-Type: application/json
```

### Example of HTTP BODY

``` json
{
    "secureLogin": "<partnerId>",
    "token" : "<token>",
    "userId": "421",
    "datePlayed": :2016-12-23",
    "timeZone": "UTC+00:00",
    "uuid": "980d06d3361f1e21a2f1550c6806ef52"
}
```

## Response

Example of successful response from Kyren API servers.

### Response Parameters

| Name                       | Object      | Data Type | Description                                                                                                                   |Remark  |
|:----------------------------|-------------|:---------:|:------------------------------------------------------------------------------------------------------------------------------|---|
| error |             |string|                                                                                                    | Required |
| description |             |string| Description of the error for troubleshooting.                                                                                                                                                                                                                                                                                                        | Required |
| games List of games played |             |   array   | See below GamePlayed type description of the objects in the list.                                                                          | Required |
|                             | gameId      |  string   | Symbolic unique identifier of the game.                                                                                                   |  Required |
|                             | gameName    |  string   | Name of the game. |  Required |




### Example of Json BODY

``` json
{

  "error": 0,
  "description": "Success",
  "games": [

    {

      "gameId": "6_speed_baccarat1",
      "gameName": "SPEEDBACCAT1"
    },
    {

      "gameId": "7_speed_baccarat2",
      "gameName": "SPEEDBACCAT2"
    },
    {

      "gameId": "48_SPEEDBACCAT3",
      "gameName": "SPEEDBACCAT3"
    },
    {

      "gameId": "49_SPEEDBACCAT4",
      "gameName": "SPEEDBACCAT4"
    },
    {

      "gameId": "52_SPEEDBACCAT5",
      "gameName": "SPEEDBACCAT5"
    },
    {

      "gameId": "53_SPEEDBACCAT6",
      "gameName": "SPEEDBACCAT6"
    }
```