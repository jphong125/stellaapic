# Get Slot Log

## Overview
Method returns the user's slot log.

## API URL
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
| start |     number      | starting index of log                          | Required |
| limit |     number      | Number of logs to obtain (up to 1,000)           | Required |
| uuid                |  string   | A unique ID for each request                                             | Required |

### Example of Request Body

``` json
{
    "start": 100,
    "limit": 1000
    "token": "980d06d3361f1e21a2f1550c6806ef52"
}
```

## Response Example

### Response Parameters

| Name        |    Data Type    | Description                                   | Remark |
|:------------|:---------------:|:----------------------------------------------|--------|
| status      |     string      | OK or Failed                                  |Required |
| uuid                |  string   | A unique ID for each request                  | Required |
| logs        |      array      | log list                                      |Required |
| error       |     string      | error Code                                    |Required |
| description |   string       | Description of the error for troubleshooting. |Required |

Log Detail

| Index |      Name      |    Data Type  |  Description  |
|:-----:|:--------------:|:-------------:|:-------------:|
|   0   |     Index      |    number     |Log Index|
|   1   |     gameId     |  string   |Symbolic unique identifier of the game. |
|   2   |    Currency    |   string   |Currency code (ISO 4217 3-digit code)<br/>Please check SLOT_SPEC document|
|   3   | Betting Amount | string |Betting Amount|
|   4   |   Win Amount   | string|Total Win Amouint|
|   5   |  Jackpot Type  |   string   |Jackpot Name|
|   6   | Jackpot Amount | string |Jackopt Win Amount|


### Success Example

``` json
{
    "error": "0",
    "status": "success",
    "uuid" : "ab64cee3-f73b-4631-9abf-b1a09c1f9c36",
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
            "0.0",
            "0.0",
            "none",
            "0.0"
        ],...
    ]
}
```

