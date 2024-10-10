# Get Betting table

## Overview

Retrieve the game betting table from LuckyMonaco to proceed a specific game.

## Usage

Game Currency can be retrieved as per your request through individual API URL.

## API URL

Requested game session API URL will be notified individually, for security reasons.

Request parameters

| Name        |Data Type| Description                                                                                                                                                        | Remark |
|:------------|:---:|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------|:---------:|
| secureLogin |string| User name for authentacation in the Casino Game API service                                                                                                        | Required |
| currency    |string| Player’s currency.                                                                                                                                           | Required |
| hash        |string| Hash code of request.                                                                                                                                              | Required |
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

|        Name         |                | Data Type | Description                        |
|:-------------------:|:--------------:|:---------:|:-----------------------------------|
|      Currency       |                |  string   | Player's ISO 4217 currency code    |
|    Betting table    |                |   array   | List of betting table information. |
|                     | betting amount |  string   | betting amount    |


### Example of body

``` json
{

  "error": 0,
  "description": "Success",
  "currency": "USD",
  "bettingtable": [
   "0.1", "0.3", "0.5", "1", "1.5", "2", "2.5", "3", "4", "5", "7.5", 
   "10", "12.5", "15", "20", "25", "30", "35", "40", "50", "60", "70", 
   "80", "90", "100" 
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

