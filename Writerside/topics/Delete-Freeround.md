# Cancel Free Rounds

## Overview

Using this method Operator can cancel an existing Free Rounds Bonus in the Kyren system.<br/> Free Rounds will be canceled in the Kyren system regardless of whether the player started to play them or not.

## Request
Requested cancel free round API URL will be notified individually, for security reasons.

### Request Parameters
| Name           | Data Type | Description                                                  | Remark  |
|:---------------|:---------:|:-------------------------------------------------------------|----------|
| uuid                |  string   | A unique ID for each request                                 | Required |
| secureLogin  |string| Partner Id for authentication in the Kyren API service | Required |
| bonuscode      |  string   | Bonus id within the Casino Operator’s system.                | Required |
| token      |string| Token of the Partner from Authenticate response              | Required |
### Examples

METHOD

``` http
POST
```


URL

``` http
https://<API URL>/freeround/cancelFreeRound
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
    "bonuscode": "43f4a26e-6da6-496e-9754-0d6c13a19df7"
}
```

## Response

Example of successful response from Kyren API servers.

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

```
