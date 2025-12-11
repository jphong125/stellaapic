# User Balance

## Overview
Obtains the user's possession of a specific currency (include both fiat or crypto).

## Usage
You can obtain the amount of the desired currency (include both fiat or crypto) by calling the URL provided by Kyren.

## API URL
For security reasons, we will notify you individually.

## Request Example

METHOD

``` http
 POST
```

URL

``` http
https://<API URL>/user/balance?partner_id=<Partner ID>&token=<TOKEN>
```

HEADER

``` http
Content-Type: application/json
```

### Request Parameters

| Name     | Data Type  | Description                         |
|:---------|:----------:|:------------------------------------|
| id       | string(32) | User ID                             |
| currency | string(4)  | Currency code (ISO 4217 3-digit code)<br/>Please check SLOT_SPEC document                            |
| uuid     | string(36) | A unique ID for each request(uuid4) |

### Example of Request Body

``` json
{
    "id": "tester",
    "currency": "USD",
    "uuid" : "ab64cee3-f73b-4631-9abf-b1a09c1f9c36"
}
```

## Response Example

### Response Parameters

| Name                | Data Type | Description                          |
|:--------------------|:---------:|:-------------------------------------|
| status              |  string   | OK or Failed                         |
| uuid(36)            |  string   | A unique ID for each response(uuid4) |
| balance         |  string(decimal)   | reserves (Decimal)                        |
| code(Failed only)   |  number   | Failed Code                          |
| reason(Failed only) |  number   | Error Reason                         |

### Success Example

``` json
{
    "status": "OK",
    "uuid" : "ab64cee3-f73b-4631-9abf-b1a09c1f9c36"
    "balance" : "100.0"
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