# Create Wallet

## Overview
Using this method Casino Operator will create player’s Wallet within the Lucky Monaco system. This method should be called
before player is sent to the Lucky Monaco’s games.


## API URL

Requested Create wallet API URL will be notified individually, for security reasons.

### Parameters

| Name             |Data Type| Description                                                 | Remark   |
|:-----------------|:---:|:------------------------------------------------------------|----------|
| secureLogin      |string| User name for authentication in the Casino Game API service | Required |
| PlayerId |string| Id of the player within the Operator system.                | Required |
| currency         |string| Currency of the player.           | Required |
| uuid                |  string   | A unique ID for each request                                             | Required |

### Examples

METHOD

``` http
POST
```

URL

``` http
https://<API URL>/createwallet
```
HEADER

``` http
Content-Type: application/json
```

### Example of HTTP BODY

``` json
{
    "playerid": "tester",
    "currency": "USD",
    "uuid": "<uuid>"
}
```

## Response from partner

### Parameters 2

| Name     |Data Type| Description                                      | Required |
|:---------|:---:|:-------------------------------------------------|---|
| playerid |string| Id of the player within the Lucky Monaco system. |  Required |



### Example of HTTP BODY 2

``` json
{
    "error": "0",
    "description": "success",
    "playerId": "64749175",
}
