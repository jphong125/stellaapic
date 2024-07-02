# Get SlotLog

## Overview
사용자의 슬롯 로그를 얻어올 수 있습니다.

## Usage
럭키모나코에서 제공하는 URL을 호출하여 슬롯 로그 정보를 얻어올 수 있습니다.

## API URL
보안상의 이유로 개별 통보해 드립니다.

## Request Example

METHOD

``` http
 POST
```

URL

``` http
https://<API URL>/log/slot?partner_id=<Partner ID>&token=<TOKEN>
```

HEADER

``` http
Content-Type: application/json
```

### Request Parameters

| Name  |    Data Type    | Description                         |
|:------|:---------------:|:------------------------------------|
| start |     number      | 로그의 시작 인덱스                          |
| limit |     number      | 얻어올 로그의 개수 (최대 1,000개)              |
| uuid  |   string(36)    | A unique ID for each request(uuid4) |

### Example of Request Body

``` json
{
    "start": 100,
    "limit": 1000
    "uuid" : "ab64cee3-f73b-4631-9abf-b1a09c1f9c36"
}
```

## Response Example

### Response Parameters

| Name                |    Data Type    | Description                          |
|:--------------------|:---------------:|:-------------------------------------|
| status              |     string      | OK or Failed                         |
| uuid(36)            |     string      | A unique ID for each response(uuid4) |
| logs                |      array      | log list                             |
| code(Failed only)   |     number      | Failed Code                          |
| reason(Failed only) |     number      | Error Reason                         |

Log Detail

| Index |      Name      |    Data Type  |  Description  |
|:-----:|:--------------:|:-------------:|:-------------:|
|   0   |     Index      |    number     |Log Index|
|   1   |    Game ID     |  string(32)   |Game ID|
|   2   |    Currency    |   string(4)   |Currency code (ISO 4217 3-digit code)<br/>Please check SLOT_SPEC document|
|   3   | Betting Amount | string(32,18) |Betting Amount|
|   4   |   Win Amount   | string(32,18) |Total Win Amouint|
|   5   |  Jackpot Type  |   string(8)   |Jackpot Name|
|   6   | Jackpot Amount | string(32,18) |Jackopt Win Amount|


### Success Example

``` json
{
    "status": "OK",
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

### Failed Example

``` json
{
    "status": "Failed",
    "uuid" : "ab64cee3-f73b-4631-9abf-b1a09c1f9c36",
    "code" : 3,
    "reason" : "Have No Additional Record"
}
````