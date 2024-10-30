# Add Player

## Overview
Using this method Operator can add players to the existing Free Round Bonus. <br/>If player’s account does not exist in the Lucky Monaco system yet, it will be registered automatically.

## Request
Requested add player round API URL will be notified individually, for security reasons.

### Request Parameters
| Name        | Data Type | Description                                                                                                                            | Remark  |
|:------------|:---------:|:---------------------------------------------------------------------------------------------------------------------------------------|----------|
| token      |string| Token of the Partner from Authenticate response                                                                                        | Required |
| secureLogin  |string| partner Id for authentication in the LuckyMonaco API service | Required |
| userList    |  string   | List of user id to add to the existing Free Round Bonus, comma separated. This data must be sent as a JSON in the body of the request. | Required |
| bonuscode   |  string   | Bonus id within the Casino Operator’s system.                                                                                          | Required |
| uuid                |  string   | A unique ID for each request                                                                                                           | Required |

### Examples

METHOD

``` http
POST
```


URL

``` http
https://<API URL>/api/addPlayer
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
