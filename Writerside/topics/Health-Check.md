# Health Check

## Overview
HealthCheck method can be used by operators to check if Lucky Monaco provider API service or Game server are live and
ready.

## API URL

Requested health check API URL will be notified individually, for security reasons.


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

### Example of body (API Service HeathCheck)
| Name  |Data Type| Description                  | Required |
|:------|:---:|:-----------------------------|----------|
| error |string| error code                   | Required |
| description |string| Response status short description. | Optional |

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

