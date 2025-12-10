# Active Jaclpots

## Overview
Active Jackpots feed provides information about open jackpots and their open tiers (progressive) per casino brand. Operator will get in the response a list of the open jackpots including detailed info about their open/active (not won) tiers in JSON format. Information about non-progressive (multiplier) tiers is not displayed in this feed. <br/>
**Important : In case there are no active jackpots according to the given criteria, an empty list is returned in the response.**

## Request

Requested "Active Jackpot" API URL will be notified individually, for security reasons.

### Request Parameters

| Name         | Data Type | Description                                                                       | Remark   |
|:-------------|:---------:|:----------------------------------------------------------------------------------|----------|
| uuid         |string| A unique ID for each request                                                      | Required |
| secureLogin  |string| Partner Id for authentication in the LuckyMonaco API service           | Required |
| currency     |string| Currency of the User                                                              | Required |
| token      |string| Token of the Partner from Authenticate response.                       | Required |

### Examples

METHOD

``` http
POST
```

URL

``` http
https://<API URL>/v4/JackpotFeed/Extended/jackpots
```
HEADER

``` http
Content-Type: application/json
```

### Example of HTTP BODY

``` json
{
  "secureLogin" : "<partnerId>",
  "token" : "<token>",
  "uuid" : "fSYFZMScpZ01FhR26r59GexREh1xHgEY"
}
```

## Response

Example of successful response from Partner API servers.

### Response Parameters

| Name          |Data Type| Description                                                                                                                                                                                                                                                                                                                                             | Remark   |
|:--------------|:---:|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------|
| mainjackpotId |  string   | Unique identifier (parent/main) of the jackpot within Lucky Monaco system.                                                                                                                                                                                                                                                                              | Required |
| name          |  string   | name of the Jackpot.                                                                                                                                                                                                                                                                                                                                    | Required |
| level         |  string   | level of the jackpot <br/> G – Global jackpot (reserved future) <br/> N – network jackpot (reserved future) <br/> O – Jackpot for particular Operation (reserved future) <br/>B – jackpot for particular casino Brand                                                                                                                                | Required |
| games         |  string   | The list of games participating in the Jackpot. It contains gameId (game symbols), comma separated. Example : lm_6_kittyinthebasket.                                                                                                                                                                                                                    | Required |
| status        |  string   | Current status of the Jackpot. Possible value : <br/> A - Active <br/> S - Shutdowned                                                                                                                                                                                                                                                                   | Required |
| tiersNumber   |  string   | Parameter indicating the total number of progressive (active and won) configured for a Jackpot. For single-tire jackpots the value “1” will be specified. The non-progressive tier should not be included                                                                                                                                               | Required |
| tiersName     |  string   | Displays the name that appears in the game UI for a specific tier.                                                                                                                                                                                                                                                                                      | Required |
| amount        |  string   | jackpot fund (for specific tier) for the moment of request, in USD by default. Or values can be returned in the request currency.                                                                                                                                                                                                                                                                                   | Required |
| error         |  string   | Code of error.                                       | Required |
| description   |string| Response status short description.                   | Optional |
#### Type Tiers
This list displays information only for active/open (not won) progressive tiers. Information about non-progressive (multiplier) tiers is not displayed in the list

| Name           |Data Type| Description                                                                                                                                                                                                                                                                                                                                                  | Remark   |
|:---------------|:---:|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------|
| jackpotTierdId |  string   | unique identifier of the jackpot Tier within the Lucky Monaco system.                                                                                                                                                                                                                                                                                        | Required |
| Tier           |  string   | jackpot tier name identifier. The tier index (0-7) that operator receives in API should be mapped with the appropriate tier in the game : <br/> 0 - the 1st tier (the lowest) <br/> 1 - the 2st tier <br/> 2 - the 3st tier <br/> 3 - the 4st tier <br/> 4 - the 5st tier <br/> 5 - the 6st tier <br/> 6 - the 7st tier <br/> 7 - the 8st tier (the highest) | Required |


### Example of Json BODY

``` json
{
  "jackpot" : [
    {
      "mainJackpotId" : "456",
      "name" : "test_name", 
      "level" : "B", 
      "games" : "lm_1_SPEEDBACCAT1", 
      "status" : "A", 
      "tiersNumber" : "4", 
      "tiers" : [
        {
          "jackpotId" : "456",
          "tier" : "0",
          "TiersName" : "0.1%pot",
          "amount" : "10"},
        ....
        {
          "jackpotId" : "460",
          "tier" : "1", 
          "TiersName" : "0.5%pot", 
          "amount" : "200"}]}
  ],
  "error" : "0", 
  "description": "successs"
}
```

### In case there are no active jackpots : 
``` json
{
  "winners" : [ ],
  "error" : "0", 
  "description": "successs"
}
```