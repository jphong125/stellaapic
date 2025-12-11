# Create Wallet

## Overview
Using this method Casino Operator will create player’s Wallet within the Kyren system. This method should be called
before player is sent to the Kyren’s games.


## Request

Requested Create wallet API URL will be notified individually, for security reasons.

### Request Parameters

| Name        |Data Type| Description                                                    | Remark   |
|:------------|:---:|:---------------------------------------------------------------|----------|
| secureLogin  |string| partner Id for authentication in the Kyren API service | Required |
| userId    |string| Id of the User within the Operator system.                     | Required |
| currency    |string| Currency of the User.                                          | Required |
| uuid        |  string   | A unique ID for each request                                   | Required |
| token       |string| Token of the Partner from Authenticate response                 | Required |

### Examples

METHOD

``` http
POST
```

URL

``` http
https://<API URL>/transfer/CreateWallet
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
    "currency": "USD",
    "uuid": "<uuid>"
}
```

## Response

Example of successful response from Kyren API servers.

###  Response Parameters 

| Name        |Data Type| Description                                      |Remark  |
|:------------|:---:|:-------------------------------------------------|---|
| userId      |string| Id of the player within the Kyren system. |  Required |
| error       |  string   | Code of error.                                   | Required |
| description |string| Response status short description.               | Optional |


### Example of Json BODY

``` json
{
    "error": 0,
    "description": "success",
    "userId": "tester"
}
