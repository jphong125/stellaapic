# Refund (Reserved for future development)

## Overview
Lucky Monaco system may use this method to rollback a bet transaction on the Casino Operator side, in order to reverse
the transaction and adjust player’s balance. 
When receive a Refund request Operator have to return money back to player’s  balance.

- Important: The call is idempotent, i.e. sending refund for existing bet again only creates one transaction.

- Important: If bet transaction is not found then nothing should happen on the Casino Operator side and success (0)
or specific error code for this situation should be returned.

## API URL

Requested "Refund" win API URL will be notified individually, for security reasons.

### Parameters

| Name         | Data Type | Description                                                              | Required |
|:-------------|:---------:|:-------------------------------------------------------------------------|----------|
| secureLogin  |string| User name for authentication in the Casino Game API service              | Required |
| userId       |  string   | Player's ID, specified by Partner when creating a game session.          | Required |
| reference    |  string   | Unique reference of this transaction.                                    | Required |
| providerId   |  string   | Game Provider id.                                                        | Required |
| gameId       |  string   | Id of the game.                                                          | Optional |
| roundId      |  string   | Id of the round.                                                         | Optional |
| timestamp    |  string   | Date and time when the transaction is processed on the Lucky Monaco side | Optional |
| roundDetails |  string   | Additional information about the current game round.                     | Optional |
| amount       |  decimal  | Amount to be refunded.                                                   | Optional |
| bonusCode    |  string   | Id of the bonus in Casino Operator system.                               | Optional |              
| platform     |  string   | The platform type (channel) on which the game is played.                 | Optional |
| token        |  string   | Token of the player from Authenticate response.                          | Optional |
| uuid                |  string   | A unique ID for each request                                             | Required |

### Examples

METHOD

``` http
POST
```

URL

``` http
https://<API URL>/V4/Refund
```
HEADER

``` http
Content-Type: application/json
```

### Example of HTTP BODY

``` json
{
    "reference": "585c1306f89c56f5ecfc2f5d",
    "gameId": "Im_60_tumblefortune",
    "providerId": "luckymonaco",
    "userId": "421",
    "uuid": "4a5d375ac1311b04fba2ea66d067b8e5"
}
```

## Response from partner

### Parameters 2

| Name          |Data Type| Description                                                          | Remark   |
|:--------------|:---:|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------|
| transactionId|string| Id of the transaction in wallet.                                                                                                                                                                                                                                                                                                          | Required |
| error |string| error code                   | Required |
| description |string| Response status short description. | Optional |

### Example of HTTP BODY 2

``` json
{
 "transactionId": "<transactionId>",
 "error": "0",
 "description": "Success"
 }

```
