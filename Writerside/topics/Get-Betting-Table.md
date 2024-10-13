# Get Betting table

## Overview
Using this method Casino Operator will get the game betting table from LuckyMonaco to proceed a specific game.

## API URL

Requested get betting table API URL will be notified individually, for security reasons.

###  Request parameters

| Name        |Data Type| Description                                                                                                                                                        | Remark |
|:------------|:---:|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------|:---------:|
| secureLogin |string| User name for authentacation in the Casino Game API service                                                                                                        | Required |
| currency    |string| Player’s currency.                                                                                                                                           | Required |
| uuid        |string| A unique ID for each request                                                                                                                                              | Required |
### Examples

METHOD

``` http
POST
```

URL

``` http
https://<API URL>/V4/GetBettingTable
```

HEADER

``` http
Content-Type: application/json
```

## Successful response

###  Response parameters

|     Name     |                | Data Type | Description                        |
|:------------:|:--------------:|:---------:|:-----------------------------------|
|   currency   |                |  string   | Player's ISO 4217 currency code    |
| bettingTable |                |   array   | List of betting table information. |
|              | betting amount |  string   | betting amount    |


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

