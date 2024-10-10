# Get Info

You can get information about the free round you can set by making a simple call via URL.

## Requested 

### Parameters

| Name             |Data Type| Description                                                 | Remark   |
|:-----------------|:---:|:------------------------------------------------------------|----------|
| secureLogin      |string| User name for authentication in the Casino Game API service | Required |
| hash             |string| Hash code of request.                                       | Required |

### Example of URL

``` http
https://<API URL>/api/get_info.php?MEMB_ID=<Partner ID>&HASH=<TOKEN>
```


## Response from partner

### Parameters 2

| Name          |Data Type| Description                                                                                                                   | Required |
|:--------------|:---:|:------------------------------------------------------------------------------------------------------------------------------|---|
| limit_spin|number| Max possible Freeround Count (1~limit_spin) | Required |
| slot|array|List of support slot                                                                                                    |  Required |
| slot.No|string|slot no |  Required |
| slot.Name|string|slot name                                                                              |  Required |
|slot.ID|string|slot game id                                                                                                           |  Required |
| currency|array|List of support currency                                                                               |  Required |



### Example of HTTP BODY 2

``` json
{
    "slot": [
        {
            "No": "1",
            "Name": "Pumpkin Farm",
            "ID": "lm_1_pumpkinfarm"
        },
        {
            "No": "2",
            "Name": "Kelly's Wheel Double",
            "ID": "lm_2_kellyswheeldouble"
        },...
    ],
    "currency": [
        "IDX",
        "USD",
        "JPY",
        "CNY",
        "RUB",...
    ],
    "limit_spin": 999
}
```