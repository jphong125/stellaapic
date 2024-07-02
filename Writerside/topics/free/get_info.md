# Get Freeround Information

## Overview

Get free round information

## Usage

You can get free round information by calling the API of the provided address.

## API URL

Requested game session API URL will be notified individually, for security reasons.

### Examples

METHOD

``` http
 GET or POST
```

URL

``` http
https://<API URL>/api/get_info.php?MEMB_ID=<Partner ID>&HASH=<TOKEN>
```

HEADER

``` http
Content-Type: application/json
```

## Successful response

|Name|Data Type|Description|
|:---|:---:|:---|
|limit_spin|number| Max possible Freeround Count (1~limit_spin)|
|slot|array|List of support slot|
|slot.No|string|slot no|
|slot.Name|string|slot name|
|slot.ID|string|slot game id|
|currency|array|List of support currency|

### Example of BODY

``` json
{
    "slot": [
        {
            "No": "1",
            "Name": "Pumpkin Farm",
            "ID": "lm_1_pumpkinfarm"
        },
        {
            "No": "2",
            "Name": "Kelly's Wheel Double",
            "ID": "lm_2_kellyswheeldouble"
        },...
    ],
    "currency": [
        "IDX",
        "USD",
        "JPY",
        "CNY",
        "RUB",...
    ],
    "limit_spin": 999
}
```

## Failure response

Example of failure response from LuckyMonaco API servers.

In case of failure, LuckyMonaco servers will return  'HTTP status 4XX' or 'HTTP status 5XX' and following response body.

### Example of BODY 2

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
|G.99|System error, should be retried, in case of constant occurrences should be reported to Lucky Monaco.|

Error codes will be additionally updated
