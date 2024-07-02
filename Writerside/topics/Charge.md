# Charge Balance

## Overview
사용자의 재화 보유량을 늘려준다.

## Usage
럭키모나코에서 제공하는 URL을 호출하여 원하는 재화의 양을 늘려줄수 있다.

## API URL
보안상의 이유로 개별 통보해 드립니다.

## Request Example

METHOD

``` http
 POST
```

URL

``` http
https://<API URL>/user/charge?partner_id=<Partner ID>&token=<TOKEN>
```

HEADER

``` http
Content-Type: application/json
```

### Request Parameters

| Name     |    Data Type    | Description                                                               |
|:---------|:---------------:|:--------------------------------------------------------------------------|
| id       |   string(32)    | User ID                                                                   |
| currency |    string(4)    | Currency code (ISO 4217 3-digit code)<br/>Please check SLOT_SPEC document |
| amount   | string(decimal) | 늘릴 보유량                                                                    |
| uuid     |   string(36)    | A unique ID for each request(uuid4)                                       |

### Example of Request Body

``` json
{
    "id": "tester",
    "currency": "USD",
    "uuid" : "ab64cee3-f73b-4631-9abf-b1a09c1f9c36",
    "amount" : "200.0"
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
    "balance" : "300.0"
}
```

### Failed Example

``` json
{
    "status": "Failed",
    "uuid" : "ab64cee3-f73b-4631-9abf-b1a09c1f9c36",
    "code" : 2,
    "reason" : "Have no Wallet"
}
````