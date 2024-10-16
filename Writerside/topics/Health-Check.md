# Health Check

## Overview
HealthCheck method can be used by operators to check if Lucky Monaco provider API service or Game server are live and
ready.

## API URL

Requested "Health Check" API URL will be notified individually, for security reasons.

### Request parameters

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



## response 

### Response parameters
| Name  |Data Type| Description                  | Remark  |
|:------|:---:|:-----------------------------|----------|
| error |string| error code                   | Required |
| description |string| Response status short description. | Optional |

### Example of body (API Service HeathCheck)

``` json
http status : 200 Success
{
  "error": 0,
  "description": "Success"
}

```
### Example of body (Game Server HeathCheck)

``` json
http status : 200 Success

```

