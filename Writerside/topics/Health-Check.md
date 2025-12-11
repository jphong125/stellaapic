# Health Check

## Overview
HealthCheck method can be used by operators to check if Kyren provider API service.

## Request

Requested "Health Check" API URL will be notified individually, for security reasons.

### Request Parameters

| Name       |Data Type| Description                                                  |  Remark  |
|:-----------|:---:|:-------------------------------------------------------------|:--------:|
| secureLogin  |string| Partner Id for authentication in the Kyren API service | Required |
| token      |string| Token of the Partner from Authenticate response              | Required |
| uuid                |  string   | A unique ID for each request                                 | Required |

### Examples

METHOD

``` http
POST
```

URL

``` http
https://<API URL>/v1/HealthCheck
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
    "uuid": "<uuid>"
}
```



## Response 

Example of successful response from Kyren API servers.

### Response parameters
| Name  |Data Type| Description                        | Remark  |
|:------|:---:|:-----------------------------------|----------|
| error |string| Error code                         | Required |
| description |string| Response status short description. | Optional |

### Example of Json BODY (API Service HeathCheck)

``` json

{
  "error": 0,
  "description": "Success"
}

```

