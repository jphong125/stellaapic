# Add Player

Using this method Operator can add players to the existing Free Round Bonus. If player’s account does not exist in the Lucky Monaco system yet, it will be registered automatically.

| Name           | Data Type | Description                                                                                                                              | Required |
|:---------------|:---------:|:-----------------------------------------------------------------------------------------------------------------------------------------|----------|
| hash           |  string   | Hash code of the request                                                                                                                 | Required |
| secureLogin       |  string   | User name for authentication in the Casino Game API service                                                                              | Required |
| playerList        |  string   | List of player id to add to the existing Free Round Bonus, comma separated. This data must be sent as a JSON in the body of the request. | Required |
| bonuscode      |  string   | Bonus id within the Casino Operator’s system.                                                                                            | Required |

### Example of URL

``` http
https://<API URL>/api/add.php?MEMB_ID=<Partner ID>&HASH=<TOKEN>
```

### Example of HTTP BODY

``` json
{
  "playerList": ["449986","450013","450509","437070"] 
}
```

## Response from partner(s)

### Parameters 2

| Name      |Data Type| Description                                                                                                                                                                                                                                                                                                                                          | Required |
|:----------|:---:|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----|
| error |string| Error code.                                                                                                                                                                                                                                                                                                                                          | Required |
| description  |string| Description of the error for troubleshooting.                                                                                                                                                                                                                                                                                                        | Required |

### Example of HTTP BODY 2

``` json
{
    "error": "0",
    "description": "success"


