# Get Betting Table

## Overview

Retrieve the game Betting Table for Specific currency  from LuckyMonaco to proceed a specific game.

## Usage

Betting Table can be retrieved as per your request through individual API URL.

## API URL

Requested game session API URL will be notified individually, for security reasons.

Request parameters

| Name        |Data Type| Description                                                 | Remark |
|:------------|:---:|:------------------------------------------------------------|:---------:|
| secureLogin |string| User name for authentacation in the Casino Game API service | Required |
| gameid      |string| Id of game                                                  | Required |
| currency    |string| Supported currency of game                                  | Required |
| hash        |string| Hash code of request.                                       | Required |
### Examples

METHOD

``` http
POST
```

URL

``` http
https://<API URL>/V4/getbettingtable?MEMB_ID=<Partner ID>&HASH=<TOKEN>
```

HEADER

``` http
Content-Type: application/json
```

## Successful response for getting Language List

Response parameters

|     Name      |         | Data Type | Description                        |
|:-------------:|:-------:|:---------:|:-----------------------------------|
|    gameid     |         |  string   | Id of game                         |
|   currency    |         |  string   | Supported currency of game         |
| Betting Table |         |   array   | List of betting table information. |
|               | betting |  string   | List of betting range              |


### Example of body

``` json
{

  "error": 0,
  "description": "Success",
  "currency": "USD",
  "betting table": [
    "0.1",
    "0.3",
    "0.5",
    "1",
    "100"
  ]
}
```

## Failure response for getting Game List ( response )

Example of failure response from LuckyMonaco API servers.

In case of failure, LuckyMonaco servers will return  'HTTP status 4XX' or 'HTTP status 5XX' and following response body.

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

Start typing here...
Start typing here...Start typing here...