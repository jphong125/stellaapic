# User Info

## Overview
유저 정보를 얻어온다.

## Usage
럭키모나코에서 제공하는 URL을 호출하여 특정 유저의 정보를 얻어올 수 있다.
해당 api를 호출하면 지갑별 보유 금액을 얻을 수 있다.

## API URL
보안상의 이유로 개별 통보해 드립니다.

## Request Example

METHOD

``` http
 POST
```

URL

``` http
https://<API URL>/user/info?partner_id=<Partner ID>&token=<TOKEN>
```

HEADER

``` http
Content-Type: application/json
```

### Request Parameters

| Name     | Data Type  | Description                         |
|:---------|:----------:|:------------------------------------|
| id       | string(32) | User ID                             |
| uuid     | string(36) | A unique ID for each request(uuid4) |

### Example of Request Body

``` json
{
    "id": "tester",
    "uuid" : "random generated uuid4"
}
```

## Response Example

### Response Parameters

| Name                 |       | Data Type  | Description                          |
|:--------------------|:----------:|:-------------------------------------|
| status              | |   string   | OK or Failed                         |
| uuid(36)            | |   string   | A unique ID for each response(uuid4) |
| name(32)            | |   string   | User Name                            |
| at_create           | |   string   | at create (yyyy-MM-dd HH:mm:ss)      |
| at_login            | |   string   | at login (yyyy-MM-dd HH:mm:ss)       |
| wallet              | | dictionary | wallets       |
|                     |currency code|string|balance of currency|
| code(Failed only)   | |   number   | Failed Code                          |
| reason(Failed only) | |   number   | Error Reason                         |

### Success Example

``` json
{
    "status": "OK",
    "uuid" : "random generated uuid4",
    "namme" : "kim test",
    "at_create" : "2024-07-02 11:50:12"
    "at_login" : "2024-07-02 12:10:32"
    "wallet" : {
        "USD" : "100.0",
        "CNY" : "1023"
    }
}
```

### Failed Example

``` json
{
    "status": "Failed",
    "uuid" : "random generated uuid4",
    "code" : 1,
    "reason" : "Invalid Parameter"
}
````