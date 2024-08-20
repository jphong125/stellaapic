# Delete Freeround

This will delete the created Free Round
In case if the player has already consumed it, or the created Free Round has passed it expiration, system will not return any message regarding such status.

## Overview

Delete a previously provided free round

## Usage

You can remove the free round by calling the API of the provided address.

## API URL

Requested game session API URL will be notified individually, for security reasons.

### Examples

METHOD

``` http
 POST
```

URL

``` http
https://<API URL>/api/delete.php?MEMB_ID=<Partner ID>&HASH=<TOKEN>
```

HEADER

``` http
Content-Type: application/json
```

### Request parameters

|Name|Data Type|Description|
|:---|:---:|:---|
|bonus_code|string|Bonus code requested|

### Example of BODY

``` json
{
    "bonus_code": "43f4a26e-6da6-496e-9754-0d6c13a19df7"
}
```

## Successful response

|Name|Data Type|Description|
|:---|:---:|:---|
|bonus_code|string|Bonus code requested|

### Example of BODY 2

``` json
{
    "bonus_code": "43f4a26e-6da6-496e-9754-0d6c13a19df7"
}
```

## Failure response

Example of failure response from LuckyMonaco API servers.

In case of failure, LuckyMonaco servers will return  'HTTP status 4XX' or 'HTTP status 5XX' and following response body.

### Example of BODY 3

``` json
{
    "error": {
        "code": "G.99",
        "message": "System error, should be retried, in case of constant occurrences should be reported to Lucky Monaco."
    }
}
```

### Error Codes

Error codes are classified into following categories.

* G - generic failures
* V - validation of input parameters failed

|Code|Description (omitting error codes)|
|:---|:---:|
|G.9|System error, should be retried, in case of constant occurrences should be reported to Lucky Monaco.|
|G.99|System error, should be retried, in case of constant occurrences should be reported to Lucky Monaco.|

Error codes will be additionally updated
