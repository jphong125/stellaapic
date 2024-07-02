# Balance

A request to check wallet balance

## Requested by LuckyMonaco

### Parameters

| Name                  |Data Type|Description|
|:----------------------|:---:|:---|
| sid                   |string|Player's session ID, specified by Partner when creating a game session.|
| userid                |string|Player's ID, specified by Partner when creating a game session.|
| currency              |string|Currency code (ISO 4217 3-digit code)<br/>Please check SLOT_SPEC document |
| [gametype](define.md) |string|Types of game (I.e. slot,table game)|
| [gameid](define.md)   |string|"gameid" is a unique ID for each games, please check SLOT_SPEC document|
| uuid                  |string|A unique ID for each request|

### Example of URL

``` http
https://<Partner website(Domain)>/<Balance specified by partner>?authToken=<TOKEN>
```

### Example of HTTP BODY

``` json
{
    "sid": "<Session ID>",
    "userid": "<User ID>",
    "currency": "USD",
    "gametype": "slot",
    "gameid": "<Game ID>",
    "uuid": "<Unique request ID>"
}
```

## Response from partner(s)

### Parameters 2

|Name|Data Type|Description|
|:---|:---:|:---|
|status|string|* "OK" is a default value. If the response status is a non-200 HTTP response or the arbitrary error codes are created, it will  be considered as an error. <br/>* A non-200 HTTP response is a TEMPORARY_ERROR.<br/>* If the format of HTTP response does not match, it will be considered as a TEMPORARY_ERROR.<br/>* Any values that are not included in the list will be cosidered as an UNKNOWN_ERROR.|
|balance|decimal|Balance (decimal string)<br/> This value must always be quoted.<br/>except in the following cases:<br/><br/>*If user's balance is unable to view upon request,<br/> *Securing balance is not possible due to an error/failure|
|uuid|string|A unique ID for each response|
|retransmission|boolean|If response is for a retransmission of original request (I.E. same uuid) then the value should be "true".<br/>(e.g.: If the request is retried due to a network failure, an original response needs to be received with "retransmission" = true.).<br/>'False' for all other cases or 'retransmission' should not be included in response.|

### Example of HTTP BODY 2

``` json
{
    "status": "OK",
    "balance": "<user's balance>",
    "uuid": "<Unique response ID>"
}
