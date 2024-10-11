# Get Round Status

## Overview
Method returns the current status of a particular game round. Using this method Casino Operator can check game rounds recorded on their side and cancel open bets returning money to the player’s balance.

## API URL
Requested get round status API URL will be notified individually, for security reasons.

### Parameters

| Name        |Data Type| Description                                                 | Remark   |
|:------------|:---:|:------------------------------------------------------------|----------|
| secureLogin |string| User name for authentication in the Casino Game API service | Required |
| roundId   |string|  Id of the game round                | Required |
| hash        |string| Hash code of request.                                       | Required |

### Example of URL

``` http
https://<API URL>/getroundstatus?authToken=<TOKEN>
```

### Example of HTTP BODY

``` json
{
    "secureLogin": "username"
    "roundId": "5108924498"
    "hash": "980d06d3361f1e21a2f1550c6806ef52"
}
```

## Response from partner

### Parameters 2

| Name        |Data Type| Description                                                 | Remark   |
|:------------|:---:|:------------------------------------------------------------|----------|
| roundId   |string|  Id of the game round                | Required |
| betAmount   |string|  Amount of the bet               | Required |
| winAmount   |string|  Amount of the winnings.               | Required |
| roundStatus  |string|  Status of the game round               | Required |
| error  |string|  Error code.               | Required |
| description         |string| Description of the error for troubleshooting.                                    | Required |


### Example of HTTP BODY 2

``` json
{
   "error": "0",
   “bet”: “10”,
   "description": "OK",
   “winAmount”: “100”
   “roundstatus”: “completed”

}
```