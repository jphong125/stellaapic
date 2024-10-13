# Health Check

## Overview
HealthCheck method can be used by operators to check if Lucky Monaco provider API service or Game server are live and
ready.

## API URL

Requested healthcheck API URL will be notified individually, for security reasons.


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



## Successful response

### Example of body (API Service HeathCheck)

``` json
http status : 200 OK
{
  "error": 0,
  "description": "Success"
}

```
### Example of body (Game Server HeathCheck)

``` json
http status : 200 OK

```

