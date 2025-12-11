# Get a list of games

## Overview

Retrieve the game list from Kyren to proceed a specific game.

## Usage

Game list can be retrieved as per your request through individual API URL.

## API URL

Requested game session API URL will be notified individually, for security reasons.

| Name                  |Data Type|Description|
|:----------------------|:---:|:---|
| [Gametype](define.md) |string|Types of game (I.e. slot or table game)|

### Examples

METHOD

``` http
POST
```

URL

``` http
https://<API URL>/api/gamelist?MEMB_ID=<Partner ID>&HASH=<TOKEN>
```

HEADER

``` http
Content-Type: application/json
```

## Successful response for getting Game List ( response )

|         Name          |                     |Data Type| Description                                                                                         |
|:---------------------:|:-------------------:|:-------:|:----------------------------------------------------------------------------------------------------|
| [Gametype](define.md) |                     | string  | Types of game (I.e. slot or table game)                                                             |
|       Gamelist        |                     |  array  | List of game information                                                                            |
|                       | [gameid](define.md) | string  | "Gameid" is a unique ID for each games, you can find from separately provided "SLOT_SPEC" document. |
|                       |      gameName       | string  | Game Title(English)                                                                                 |
|                       |      icon_url       | string  | URL for gaming icons                                                                                |

### Example of body

``` json
{
    "gametype" : "slot",
    "gamelist" : [
        {
            "gameid": "lm_8_treasureofzeus",
            "gameName": "Treasure of Zeus",
            "icon_url": "https://cdn.lmgamelab/Images/8.png"
        }
    ],
    ...
}
```

## Failure response for getting Game List ( response ) 

Example of failure response from Kyren API servers.

In case of failure, Kyren servers will return  'HTTP status 4XX' or 'HTTP status 5XX' and following response body.

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
