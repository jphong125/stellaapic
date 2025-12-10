# Create FreeRound

## Overview
Using this method, the operator can create a new free round bonus with the Stella system.<br/> In case of network failure, the operator can send a repeated free round creation request.<br/> 
The Stella system will not create a new FR bonus if there is an active FR bonus with the same bonus code.

**Expiration date is mandatory. It should be sent as timestamp in seconds, and the bonus validity period must not be longer than 30 days.**

## Request
Requested create free round API URL will be notified individually, for security reasons.

### Request Parameters
| Name           |  Data Type  | Description                                                                                                                                     | Remark  |
|:---------------|:-----------:|:------------------------------------------------------------------------------------------------------------------------------------------------|----------|
| secureLogin    |   string    | Partner Id for authentication in the LuckyMonaco API service                                                                                    | Required |
| token          |   string    | Token of the Partner from Authenticate response                                                                                                 | Required |
| uuid           |   string    | A unique ID for each request                                                                                                                    | Required |
| currency       |   string    | Currency                                                                                                                                        | Required |
| betvalues      |   string    | Values of bet                                                                                                                                   | Required |
| bonuscode      | string (36) | Bonus id within the Casino Operator’s system.                                                                                                   | Required |
| rounds         |   string    | Numbers of free round                                                                                                                           | Required |
| startdate      |   decimal   | Date and time when free rounds bonus will start (i.e. Unix epoch time in milliseconds, for example : 1470926696715)                             | Required |
| expirationdate |   string    | Date and time when the bonus gets invalid and is unavailable for the player. (i.e. Unix epoch time in milliseconds, for example : 1470926696715 | Required |
| gamelist       |   string    | List of the games associated with the bonus                                                                                                     | Required |

### Examples

METHOD

``` http
POST
```


URL

``` http
https://<API URL>/freeround/createFreeround
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
    "uuid": "<uuid>",
    "currency": "USD",
    "betvalues": "1",
    "bonuscode": "43f4a26e-6da6-496e-9754-0d6c13a19df7",
    "rounds": 10,
    "startdate": 1713400705000,
    "expirationdate": 1713401305000,
    "gamelist": [
        "lm_1_SPEEDBACCART1",
        "lm_2_SPEEDBACCART2"
    ]
}
```

## Response

Example of successful response from LuckyMonaco API servers.

### Response Parameters

| Name      |Data Type| Description                                                                                                                                                                                                                                                                                                                               | Remark  |
|:----------|:---:|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----|
| bonuscode |string| Bonus id within the Casino Operator’s system.                                                                                                                                                                                                                                                                                                         | Required |

### Example of Json BODY

``` json
{
    "error": 0,
    "description": "Success",
    "bonuscode": "43f4a26e-6da6-496e-9754-0d6c13a19df7"
 }

```
