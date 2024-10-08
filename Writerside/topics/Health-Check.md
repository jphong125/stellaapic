# Health Check

## Overview

HealthCheck method can be used by operators to check if Lucky Monaco provider API service or Game server are live and
ready.

## Usage

Health Check can be executed as per your request through individual API URL.

## API URL

Requested game session API URL will be notified individually, for security reasons.


### Examples

METHOD

``` http
POST
```

URL

``` http
https://<API-service-domain>/V4/health/heartbeatcheck?MEMB_ID=<Partner ID>&HASH=<TOKEN>
```

``` http
https://<game-server-domain>/V4/livetest?MEMB_ID=<Partner ID>&HASH=<TOKEN>
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

## Failure response for getting Game List ( response )

Example of failure response from LuckyMonaco API servers.

In case of failure, LuckyMonaco servers will return  'HTTP status 4XX' or 'HTTP status 5XX' and following response body.

### Example of body2

``` json
{
    "error": {
        "code": "G.1",
        "message": "INVALID GAME TYPE"
    }
}
```

### Error codes

Error codes are classified into following categories.

* G - Generic failures
* V - Validation of input parameters failed

|Code|Description (omitting error codes)|
|:---|:---:|
|G.01|Invalid game type|

Error codes will be additionally updated

Start typing here...
Start typing here...Start typing here...Start typing here...