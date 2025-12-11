# Jackpot Winners

## Overview
The Jackpot Winners feed provides information about jackpot winnings including progressive jackpot wins and community share part. An operator will get in the response a list of the winners in JSON format.
Maximal period of Jackpot Winners DataFeeds for which data can be transferred is not more than 30 days

## Request

Requested "Jackpot Winners" API URL will be notified individually, for security reasons.

### Request Parameters

| Name           | Data Type | Description                                                                       | Remark   |
|:---------------|:---------:|:----------------------------------------------------------------------------------|----------|
| uuid           |string| A unique ID for each request                                                      | Required |
| secureLogin    |string| Partner Id for authentication in the Kyren API service           | Required |
| startTimePoint |string| Starting Time point for transferring data period                                                             | Required |
| endTimePoint   |string| Ending Time point for transferring data period                                                            | Required |
| token          |string| Token of the Partner from Authenticate response.                       | Required |

### Examples

METHOD

``` http
POST
```

URL

``` http
https://<API URL>/v4/JackpotFeed/Extended/winners
```
HEADER

``` http
Content-Type: application/json
```

### Example of HTTP BODY

``` json
{
  "secureLogin" : "<partnerId>",
  "startTimePoint" : "1619710210000",
  "endTimePoint" : "1627486210000",
  "token" : "<token>",
  "uuid" : "fSYFZMScpZ01FhR26r59GexREh1xHgEY"
}
```

## Response

Example of successful response from Partner API servers.

### Response Parameters

| Name        |Data Type| Description                                                                                                                                                                                                           | Remark   |
|:------------|:---:|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------|
| winner      |  string   | list of jackpot winners during requested period. See below Winners type description of object in the list                                                                                                             | Required |
| error       |  string   | Code of error.                                                                                                                                                                                                        | Required |
| description |string| Response status short description.                                                                                                                                                                                    | Optional |

#### Type winner

| Name           |Data Type| Description                                                                                                     | Remark   |
|:---------------|:---:|:----------------------------------------------------------------------------------------------------------------|----------|
| jackpotTierdId |  string   | unique identifier of the jackpot Tier within the Kyren system.                                           | Required |
| userId         |  string   | Player unique identifier within Operator system.                                                                | Required |
| winAmount      |  string   | won jackpot amount in player’s currency.                                                                        | Required |
| winDate        |  string   | Jackpot winning type – possible values : <br/> W – standard jackpot winning <br/> WC – community share jackpot winning <br/> NW – non-progressive jackpot winning | Required |
| sessionId      |  string   | Unique number of the play session (game round) in which jackpot was won | Required |
| currency     |string| Currency of the User                                                              | Required |


### Example of Json BODY

``` json
{
  "winners": [
    {"jackpotTierID": "3924",
     "userld": "459",
     "winAmount": "8.60", 
      "winDate": "1620890276322",
      "winType": "W",
      "sessionld": "10293633659602", 
      "currency" : "USD"
    },
    ....
    {
      "jackpotTierlD": "3925",
      "extPlayerlD": "460", 
      "winAmount": "15", 
      "winDate": "1620890648909",  
      "winType": "NW", 
      "sessionID": "10293686600602", 
      "currency": "USD"
    }
  ], 
  "error": "0", 
  "description": "Success"
}
```

