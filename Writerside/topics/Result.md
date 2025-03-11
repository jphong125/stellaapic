# Result

## Overview
Using this method the Lucky Monaco system will send to Casino Operator the winning result of a bet. <br /> **The Casino Operator
will change the balance of the player in accordance with this request and return the updated balance.** <br />

Result request may contain a prize that the player is awarded with during the game round, if there is an active promotional 
campaigns or Free Round (FRB). <br /> **If the result parameter value contains a bonusCode, it is a Free Round Result.** The Casino Operator
will change the balance of the player in accordance with this request and return the updated balance. If applicable, Also increase **balance in bonus parameters** (optional for statistics use). <br/> Players connection was lost in any cases so lucky monaco will do retransmission 10 times, then do not receive any result response. <br /> 

Important : The call is idempotent, i.e. sending result again with the same reference number creates only one
transaction.

## Request

Requested "Result" API URL will be notified individually, for security reasons.

### Request Parameters

| Name         | Data Type | Description                                                                               | Remark  |
|:-------------|:---------:|:------------------------------------------------------------------------------------------|----------|
| uuid         |  string   | A unique ID for each request                                                              | Required |
| userId       |  string   | User's ID, specified by Partner when creating a game session.                             | Required |
| gameId       |  string   | Id of the game.                                                                           | Required |
| gameName     |  string   | Name of the game.                                                                         | Required |
| roundId      |  string   | Id of the round.                                                                          | Required |
| amount       |  decimal  | Amount of the bet.                                                                        | Required |
| reference    |  string   | Unique reference of this transaction.                                                     | Required |
| currency     |  string   | Currency of the User.                                                                     | Required |
| providerId   |  string   | Game Provider id.                                                                         | Required |
| timestamp    |  string   | Date and time when the transaction is processed on the Lucky Monaco side.                 | Required |
| roundDetails |   array   | Additional information about the current game round. (ie. "spin", "freespin", "minigame") | Required |
| sessionId    |  string   | User’s game session id on Lucky Monaco system.                                            | Required |
| bonusCode         |  string   | Id of the bonus in Casino Operator system.                                  | Optional |

### Parameters  (Reserved for future development)

| Name              |Data Type| Description                                                  | Remark   |
|:------------------|:---:|:-------------------------------------------------------------|----------|
| promoWinReference |  string   | Unique reference of this transaction.                                       | Optional |
| promoCampaignID   |  string   | Id of the promotional campaign.                                             | Optional |
| promoCampaignType |  string   | Type of the promotional campaign.                                             | Optional |

### Examples

METHOD

``` http
POST
```


### Example of URL

``` http
https://<API URL>/v4/Result
```
HEADER

``` http
Content-Type: application/json
```

### Example of HTTP BODY

``` json
{
    "providerId": "luckymonaco",
    "userId": "421",
    "sessionId": "<sessionId>",
    "currency": "USD",
    "amount": "10.0",
    "roundDetails": "spin",
    "roundId" : "5103188801",
    "reference": "585c1306f89c56f5ecfc2f5d",
    "gameId": "Im_60_tumblefortune",
    "gameName" : "tumblefortune",
    "uuid": "4a5d375ac1311b04fba2ea66d067b8e5",
    "timestamp": "1482429190374"
}
```

## Response

Example of successful response from Partner API servers.

### Response Parameters 

| Name          |Data Type| Description                        | Remark  |
|:--------------|:---:|:-----------------------------------|-----|
| transactionId |string| Id of the transaction within Casino Operator system. | Required |
| currency      |string| Currency of the User.              | Required |
| cash          |decimal| Real balance of the User.          | Required |
| error  |  string   | code of error                      | Required |
| description |string| Response status short description. | Optional |
| bonus         |decimal| Bonus balance of the User. | Optional |

### Example of Json BODY

``` json
{
 "transactionId": "<transactionId>",
 "currency": "USD",
 "cash": "99899.99",
 "error": 0,
 "description": "Success"
 }

```


