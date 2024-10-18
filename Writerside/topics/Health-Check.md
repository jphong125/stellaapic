# Health Check

## Overview
HealthCheck method can be used by operators to check if Lucky Monaco provider API service or Game server are live and
ready.

## Request

Requested "Health Check" API URL will be notified individually, for security reasons.

### Request Parameters

| Name       |Data Type| Description                                                                                                                                                                                                                                                |  Remark  |
|:-----------|:---:|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:--------:|
| secureLogin  |string| User name for authentication in the Casino Game API service                                                                                                                                                                                                | Required |
| token      |string| Token of the player from Authenticate response                                                                                                                                                                                                             | Required |
| uuid                |  string   | A unique ID for each request                                             | Required |

### Examples

METHOD

``` http
POST
```

URL

``` http
https://<API-service-domain>/V4/Check
```

``` http
https://<game-server-domain>/V4/Check
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

Example of successful response from LuckyMonaco API servers.

### Response parameters
| Name  |Data Type| Description                  | Remark  |
|:------|:---:|:-----------------------------|----------|
| error |string| error code                   | Required |
| description |string| Response status short description. | Optional |

### Example of Json BODY (API Service HeathCheck)

``` json
http status : 200 Success
{
  "error": 0,
  "description": "Success"
}

```
### Example of Json BODY (Game Server HeathCheck)

``` json
http status : 200 Success

```

