# SnapShot Integration

## Overview

Provides a way to check game results.

## Usage

You can check game results using Transaction ID.

## API URL

Requested game session API URL will be notified individually, for security reasons.

### Examples

METHOD

``` http
 GET or POST
```

URL

``` http
https://<API URL>/api/snapshot.php?MEMB_ID=<Partner ID>&HASH=<TOKEN>
```

HEADER

``` http
Content-Type: application/json
```

### Request parameters

|Name|Data Type|Description|
|:---|:---:|:---|
|transaction_id|string| Transaction ID passed through bet, win, round API|

### Example of BODY

``` json
{
    "transaction_id" : "fb649639-1d88-4506-98fa-28ec9ce28b93"
}
```

## Successful response

|Name|Data Type|Description|
|:---|:---:|:---|
|url|string| URL where you can check the snapshot|

### Example of BODY 2

``` json

{
    "url": "URL where you can check the snapshot"
}
```

## Failure response

Example of failure response from Kyren API servers.

In case of failure, Kyren servers will return  'HTTP status 4XX' or 'HTTP status 5XX' and following response body.

### Example of BODY 3

``` json
{
    "error": {
        "code": "G.99",
        "message": "System error, should be retried, in case of constant occurrences should be reported to Kyren."
    }
}
```

### Error Codes

Error codes are classified into following categories.

* G - generic failures
* V - validation of input parameters failed

|Code|Description (omitting error codes)|
|:---|:---:|
|G.99|System error, should be retried, in case of constant occurrences should be reported to Kyren.|

Error codes will be additionally updated
