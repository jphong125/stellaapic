# Promo Win (Reserved for future development)

## Overview
Using this method the Pragmatic Play system will notify Casino Operator about winning that the player is awarded as a result of a campaign that is finished. Notification is asynchronous and may come to the operator with a short delay after the campaign is over. Operator should handle the transaction in their system and send promo win transaction id back to the Lucky Monaco

Important: The call is idempotent, i.e. sending result again with the same reference number creates only one transaction. For retries actual player's balance should be returned

Important: This call is also used for notification about the FSB as Prize winnings from prize drops or tournament.

Important: The call is also used for notification about community jackpot winnings. In case Casino Operator would like to receive the CJP value also (in the campaignType parameter), they should ask the Lucky Monaco's Technical Support for additional configuration.

## Request

Requested "Promo win" API URL will be notified individually, for security reasons.

### Request Parameters

| Name         | Data Type | Description                                                                                                     | Remark   |
|:-------------|:---------:|:----------------------------------------------------------------------------------------------------------------|----------|
| uuid         |string| A unique ID for each request.                                                                                   | Required |
| providerId   |  string   | Game Provider id.                                                                                               | Required |
| timestamp    |  string   | Date and time when the transaction is processed on the Lucky Monaco side                                        | Required |
| userId       |  string   | user's ID, specified by Partner when creating a game session.                                                   | Required |
| campaignId   |  string   | Id of the campaign.                                                                                             | Required |
| campaignType |  string   | Type of the campaign. <br/>T-Tournament  <br/> CJP - Community Jackpot <br/> CB - Cashback                      | Required |
| amount       |  decimal  | Prize amount that the player is awarded with.  The prize amount must be added to the player's cash balance.                                                                 | Required |
| reference    |  string   | Unique reference of this transaction.                                                                           | Required |
| currency     |  string   | User’s currency.                                                                                                | Required |
| roundId      |  string   | Id of the round. Id of the round (the last round in Tournaments achievement which leads to changing the scores) | Optional |
| gameId       |  string   | Id of the game.                                                                                                 | Required |
| dataType     |  string   | Portfolio type of promo campaign                                                                                | Optional |

### Examples

METHOD

``` http
POST
```

### Example of URL

``` http
https://<API URL>/v4/PromoWin
```
HEADER

``` http
Content-Type: application/json
```

### Example of HTTP BODY

``` json
{
    "campaignId" : "5103188801"
    "reference": "585c1306f89c56f5ecfc2f5d",
    "amount": "500.0",
    "providerId": "Luckymonaco",
    "userId": "421",
    "campaignType" : "T"
    "currency": "USD"
    "uuid": "4a5d375ac1311b04fba2ea66d067b8e5"
    "timestamp": "1482429190374"
}
```

## Response

Example of successful response from Partner API servers.

### Response Parameters 

| Name          |Data Type| Description                                          | Remark  |
|:--------------|:---:|:-----------------------------------------------------|-----|
| transactionId |string| Id of the transaction within Casino Operator system. | Required |
| currency      |string| Currency of the player.                              | Required |
| cash          |decimal| Real balance of the player.                          | Required |
| bonus         |decimal| Bonus balance of the player.                         | Required |
| error  |  string   | Code of error                                        | Required |
| description |string| Response status short description.                   | Optional |

### Example of Json BODY

``` json
{
 "transactionId": "<transactionId>",
 "currency": "USD",
 "cash": "99899.99",
 "bonus": "99.99",
 "error": 0,
 "description": "Success"
 }

```
