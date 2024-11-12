# Promo Win (Reserved for future development)

## Overview
Using this method the Lucky Monaco system will notify Casino Operator about winning that the player is awarded as a 
result of a campaign that is finished.<br/> 
Notification is asynchronous and may come to the operator with a short delay after 
the campaign is over. <br/>
Operator should handle the transaction in their system and send promowin transactionid back to
the  Lucky Monaco.

Important : The call is idempotent, i.e. sending result again with the same reference number creates only one
transaction.

## Request

Requested "Promo win" API URL will be notified individually, for security reasons.

### Request Parameters

| Name              | Data Type | Description                                                              | Remark  |
|:------------------|:---------:|:-------------------------------------------------------------------------|----------|
| uuid              |string| A unique ID for each request.                                            | Required |
| userId            |  string   | user's ID, specified by Partner when creating a game session.            | Required |
| amount            |  decimal  | Prize amount that the player is awarded with.                            | Required |
| reference         |  string   | Unique reference of this transaction.                                    | Required |
| providerId        |  string   | Game Provider id.                                                        | Required |
| timestamp         |  string   | Date and time when the transaction is processed on the Lucky Monaco side | Required |
| promoCampaignId   |  string   | Id of the campaign.                                                      | Required | 
| promoCampaignType |  string   | Type of the campaign.                                                    | Required |
| currency          |  string   | User’s currency.                                                         | Required |

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
    "amount": "500.0",
    "providerId": "Luckymonaco",
    "userId": "421",
    "promoCampaignType" : "T"
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
