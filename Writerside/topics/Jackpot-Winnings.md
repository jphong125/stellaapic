# Jackpot Winnings

## Overview
Jackpot  Winnings  feed  provides  information  on  jackpot  winnings  for  each  jackpot  tier  for  the  entire  jackpot  lifetime, indicating the total number of winnings, as well as the amount and winner of the largest and last winnings.

## Request

Requested "Jackpot Winnings" API URL will be notified individually, for security reasons.

### Request Parameters

| Name           | Data Type | Description                                                                       | Remark   |
|:---------------|:---------:|:----------------------------------------------------------------------------------|----------|
| uuid           |string| A unique ID for each request                                                      | Required |
| secureLogin    |string| Partner Id for authentication in the Kyren API service           | Required |
| mainJackpotId |string| Unique identifier (parent/main) of the Jackpot within Kyren system                                                         | Required |
| currency   |string|  ISO-4217 code currency                                                           | Required |
| token          |string| Token of the Partner from Authenticate response.                       | Required |

### Examples

METHOD

``` http
POST
```

URL

``` http
https://<API URL>/v4/JackpotFeed/Extended/Winnings
```
HEADER

``` http
Content-Type: application/json
```

### Example of HTTP BODY

``` json
{
  "secureLogin" : "<partnerId>",
  "currency" : "EUR",
  "mainJackpotId" : "1234",
  "token" : "<token>",
  "uuid" : "fSYFZMScpZ01FhR26r59GexREh1xHgEY"
}
```

## Response

Example of successful response from Partner API servers.

### Response Parameters

| Name        |Data Type| Description                                                                                                                                                                                                           | Remark   |
|:------------|:---:|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------|
| name        |  string   | Name of the Jackpot                                                                                                           | Required |
| tiers       |  string   | List of tier objects for transferring details for tiers. See below (tiers type) the description of the object in the list                                                                                                          | Required |
| error       |  string   | Code of error.                                                                                                                                                                                                        | Required |
| description |string| Response status short description.                                                                                                                                                                                    | Optional |

#### Type tiers

| Name           |Data Type| Description                                                                                                     | Remark   |
|:---------------|:---:|:----------------------------------------------------------------------------------------------------------------|----------|
| jackpotTierdId |  string   | unique identifier of the jackpot Tier within the Kyren system.                                           | Required |
| Tier           |  string   | jackpot tier name identifier. The tier index (0-7) that operator receives in API should be mapped with the appropriate tier in the game : <br/> 0 - the 1st tier (the lowest) <br/> 1 - the 2st tier <br/> 2 - the 3st tier <br/> 3 - the 4st tier <br/> 4 - the 5st tier <br/> 5 - the 6st tier <br/> 6 - the 7st tier <br/> 7 - the 8st tier (the highest) | Required |
| biggerstWin    |  string   |set of biggest win parameters. See below (biggestWin type) parameters description                                                                     | Required |
| lastWin       |  string   | set of last win parameters. See below (lastWin type) parameters description | Required |

#### Type biggerstWin

| Name           |Data Type| Description                                                                                                     | Remark   |
|:---------------|:---:|:----------------------------------------------------------------------------------------------------------------|----------|
| win Date |  string   | Date and time of the biggest win in the jackpot tier lifetime. (Will be returned as timestamp in milliseconds.)                                           | Required |
| winAmount         |  string   | won jackpot amount in player’s currency | Required |
| biggerstWin    |  string   |set of biggest win parameters. See below (biggestWin type) parameters description                                                                     | Required |
| userID    |  string   | Player unique identifier within Operator system. | Required |
| maskedUserId   |  string   | Identifier of the player (within the casino Operator system) who won the biggest win within the jackpot tier. Is returned in masked view. | Required |

#### Type lastWin

| Name           |Data Type| Description                                                                                                     | Remark   |
|:---------------|:---:|:----------------------------------------------------------------------------------------------------------------|----------|
| win Date |  string   | Date and time of the biggest win in the jackpot tier lifetime. (Will be returned as timestamp in milliseconds.)                                           | Required |
| winAmount         |  string   | won jackpot amount in player’s currency | Required |
| biggerstWin    |  string   |set of biggest win parameters. See below (biggestWin type) parameters description                                                                     | Required |
| userID    |  string   | Player unique identifier within Operator system. | Required |
| maskedUserId   |  string   | Identifier of the player (within the casino Operator system) who won the biggest win within the jackpot tier. Is returned in masked view. | Required |

### Example of Json BODY

``` json
{
  "error": "0",
  "description": "successs",
  "name": "Test Jackpot",
  "tiers": [
    {
      "JackpotTierId": "459",
      "tier": "0",
      "numberofwin": "54",
      "biggestWin": {
        "winDate": "1689404434",
        "winAmount": "50",
        "userId": "456",
        "maskedUserId": "*56*"
      },
      "lastWin": {
        "winDate": "1706261434",
        "winAmount": "20.00",
        "maskedUserId": "**56***"
      }
    },
    .....
    {
      "JackpotTierId": "459",
      "tier": "8",
      "numberofwin": "7",
      "biggestWin": {
        "winDate": "1689404434",
        "winAmount": "20000000.00",
        "userId": "456",
        "maskedUserId": "*56*"
      },
      "lastWin": {
        "winDate": "1706261434",
        "winAmount": "20000000.00",
        "maskedUserId": "**56***"
      }
    }
  ]
}
```

