# Promo Win

## Overview
Using this method the Lucky Monaco system will notify Casino Operator about winning that the player is awarded as a 
result of a campaign that is finished. Notification is asynchronous and may come to the operator with a short delay after 
the campaignisover.Operatorshouldhandlethetransactionintheirsystemandsendpromowintransactionidbackto
the  Lucky Monaco.

Important:The call is idempotent, i.e. sending result again with the same reference number creates only one
transaction.

## API URL

Requested promo win API URL will be notified individually, for security reasons.

### Parameters

| Name         | Data Type | Description                                                                 | Required |
|:-------------|:---------:|:----------------------------------------------------------------------------|----------|
| hash         |  string   | Hash code of the request                                                    | Required |
| userid       |  string   | Player's ID, specified by Partner when creating a game session.             | Required |
| amount       |  decimal  |  Prize amount that the player is awarded with.                                                         | Required |
| reference    |  string   | Unique reference of this transaction.                                       | Required |
| providerId   |  string   | Game Provider id.                                                           | Required |
| timestamp    |  string   | Date and time when the transaction is processed on the Lucky Monaco side    | Required |
| campaignId   |  string   | Id of the campaign.                         | Required | 
| campaignType |  string   |  Type of the campaign.                         | Required |
| currency     |  string   |   Player’s currency.                         | Required |


### Example of URL

``` http
https://<Partner website(Domain)/promowin?authToken=<TOKEN>
```

### Example of HTTP BODY

``` json
{
    "campaignId" : "5103188801"
    "reference": "585c1306f89c56f5ecfc2f5d",
    "amount": 500.0,
    "providerId": "luckymonaco",
    "userId": "421",
    "campaignType" : "T"
    "currency": "USD"
    "hash": "4a5d375ac1311b04fba2ea66d067b8e5"
    "timestamp": "1482429190374"
}
```

## Response from partner(s)

### Parameters 2

| Name          |Data Type| Description                                                                                                                                                                                                                                                                                                                               | Required |
|:--------------|:---:|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----|
| transactionId |string| Id of the transaction in wallet.                                                                                                                                                                                                                                                                                                          | Required |
| currency      |string| Currency of the player. | Required |
| cash          |decimal| Currency of the player.                                                                                                                                                                                                                                                                                                                   | Required |
| bonus         |decimal| Bonus balance of the player.                                                                                                                                                                                                                                                                                                               | Required |


### Example of HTTP BODY 2

``` json
{
 "transactionId": 1482429190474,
 "currency": "USD",
 "cash": 99899.99,
 "bonus": 99.99,
 "error": 0,
 "description": "Success"
 }

```
