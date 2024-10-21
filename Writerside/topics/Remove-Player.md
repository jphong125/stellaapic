# Remove Player

## Overview
Using this method Operator can remove players from the existing Free Round Bonus and cancel free rounds awarded to them. <br/> The  bonus will be canceled for a particular player even in case the player had started playing free rounds.

## Request
Requested remove player API URL will be notified individually, for security reasons.

### Request Parameters
| Name        | Data Type | Description                                                                                                                              | Remark  |
|:------------|:---------:|:-----------------------------------------------------------------------------------------------------------------------------------------|----------|
| secureLogin      |string| Partner name for authentication in the Casino Game API service | Required |
| token      |string| Token of the Partner from Authenticate response              | Required |
| uuid        |  string   | A unique ID for each request                                             | Required |
| userList    |  string   | List of player id to add to the existing Free Round Bonus, comma separated. This data must be sent as a JSON in the body of the request. | Required |
| bonuscode   |  string   | Bonus id within the Casino Operator’s system.                                                                                            | Required |

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
  "secureLogin" : "<partnerId>",
  "token" : "<token>",
  "uuid": "<uuid>",
  "userList": ["449986","450013","450509","437070"],
  "bonuscode": "43f4a26e-6da6-496e-9754-0d6c13a19df7" 
}
```

## Response

Example of successful response from LuckyMonaco API servers.

### Response Parameters

| Name      |Data Type| Description                                                                                                                                                                                                                                                                                                                                          | Remark  |
|:----------|:---:|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----|
| error |string| Error code.                                                                                                                                                                                                                                                                                                                                          | Required |
| description  |string| Description of the error for troubleshooting.                                                                                                                                                                                                                                                                                                        | Required |

### Example of Json BODY

``` json
{
    "error": "0",
    "description": "success"
}
```
