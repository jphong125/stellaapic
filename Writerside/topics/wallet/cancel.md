# Cancel

Transaction will be cancelled when an error occurs during an API integration.

## Requested by LuckyMonaco

### Parameters

|Name|Data Type| Description                                                             |
|:---|:---:|:------------------------------------------------------------------------|
|sid|string| Player's session ID, specified by Partner when creating a game session. |
|userid|string| Player's ID, specified by Partner when creating a game session.         |
|transaction|object| Object containing transaction details.                                  |
|transaction.id|string| ID that was used in failed API<br/>ID that was in failed API            |
|uuid|string| A unique ID for each request                                            |

### Example of URL

``` http
https://<Partner website(Domain)/<Cancel, specified by partner>?authToken=<TOKEN>
```

### Example of HTTP BODY

``` json
{
    "sid": "<Sesseion ID>",
    "userid": "<User ID>",
    "transaction": {
        "id": "<Unique transaction ID>"
    },
    "uuid": "<Unique Request ID>"
}
```

## Response from partner(s)

### Parameters 2

|Name|Data Type| Description                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
|:---|:---:|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|status|string| * "OK" is a default value. The value is "OK" even if there is no Transaction.id.<br/>If the response status is a non-200 HTTP response or the arbitrary error codes are created, it will  be considered as an error.<br/>* A non-200 HTTP response is a TEMPORARY_ERROR.<br/>* If the format of HTTP response does not match, it will be considered as a TEMPORARY_ERROR.<br/>* Any values that are not included in the list will be cosidered as an UNKNOWN_ERROR.|
|uuid|string| A unique ID for each response                                                                                                                                                                                                                                                                                                                                                                                                                                     |
|retransmission|boolean| If response is for a retransmission of original request (I.E. same uuid) then the value should be "true".<br/>(e.g.: If the request is retried due to a network failure, then this response needs to be sent with "retransmission" = true.)<br/>For all other cases, "False" or "retransmission" shouldn't be included in response.                                                                                                                               |

### Example of HTTP BODY 2

``` json
{
    "status": "OK",
    "uuid": "<Unique response ID>"
}
```
