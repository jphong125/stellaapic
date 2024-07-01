# Get a list of games

## Overview

Retrieve the game list from LuckyMonaco to proceed a specific game.

## Usage

Game list can be retrieved as per your request through individual API URL.

## API URL

Requested game session API URL will be notified individually, for security reasons.

| Name                |Data Type|Description|
|:--------------------|:---:|:---|
| [gametype](define.md)|string|Types of game (I.e. slot or table game)|

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

| Name                       |Data Type|Description|
|:---------------------------|:---:|:---|
| [gametype](define.md)      |string|Types of game (I.e. slot or table game)|
| gamelist                   |array|List of game information|
| [gamelist.gameid](define.md)|string|string|"gameid" is a unique ID for each games, you can find from separately provided "SLOT_SPEC" document.|
| gamelist.gamename          |string|Game Title(English)|
| gamelist.icon_url          |string|URL for gaming icons|

### Example of BODY

``` json
{
    "gametype" : "slot",
    "gamelist" : [
        {
            "gameid": "pc_1001_rising_fortune",
            "gamename": "Rising Fortune",
            "icon_url": "https://cdn.LuckyMonaco/Images/1001.png"
        }
    ],
    ...
}
```

## Failure response for getting Game List ( response ) 

Example of failure response from LuckyMonaco API servers.

In case of failure, LuckyMonaco servers will return  'HTTP status 4XX' or 'HTTP status 5XX' and following response body.

### Example of BODY2

``` json
{
    "error": {
        "code": "G.1",
        "message": "INVALID GAME TYPE"
    }
}
```

### Error Codes

Error codes are classified into following categories.

* G - generic failures
* V - validation of input parameters failed

|Code|Description (omitting error codes)|
|:---|:---:|
|G.01|Invalid game type|

Error codes will be additionally updated
