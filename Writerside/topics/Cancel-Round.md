# Cancel Round

## Overview

CancelRound method initiates a refund request, which the Lucky Monaco system will send to the Operator’s remote wallet.
After  successful refund call the game round will be marked as Cancelled in the Lucky Monaco system.
This method Operator can use any time they want to close player’s round forcefully, due to a retention policy on the
Operator’s system or according to requirements for regulated markets


## API URL

Requested cancel round API URL will be notified individually, for security reasons.

###  Request parameters

| Name         |Data Type| Description                                                                                                                          |  Remark  |
|:-------------|:---:|:-------------------------------------------------------------------------------------------------------------------------------------|:--------:|
| secureLogin  |string| User name for authentacation in the Casino Game API service                                                                          | Required |
| externalPlayerId  |string| Id of the player within the Operator system.                                                                                         | Required |
| gameId       |string| Id of the game. This is optional parameter, which has to be sent by Operator if only the session for specific game should be closed. | Required |
|  roundId |string| Id of the game round to be canceled (play session id).                                                                               | optional |
| hash         |string| Hash code of request.                                                                                                                | Required |
### Examples

METHOD

``` http
POST
```

URL

``` http
https://<API URL>/V4/cancelround?MEMB_ID=<securelogin>&HASH=<TOKEN>
```

HEADER

``` http
Content-Type: application/json
```

## Successful response

### Example of body

``` json
{
  "error": 0,
  "description": "Success"
}
```

