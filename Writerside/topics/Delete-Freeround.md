# Cancel Free Rounds

## Overview

Using this method Operator can cancel an existing Free Rounds Bonus in the Lucky Monaco system. Free Rounds will be canceled in the Lucky Monaco system regardless of whether the player started to play them or not.

## API URL
Requested cancel free round API URL will be notified individually, for security reasons.

### Parameters
| Name           | Data Type | Description                                                                  | Required |
|:---------------|:---------:|:-----------------------------------------------------------------------------|----------|
| hash           |  string   | Hash code of the request                                                     | Required |
| secureLogin       |  string   |User name for authentication in the Casino Game API service                                        | Required |
| bonuscode      |  string   | Bonus id within the Casino Operator’s system.                                | Required |


### Example of URL

``` http
https://<API URL>/api/cancel.php?MEMB_ID=<securelogin>&HASH=<TOKEN>
```

### Example of HTTP BODY

``` json
{
        "bonus_code": "43f4a26e-6da6-496e-9754-0d6c13a19df7"
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

```
