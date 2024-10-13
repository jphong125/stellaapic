# Start game

## Overview
In order to connect to servers, creates a game session for users.

After requesting start game with individual notified API URL, API servers will respond accordingly.

Redirect a user to received game session URL for entering LuckyMonaco.

## API URL

Requested start game API URL will be notified individually, for security reasons.

## Request for a start game 

Requesting start game to LuckyMonaco API Servers.

### Request parameters

| Name         |Data Type| Description                                                            |  Remark  |
|:-------------|:---:|:-----------------------------------------------------------------------|:--------:|
| secureLogin  |string| User name for authentacation in the Casino Game API service            | Required |
| uuid         |string| A unique ID for each request                                                                                                                                              | Required |
| UserId       |string| Unique identifier of the player within the Casino Operator system.     | Required |
| UserNickname |string| Nickname of the player within the Casino Operator system.              | Optional |
| gameId       |string| Symbolic unique identifier of the game within the Lucky Monaco system. | Required |
| sessionId    |string| Player’s game session id on Lucky Monaco system.                       | Required |
| language     |string| Language on which the game should be opened.                           | Required |
| currency     |string| Currency of the player.                                                | Required |
| region       |string| The region where the player is located. (select "Asia" or "Europe")    | Optional |
| cashierURL   |string| an URL for opening the Operator’s website Cashier page.                | optional |
| lobbyURL     |string| an URL for opening the Operator’s website lobby page.                  | optional |

### Examples

METHOD

``` html
POST
```

URL

``` html
https://<API URL>/api/V4/StartGame
```

HEADER

``` html
Content-Type: application/json
```

## Successful response 

Example of successful response from LuckyMonaco API servers. Use URL parameters.

### response parameter
|Name|Data Type|Description|
|:---|:---:|:---:|
|url|string|used for player redirection.|

### Example of response BODY

``` json
{

  "error": 0,
  "description": "Success",
  "url": "http://192.168.0.227/game/index_3.html?token=af7f54f4-cd53-4c94-92eb-5de9cca86a47"
}
```

