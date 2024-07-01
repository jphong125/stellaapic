# Check ( Checking Player Status)

A request to check whether player can bet or not.

## Requested by LuckyMonaco

### Parameters

|Name|Data Type|Description|
|:---|:---:|:---:|
|sid|string|Player's session ID, specified by Partner when creating a game session.|
|userid|string|Player's ID, specified by Partner when creating a game session.|
|uuid|string|A unique ID for each request|

### Example of URL

``` http
https://<Partner website(Domain)>/<Check, specified by Partner>?authToken=<TOKEN>
```

### Example of HTTP BODY

``` json
{
    "sid": "<Session ID>",
    "userid": "<User ID>",
    "uuid": "<Unique request ID>"
}
```

## Response from partner(s)

### Parameters 2

|Name|Data Type|Description|
|:---|:---:|:---|
|status|string|* "OK" is a default value. If the response status is a non-200 HTTP response or the arbitrary error codes are created, it will  be considered as an error. <br/>* A non-200 HTTP response is a TEMPORARY_ERROR.<br/>* If the format of HTTP response does not match, it will be considered as a TEMPORARY_ERROR.<br/>* Any values that are not included in the list will be cosidered as an UNKNOWN_ERROR.|
|sid|string|Player's session ID, specified by Partner.|
|uuid|string|Unique response ID|

### Example of HTTP BODY 2

``` json
{
    "status": "OK",
    "sid": "<Request Session ID>",
    "uuid": "<Unique response ID>"
}
```
