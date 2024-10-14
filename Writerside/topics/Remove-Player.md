# Remove Player

## Overview
Using this method Operator can remove players from the existing Free Round Bonus and cancel free rounds awarded to them. The  bonus will be canceled for a particular player even in case the player had started playing free rounds.

## API URL
Requested remove player API URL will be notified individually, for security reasons.

### Parameters
| Name           | Data Type | Description                                                                                                                              | Required |
|:---------------|:---------:|:-----------------------------------------------------------------------------------------------------------------------------------------|----------|
| uuid                |  string   | A unique ID for each request                                             | Required |
| secureLogin       |  string   | User name for authentication in the Casino Game API service                                                                              | Required |
| playerList        |  string   | List of player id to add to the existing Free Round Bonus, comma separated. This data must be sent as a JSON in the body of the request. | Required |
| bonuscode      |  string   | Bonus id within the Casino Operator’s system.                                                                                            | Required |

### Examples

METHOD

``` http
POST
```


### Example of URL

``` http
https://<API URL>/api/removePlayer
```


HEADER

``` http
Content-Type: application/json
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
}
```
