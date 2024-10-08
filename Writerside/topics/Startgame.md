# Start game


## Overview

In order to connect to servers, creates a game session for users.

## Usage

After requesting a game session with individual notified API URL, API servers will respond accordingly.

Redirect a user to received game session URL for entering LuckyMonaco.

## API URL

Requested game session API URL will be notified individually, for security reasons.

## Request for a start game 

Requesting a game session to LuckyMonaco API Servers.

### Request parameters

| Name             |Data Type| Description                                                            |  Remark  |
|:-----------------|:---:|:-----------------------------------------------------------------------|:--------:|
| secureLogin      |string| User name for authentacation in the Casino Game API service            | Required |
| hash             |string| Hash code of request.                                                  | Required |
| externalPlayerId |string| Unique identifier of the player within the Casino Operator system.     | Required |
| externalNickname |string| Nickname of the player within the Casino Operator system.              | Required |
| gameid           |string| Symbolic unique identifier of the game within the Lucky Monaco system. | Required |
| sessionid        |string| Player’s game session id on Lucky Monaco system.                       | Required |
| laguage          |string| Language on which the game should be opened.                           | Required |
| currency         |string| Currency of the player.                                                | Required |
| region           |string| The region where the player is located. (select "Asia" or "Europe")    | Required |
| cashierURL       |string| an URL for opening the Operator’s website Cashier page.                | optional |
| lobbyURL         |string| an URL for opening the Operator’s website lobby page.                  | optional |

### Examples

METHOD

``` html
POST
```

URL

``` html
https://<API URL>/api/startgame?MEMB_ID=<Partner ID>&HASH=<TOKEN>
```

HEADER

``` html
Content-Type: application/json
```

## Successful response 

Example of successful response from LuckyMonaco API servers. Use URL parameters.


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

## Failure response for a game session ( response )

Example of failure response from LuckyMonaco API servers.

In case of failure, LuckyMonaco servers will return  'HTTP status 4XX' or 'HTTP status 5XX' and following response body.

### Example of BODY

``` json
{
    "errors": {
        "code": "G.0",
        "message": "Could not authenticate, please review sent data and try again. If problem persists, contact customer support "
    }
}
```

### Error Codes

Error codes are classified into following categories.

* G - generic failures
* V - validation of input parameters failed

|Code|Description (omitting error codes)|
|:---|:---:|
|G.01|System error, should be retried, in case of constant occurrences should be reported to LuckyMonaco.|

Error codes will be additionally updated
Start typing here...