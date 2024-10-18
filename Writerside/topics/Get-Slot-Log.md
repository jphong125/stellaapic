# Get Slot Log

## Overview
Method returns the user's slot log.

## Request
Requested get round status API URL will be notified individually, for security reasons.

## Request Example

METHOD

``` http
 POST
```

URL

``` http
https://<API URL>/GetSlotLog
```

HEADER

``` http
Content-Type: application/json
```

### Request Parameters

| Name  |    Data Type    | Description                         |Remark |
|:------|:---------------:|:------------------------------------|-----|
| secureLogin |string| User name for authentication in the Casino Game API service | Required |
| userId     |string| Id of the player within the Operator system.                | Required |
| start |     number      | starting index of log                          | Required |
| limit |     number      | Number of logs to obtain (up to 1,000)           | Required |
| uuid                |  string   | A unique ID for each request                                             | Required |
| token      |string| Token of the player from Authenticate response              | Required |

### Example of Request Body

``` json
{
    "secureLogin" : "<partnerId>",
    "userId": "tester",
    "start": 100,
    "limit": 1000
    "token": "980d06d3361f1e21a2f1550c6806ef52"
    "uuid": "<uuid>"
}
```

## Response

Example of successful response from LuckyMonaco API servers.

### Response Parameters

| Name        |    Data Type    | Description                                   | Remark |
|:------------|:---------------:|:----------------------------------------------|--------|
| logs        |      array      | log list                                      |Required |
| error       |     string      | error Code                                    |Required |
| description |   string       | Description of the error for troubleshooting. |Required |

Log Detail

| Index |     Name      |    Data Type  |  Description  |
|:-----:|:-------------:|:-------------:|:-------------:|
|   0   |     index     |    number     |Log Index|
|   1   |    gameId     |  string   |Symbolic unique identifier of the game. |
|   2   |   currency    |   string   |Currency code (ISO 4217 3-digit code)<br/>Please check SLOT_SPEC document|
|   3   | bettingAmount | string |Betting Amount|
|   4   |   winAmount   | string|Total Win Amouint|
|   5   |  jackpotType  |   string   |Jackpot Name|
|   6   | jackpotAmount | string |Jackopt Win Amount|


### Example of Json BODY

``` json
{
    "error": "0",
    "description": "success",
    "logs": [
        [
            100,
            "lm_8_treasureofzeus",
            "USD",
            "10.0",
            "0.0",
            "none",
            "0.0"
        ],
        [
            101,
            "lm_8_treasureofzeus",
            "USD",
            "10.0",
            "0.0",
            "none",
            "0.0"
        ],...
    ]
}
```

