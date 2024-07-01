# Create Freeround

## Overview

Create a free round.

## Usage

You can create a free round by calling the API of the provided address.

## API URL

Requested game session API URL will be notified individually, for security reasons.

### Examples

METHOD

``` http
 POST
```

URL

``` http
https://<API URL>/api/create.php?MEMB_ID=<Partner ID>&HASH=<TOKEN>
```

HEADER

``` http
Content-Type: application/json
```

### Request parameters

|Name|Data Type|Description|
|:---|:---:|:---|
|user_id|string|Partner user ID|
|currency|string|currency to use|
|betting|string|Bet amount (reference betting table)|
|bonus_code|string|Bonus code determined by the partner|
|rounds_count|number|Total quantity of Free Round to be created to use in designated slot games.<br/><br/>User can play Free Round of their desire combination on any slot games specified here within the "rounds_count".|
|start_timestamp|number|Free spins offer start time(UNIX TIMESTAMP)|
|expiration_timestamp|number|Free spins offer end time(UNIX TIMESTAMP)|
|slot_ids|Array|list of slots(If the bet amount does not match the slot, it is an error)|

### Example of BODY

``` json
{
    "user_id": "godwish",
    "currency": "USD",
    "betting": "1",
    "bonus_code": "43f4a26e-6da6-496e-9754-0d6c13a19df7",
    "rounds_count": 10,
    "start_timestamp": 1713400705,
    "expiration_timestamp": 1713401305,
    "slot_ids": [
        "lm_14_childofsuccess",
        "lm_15_childoffortune"
    ]
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
|V.1|Have no Argument|
|V.2|No Support Slot|
|V.3|Slot Not Found|
|V.4|No Support Currency|
|V.5|No Support Betting|
|G.99|System error, should be retried, in case of constant occurrences should be reported to Lucky Monaco.|

Error codes will be additionally updated
