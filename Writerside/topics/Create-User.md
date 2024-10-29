# Create User

## Overview
Using this method Casino Operator will create player’s account within the Lucky Monaco system. This method should be called
before player is sent to the Lucky Monaco’s games.


## Request

Requested Create User API URL will be notified individually, for security reasons.

### Request Parameters

| Name         |Data Type| Description                                                  | Remark   |
|:-------------|:---:|:-------------------------------------------------------------|----------|
| secureLogin  |string| partner Id for authentication in the Casino Game API service | Required |
| userId       |string| Id of the User within the Operator system.                   | Required |
| userNickname |string| nickname of the User within the Operator system.             | Optional |
| uuid         |  string   | A unique ID for each request                                 | Required |
| token        |string| Token of the Partner from Authenticate response              | Required |

### Examples

METHOD

``` http
POST
```

URL

``` http
https://<API URL>/transfer/CreateUser
```

HEADER

``` http
Content-Type: application/json
```

### Example of HTTP BODY

``` json
{
    "secureLogin" : "<partnerId>",
    "token" : "<token>",
    "userId": "tester",
    "userNickname": "tester1",
    "uuid": "<uuid>"
}
```

## Response

Example of successful response from LuckyMonaco API servers.

###  Response Parameters 

| Name        |Data Type| Description                                    | Remark  |
|:------------|:---:|:-----------------------------------------------|---|
| userId      |string| Id of the User within the Operator system. |  Required |
| error       |  string   | code of error.                                 | Required |
| description |decimal| Response status short description.             | Optional |


### Example of Json BODY

``` json
{
    "error": 0,
    "description": "success",
    "userId": "tester"
}
