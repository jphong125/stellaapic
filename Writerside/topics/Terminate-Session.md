# Terminate Session

## Overview
Using this method Operator can terminate the current user session and kick him out all


## Request

Requested "Terminate Session" API URL will be notified individually, for security reasons.

###  Request Parameters

| Name         |Data Type| Description                                                                                                                                                                                                                                                |  Remark  |
|:-------------|:---:|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:--------:|
| secureLogin  |string| Partner name for authentication in the Casino Game API service                                                                                                                                                                                                | Required |
| userId     |string| Identifier of the user within the Casino Operator’s system.              | Required |
| token      |string| Token of the Partner from Authenticate response                                                                                                                                                                                                             | Required |
| uuid                |  string   | A unique ID for each request                                             | Required |

### Examples

METHOD

``` http
POST
```

URL

``` http
https://<API URL>/V4/CloseSession
```

HEADER

``` http
Content-Type: application/json
```
### Example of HTTP BODY

``` json
{
    "secureLogin" : "<partnerId>",
    "userId": "tester",
    "token" : "<token>",
    "uuid": "<uuid>"
}
```

##  Response

Example of successful response from LuckyMonaco API servers.

### Response parameters
|Name|Data Type|Description|Remark |
|:---|:---:|:---:|---|
| error  |  string   | code of error                                                   | Required |
| description |decimal| Response status short description. | Optional |

### Example of Json BODY

``` json
{
  "error": 0,
  "description": "Success"
}
```

