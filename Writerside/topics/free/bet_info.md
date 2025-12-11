# Get Betting Information

## Overview

Obtain a list of available Betting Amounts (in specific Currency) for Free Round for specific slot game.

## Usage

You can get free round betting information by calling the API of the provided address.

## API URL

Requested game session API URL will be notified individually, for security reasons.

### Examples

METHOD

``` http
 POST
```

URL

``` http
https://<API URL>/api/betting_info.php?MEMB_ID=<Partner ID>&HASH=<TOKEN>
```

HEADER

``` http
Content-Type: application/json
```

### Request parameters

|Name|Data Type|Description|
|:---|:---:|:---|
|slot_id|string|slot id|
|currency|string|currency|

### Example of BODY

``` json
{
    "slot_id": "lm_1_pumpkinfarm",
    "currency": "USD"
}
```

## Successful response

|Name|Data Type|Description|
|:---|:---:|:---|
|slot|string|slot id|
|currency|string|currency|
|support_betting|array|List of support betting|

### Example of BODY 2

``` json
{
    "slot": "lm_1_pumpkinfarm",
    "currency": "USD",
    "support_betting": [
        "0.1",
        "0.3",
        "0.5",
        "1",
        "1.5",
        "2",
        "2.5",
        "3",
        "4",
        "5",
        "7.5",
        "10",
        "12.5",
        "15",
        "20",
        "25",
        "30",
        "35",
        "40",
        "50",
        "60",
        "70",
        "80",
        "90",
        "100"
    ]
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
|V.1|Have no Argument|
|V.2|No Support Slot|
|V.3|Slot Not Found|
|V.4|No Support Currency|
|G.99|System error, should be retried, in case of constant occurrences should be reported to Kyren.|

Error codes will be additionally updated
