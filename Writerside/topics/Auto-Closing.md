# Auto Closing

## Overview
Using this method the Lucky Monaco system will send to Casino Operator for closing the pending winning result of a bet.<br/> **The Casino Operator
will change the balance of the player in accordance with this request and return the updated balance.**

**This method does not require a separate API construction.** It is sent to the result API. The reason for displaying it separately is to explain the process of how to terminate an incomplete round.

Result request may contain a prize that the player is awarded with during the game round, if there is an active promotional
campaigns.

Important : The call is idempotent, i.e. sending result again with the same reference number creates only one
transaction.

Important : This is executed when the game is abnormally disconnected, the user does not check the results of the game within **24 hours**, and fails to end the round.<br/> This status is marked as CompleteInProcess. <br/>
CompleteInProcess : game round is marked as Completed in the db, Result or EndRound requests is in asynchronous transaction queue and the system tries to send it to Operator

## Request

Requested "Result" API URL will be notified individually, for security reasons. (Using same requested "result")

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


### Parameters  (Reserved for future development)

|Name|Data Type| Description                                                  | Remark   |
|:---|:---:|:-------------------------------------------------------------|----------|
| bonusCode         |  string   | Id of the bonus in Casino Operator system.                                  | Optional |
| promoWinAmount    |  string   | Prize amount that the player is awarded with during a promotional campaign. | Optional |
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
https://<API URL>/V4/Result
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
    "currency": "USD",
    "amount": 10.0,
    "roundDetails": "spin",
    "roundid" : "5103188801",
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
| transactionId |string| Id of the transaction in wallet.   | Required |
| currency      |string| Currency of the User.              | Required |
| cash          |decimal| Real balance of the User.          | Required |
| error  |  string   | code of error                      | Required |
| description |decimal| Response status short description. | Optional |

### Response Parameters  (Reserved for future development)

|Name|Data Type| Description                | Remark   |
|:---|:---:|:---------------------------|----------|
| bonus         |decimal| Bonus balance of the User. | Required |


### Example of Json BODY

``` json
{
 "transactionId": "<transactionId>",
 "currency": "USD",
 "cash": 99899.99,
 "error": 0,
 "description": "Success"
 }

```
