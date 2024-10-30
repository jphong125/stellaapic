# Get Round Status

## Overview
Using this method returns the current status of a particular game round. <br/> Using this method Casino Operator can check game rounds recorded on their side and cancel open bets returning money to the player’s balance. <br/> This is used when a bet is successful but the result is not generated in the game DB for any reason. 

## Request
Requested get round status API URL will be notified individually, for security reasons.

### Request Parameters

| Name        |Data Type| Description                                                 | Remark   |
|:------------|:---:|:------------------------------------------------------------|----------|
| secureLogin  |string| partner Id for authentication in the LuckyMonaco API service | Required |
| roundId   |string|  Id of the game round                | Required |
| uuid                |  string   | A unique ID for each request                                             | Required |
| token      |string| Token of the Partner from Authenticate response              | Required |

### Examples

METHOD

``` http
POST
```


URL

``` http
https://<API URL>/history/GetRoundStatus
```

HEADER

``` http
Content-Type: application/json
```

### Example of HTTP BODY

``` json
{
    "secureLogin": "<partnerId>",
    "roundId": "5108924498",
    "uuid": "980d06d3361f1e21a2f1550c6806ef52",
    "token": "token"
}
```

## Response

Example of successful response from LuckyMonaco API servers.

### Response Parameters

| Name        |Data Type| Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 | Remark   |
|:------------|:---:|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------|
| roundId   |string| Id of the game round                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        | Required |
| betAmount   |string| Amount of the bet                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           | Required |
| winAmount   |string| Amount of the winnings.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     | Required |
| roundStatus  |string| Status of the game round <br/>o InProgress – game round was started but not finished yet by the user <br/>o Completed – game round has been completed by the user<br/>o Cancelled – game round has been closed automatically by the game round finalization process<br/>o CompleteInProcess – game round is marked as Completed in the db; BetResult or EndRound requests is in asynchronous transaction queue and the system tries to send it to Operator<br/>o CancelInProcess – game round is marked as Cancelled in the db; Refund is in asynchronous queue and being sent to Operator. | Required |
| currency    |string| Currency of the User.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       | Required |
| error  |string| Error code.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 | Required |
| description         |string| Description of the error for troubleshooting.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               | Required |


### Example of Json BODY

``` json
{
   "error": "0",  
   "description": "Success",
   "currency" : "USD"
   “betAmount”: “10”,
   “winAmount”: “100”,
   “roundStatus”: “completed”

}
```