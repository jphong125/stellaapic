# Get Casino Currency




## Overview

Retrieve the game Currency from LuckyMonaco to proceed a specific game.

## Usage

Game Currency can be retrieved as per your request through individual API URL.

## API URL

Requested game session API URL will be notified individually, for security reasons.

Request parameters

| Name        |Data Type| Description                                                                                                                                                        | Remark |
|:------------|:---:|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------|:---------:|
| secureLogin |string| User name for authentacation in the Casino Game API service                                                                                                        | Required |
| hash        |string| Hash code of request.                                                                                                                                              | Required |
### Examples

METHOD

``` http
POST
```

URL

``` http
https://<API URL>/V4/getcasinocurrency?MEMB_ID=<Partner ID>&HASH=<TOKEN>
```

HEADER

``` http
Content-Type: application/json
```

## Successful response for getting Language List

Response parameters

|     Name      |          | Data Type | Description                         |
|:-------------:|:--------:|:---------:|:------------------------------------|
| Currency list |          |   array   | List of Currency information.       |
|               | Currency |  string   | Player's ISO 4217 currency code |


### Example of body

``` json
{

  "error": 0,
  "description": "Success",
  "CurrencyList": [

    "KRW",
    "USD"
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

