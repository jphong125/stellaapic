# Promo Win (Reserved for future development)

## Overview
Using this method the Lucky Monaco system will notify Casino Operator about winning that the player is awarded as a 
result of a campaign that is finished. 
Notification is asynchronous and may come to the operator with a short delay after 
the campaign is over.
Operator should handle the transaction in their system and send promowin transactionid back to
the  Lucky Monaco.

Important : The call is idempotent, i.e. sending result again with the same reference number creates only one
transaction.

## API URL

Requested "Promo win" API URL will be notified individually, for security reasons.

### Parameters

| Name         | Data Type | Description                                                                 | Required |
|:-------------|:---------:|:----------------------------------------------------------------------------|----------|
| uuid         |string| A unique ID for each request                                                                                                                                              | Required |
| userId       |  string   | Player's ID, specified by Partner when creating a game session.             | Required |
| amount       |  decimal  |  Prize amount that the player is awarded with.                                                         | Required |
| reference    |  string   | Unique reference of this transaction.                                       | Required |
| providerId   |  string   | Game Provider id.                                                           | Required |
| timestamp    |  string   | Date and time when the transaction is processed on the Lucky Monaco side    | Required |
| campaignId   |  string   | Id of the campaign.                         | Required | 
| campaignType |  string   |  Type of the campaign.                         | Required |
| currency     |  string   |   Player’s currency.                         | Required |

### Examples

METHOD

``` http
POST
```

### Example of URL

``` http
https://<API URL>/V4/PromoWin
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
    "amount": 500.0,
    "providerId": "Luckymonaco",
    "userId": "421",
    "campaignType" : "T"
    "currency": "USD"
    "uuid": "4a5d375ac1311b04fba2ea66d067b8e5"
    "timestamp": "1482429190374"
}
```

## Response from partner

### Parameters 2

| Name          |Data Type| Description                                                                                                                                                                                                                                                                                                                               | Required |
|:--------------|:---:|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----|
| transactionId |string| Id of the transaction in wallet.                                                                                                                                                                                                                                                                                                          | Required |
| currency      |string| Currency of the player. | Required |
| cash          |decimal| Real balance of the player.                                                                                                                                                                                                                                                                                                                    | Required |
| bonus         |decimal| Bonus balance of the player.                                                                                                                                                                                                                                                                                                               | Required |
| eroor  |  string   | code of error                                                   | Required |
| description |decimal| Response status short description. | Optional |

### Example of HTTP BODY 2

``` json
{
 "transactionId": "<transactionId>",
 "currency": "USD",
 "cash": 99899.99,
 "bonus": 99.99,
 "error": 0,
 "description": "Success"
 }

```
