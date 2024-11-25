# Start Demo Game

## Overview
In order to connect to servers, creates a demo game session for users.

After requesting "Start Demo" with individually notified API URL, API servers will respond accordingly.

Redirect a user to received demo game session URL to entering to LuckyMonaco system.

## Request

Requested "Start Demo" API URL will be notified individually, for security reasons.

## Request for a Start Demo game

Requesting "Start Demo" to LuckyMonaco API Servers.

### Request Parameters

| Name         |Data Type| Description                                                            |  Remark  |
|:-------------|:---:|:-----------------------------------------------------------------------|:--------:|
| secureLogin  |string| Partner Id for authentication in the LuckyMonaco API service           | Required |
| token      |string| Token of the Partner from Authenticate response.                       | Required |
| gameId       |string| Symbolic unique identifier of the game within the Lucky Monaco system. | Required |
| uuid         |string| A unique ID for each request.                                          | Required |

### Examples

METHOD

``` html
POST
```

URL

``` html
https://<API URL>/api/v4/StartDemo
```

HEADER

``` html
Content-Type: application/json
```
### Example of HTTP BODY

``` json
{
    "secureLogin" : "<partnerId>",
    "token" : "<token>",
    "gameId" : "lm_9_roadtomysticoz",
    "uuid" : "fSYFZMScpZ01FhR26r59GexREh1xHgEY"
}
```

## Response

Example of successful response from LuckyMonaco API servers. Use URL parameters.

### response parameter
|Name|Data Type|            Description             |Remark |
|:---|:---:|:----------------------------------:|---|
| error  |  string   |           Code of error.           | Required |
| description |string| Response status short description. | Optional |
|url|string|    Used for player redirection.    | Required|

### Example of Json BODY

``` json
{

  "error": 0,
  "description": "Success",
  "url": "http://192.168.0.227/game/index_3.html?token=af7f54f4-cd53-4c94-92eb-5de9cca86a47"
}
```

