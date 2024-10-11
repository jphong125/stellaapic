# Get Betting Table (FreeRound)

## Overview
Get a list of possible bet amounts for a specific game for a specific currency

## API URL
Requested get betting table(for free round) API URL will be notified individually, for security reasons. 

### Parameters

| Name        |Data Type| Description                                                 | Remark   |
|:------------|:---:|:------------------------------------------------------------|----------|
| secureLogin |string| User name for authentication in the Casino Game API service | Required |
| slot_id     |string| slot id | Required |
| currency    |string| currency | Required |
| hash        |string| Hash code of request.                                       | Required |

### Example of URL

``` http
https://<API URL>/api/betting_info.php?MEMB_ID=<securelogin>&HASH=<TOKEN>
```
### Example of HTTP BODY

``` json
{
    "slot_id": "lm_1_pumpkinfarm",
    "currency": "USD"
}
```


## Response from partner

### Parameters 2

| Name            |Data Type| Description                                                                                                                   | Required |
|:----------------|:---:|:------------------------------------------------------------------------------------------------------------------------------|---|
| slot_id         |string| slot id | Required |
| currency        |string| currency | Required |
| support_betting |string| List of support betting                                       | Required |



### Example of HTTP BODY 2

``` json
{
    "slot": "lm_1_pumpkinfarm",
    "currency": "USD",
    "support_betting": [
        "0.1",
        "0.3",
        "0.5",
        "1",
        "1.5",
        "2",
        "2.5",
        "3",
        "4",
        "5",
        "7.5",
        "10",
        "12.5",
        "15",
        "20",
        "25",
        "30",
        "35",
        "40",
        "50",
        "60",
        "70",
        "80",
        "90",
        "100"
    ]
}
```