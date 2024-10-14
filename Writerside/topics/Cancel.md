# Cancel

Transaction will be cancelled when an error occurs during an API integration.

## Requested 

### Parameters

| Name         | Data Type | Description                                                                     | Remark   |
|:-------------|:---------:|:--------------------------------------------------------------------------------|----------|
| uuid         |string| A unique ID for each request                                                    | Required |
| userId       |  string   | Player's ID, specified by Partner when creating a game session.                 | Required |
| gameId       |  string   | Id of the game.                                                                 | Required |
| gamename     |  string   | name of the game.                                                               | Required |
| reference    |  string   | Unique reference of this transaction.                                           | Required |
| providerId   |  string   | Game Provider id.                                                               | Required |
| currency     |string| Currency of the player                                                          | Required |
| sessionId        |string| Player’s game session id on Lucky Monaco system.                                 | Required |            

### Example of URL

``` http
https://<API URL>/Cancel
```

### Example of HTTP BODY

``` json
{
    "providerId": "<luckymonaco>",
    "sessionId": "<Sesseion ID>",
    "userId": "<User ID>",
    "currency" : "USD"
    "gameId": "Im_tumblefortune",
    "gamename": "tumblefortune",
    "reference": "585c1306f89c56f5ecfc2f5d",
    "uuid": "<Unique Request ID>"
}
```

## Response from partner

### Parameters 2

|Name|Data Type| Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
|:---|:---:|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|status|string| * "success" is a default value. <br/>If the response status is a non-200 HTTP response, it will  be considered as an error.<br/>* A non-200 HTTP response is a TEMPORARY_ERROR.<br/>* If the format of HTTP response does not match, it will be considered as a TEMPORARY_ERROR.<br/>* Any values that are not included in the list will be cosidered as an UNKNOWN_ERROR. |
|uuid|string| A unique ID for each response                                                                                                                                                                                                                                                                                                                                                                                                                                                 |

### Example of HTTP BODY 2

``` json
{
    "error": "0"
    "status": "success",
    "uuid": "<Unique response ID>"
}
```
