# Get Round Status

## Overview
Method returns the current status of a particular game round. Using this method Casino Operator can check game rounds recorded on their side and cancel open bets returning money to the player’s balance.

## Request
Requested get round status API URL will be notified individually, for security reasons.

### Request Parameters

| Name        |Data Type| Description                                                 | Remark   |
|:------------|:---:|:------------------------------------------------------------|----------|
| secureLogin |string| User name for authentication in the Casino Game API service | Required |
| roundId   |string|  Id of the game round                | Required |
| uuid                |  string   | A unique ID for each request                                             | Required |
| token      |string| Token of the player from Authenticate response              | Required |

### Examples

METHOD

``` http
POST
```


URL

``` http
https://<API URL>/GetRoundStatus
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
    "uuid": "980d06d3361f1e21a2f1550c6806ef52"
}
```

## Response

Example of successful response from LuckyMonaco API servers.

### Response Parameters

| Name        |Data Type| Description                                                 | Remark   |
|:------------|:---:|:------------------------------------------------------------|----------|
| roundId   |string|  Id of the game round                | Required |
| betAmount   |string|  Amount of the bet               | Required |
| winAmount   |string|  Amount of the winnings.               | Required |
| roundStatus  |string|  Status of the game round               | Required |
| error  |string|  Error code.               | Required |
| description         |string| Description of the error for troubleshooting.                                    | Required |


### Example of response BODY

``` json
{
   "error": "0",
   “bet”: “10”,
   "description": "OK",
   “winAmount”: “100”,
   “roundstatus”: “completed”

}
```