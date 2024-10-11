# Get Casino Currency

## Overview
Using this method Casino Operator will get the game currency from LuckyMonaco to proceed a specific game.

## API URL

Requested get casino currency URL will be notified individually, for security reasons.

###  Request parameters

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
https://<API URL>/V4/getcasinocurrency?MEMB_ID=<securelogin>&HASH=<TOKEN>
```

HEADER

``` http
Content-Type: application/json
```

## Successful response

### Response parameters

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

