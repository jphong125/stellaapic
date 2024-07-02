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
https://<API URL>/slot_log/get?partner_id=<Partner ID>&token=<TOKEN>
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

| Name                | Data Type | Description                          |
|:--------------------|:---------:|:-------------------------------------|
| status              |  string   | OK or Failed                         |
| uuid(36)            |  string   | A unique ID for each response(uuid4) |
| currency |    string(4)    | Currency code (ISO 4217 3-digit code)<br/>Please check SLOT_SPEC document |
| balance         |  string(decimal)   | 보유금 (Decimal)                        |
| amount   | string(decimal) | 늘릴 보유량                                                                    |
| code(Failed only)   |  number   | Failed Code                          |
| reason(Failed only) |  number   | Error Reason                         |

### Success Example

``` json
{
    "status": "OK",
    "uuid" : "ab64cee3-f73b-4631-9abf-b1a09c1f9c36",
    "currency": "USD",
    "amount" : "200.0",
    "balance" : "100.0"
}
```

### Failed Example

``` json
{
    "status": "Failed",
    "uuid" : "ab64cee3-f73b-4631-9abf-b1a09c1f9c36",
    "code" : 3,
    "reason" : "Not Enough Balance"
}
````