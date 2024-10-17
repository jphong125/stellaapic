# Create FreeRound

## Overview
Using this method, the operator can create a new free round bonus with the Lucky Monaco system. In case of network failure, the operator can send a repeated free round creation request. 
The Lucky Monaco system will not create a new FR bonus if there is an active FR bonus with the same bonus code.

## Request
Requested create free round API URL will be notified individually, for security reasons.

### Request Parameters
| Name           | Data Type | Description                                                                  | Remark  |
|:---------------|:---------:|:-----------------------------------------------------------------------------|----------|
| secureLogin      |string| User name for authentication in the Casino Game API service | Required |
| token      |string| Token of the player from Authenticate response              | Required |
| uuid           |  string   | A unique ID for each request                                             | Required |
| userId         |  string   | Player ID in Casino Operator’s system                                        | Required |
| currency       |  string   | currency                                                                     | Required |
| betvalues      |  string   | values of bet                                                                | Required |
| bonuscode      |  string   | Bonus id within the Casino Operator’s system.                                | Required |
| rounds         |  string   | Numbers of free round                                                        | Required |
| startdate      |  decimal  | Date and time when free rounds bonus will start                              | Required |
| expirationDate |  string   | Date and time when the bonus gets invalid and is unavailable for the player. | Required |
| gamelist       |  string   | List of the games associated with the bonus                                  | Required |

### Examples

METHOD

``` http
POST
```


URL

``` http
https://<API URL>/api/createFreeround
```

HEADER

``` http
Content-Type: application/json
```

### Example of HTTP BODY

``` json
{
    "userId": "tester",
    "currency": "USD",
    "betvalues": "1",
    "bonuscode": "43f4a26e-6da6-496e-9754-0d6c13a19df7",
    "rounds": 10,
    "startdate": 1713400705,
    "expirationdate": 1713401305,
    "gamelist": [
        "lm_14_childofsuccess",
        "lm_15_childoffortune"
    ]
}
```

## Response

Example of successful response from LuckyMonaco API servers.

### Response Parameters

| Name      |Data Type| Description                                                                                                                                                                                                                                                                                                                               | Remark  |
|:----------|:---:|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----|
| bonuscode |string| Bonus id within the Casino Operator’s system.                                                                                                                                                                                                                                                                                                         | Required |

### Example of response BODY

``` json
{
     "bonuscode": "43f4a26e-6da6-496e-9754-0d6c13a19df7"
 }

```
