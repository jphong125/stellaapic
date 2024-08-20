# Win

Reporting Win results of Spin/Free Spins.

In general, one round (Transaction ID) has one win value.
However, if there is an additional win during a round of play, such as a regular spin win or a bonus game, multiple win values are sent under the same round (Transaction ID).

If a free spin is entered during a regular spin, the free spin will have a separate TransactionID in addition to the existing regular spin.

**Important**
1. Multiple Win values (win) within the round (Transaction ID) are all referred as Win, each of them are not referred with exclusive names.

2. Each win value is distinguished by uuid.
3. When sending the final win, send "is_end_round": "ok" at the bottom of the message to indicate that this round is over.
    - "is_end_round" is not sent for other wins.

4. If a free spin is entered after a regular spin, an additional TransactionID is received for the free spin.
    - In this case, when the free spin ends, the "is_end_round": "ok" message for the previous regular spin win is sent first, and then a separate message of "is_end_round": "ok" for the free spin is sent.

**Summary**
1. One Transaction ID may have multiple Wins and receive Win message multiple times with the different uuid.
2. If "is_end_round": "ok" is not included in the Win message, an additional Win message is sent.
3. The end of the round can be processed after receiving "is_end_round": "ok".
4. Free spins are managed through a separate TransactionID and "is_end_round": "ok" from the regular spins.


**Note**

1. amount : Sum of Spin Win + Jackpot Win in this Win message

2. jackpot :  Jackpot win

3. win : Win amount of either Spin win or Bonus win

4. is_end_round : If this line is present, this is the final win message.
If this line is absent, additional win messages will be received
after this win message.
 
``` json
"transaction": {
    "id": "<Unique transaction ID>",
    "amount": "<Win amount>", 
    "jackpot": "<Win amount>",
    "win": "<Win amount>", 
    "is_end_round" : "ok" 
}
```

## Requested by LuckyMonaco

### Parameters

| Name                  |Data Type| Description                                                                                                                                                                                                                                                                                                 |
|:----------------------|:---:|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| sid                   |string| Player's session ID, specified by Partner when creating a game session.                                                                                                                                                                                                                                     |
| userid                |string| Player's ID, specified by Partner when creating a game session.                                                                                                                                                                                                                                             |
| currency              |string| Currency code (ISO 4217 3-digit code)<br/>Please check SLOT_SPEC document                                                                                                                                                                                                                                   |
| [gametype](define.md) |string| Types of game (e.g. slot,table game)                                                                                                                                                                                                                                                                        |
| [gameid](define.md)   |string| "gameid" is a unique ID for each games, please check SLOT_SPEC document                                                                                                                                                                                                                                     |
| gamename              |string| Game Title(English)                                                                                                                                                                                                                                                                                         |
| bonus                 |string| Freeround Code(optional feature) <br/> Free Round is a promotional tool to grant spinning to player for "free of charge".<br/>Usage and policy for the Free Round must be consulted with Lucky Monaco team. <br/>IMPORTANT : PLEASE NOT THAT, FREE ROUND IS CURRENTLY NOT SUPPORED IN TRANSFER WALLET TYPE. |
| transaction           |object| Object containing transaction details.                                                                                                                                                                                                                                                                      |
| transaction.id        |string| Unique transaction ID (use to prevent duplicates)                                                                                                                                                                                                                                                           |
| transaction.amount    |string| Total Win(spin+jackpot) (decimal string)                                                                                                                                                                                                                                                                    |
| transaction.jackpot   |string| Jackpot Win (decimal string)                                                                                                                                                                                                                                                                                |
| transaction.win       |string| Spin Win (decimal string)                                                                                                                                                                                                                                                                                   |
| transaction.is_end_round   |  string   | Always "ok" , End Of Round (conditional)                                                                                                                                                                                                                                                                    |
| uuid                  |string| A unique ID for each request                                                                                                                                                                                                                                                                                |

### Example of URL

``` http
https://<Partner website(Domain)/<Win, specified by partner>?authToken=<TOKEN>
```

### Example of HTTP BODY

``` json
{
    "sid": "<Sesseion ID>",
    "userid": "<User ID>",
    "currency": "USD",
    "gametype": "<Game Type>",
    "gameid": "<Game ID>",
    "gamename": "<Game Title>",
    "transaction": {
        "id": "<Unique transaction ID>",
        "amount": "<Win amount>",
        "jackpot": "<Win amount>",
        "win": "<Win amount>"
    },
    "uuid": "<Unique Request ID>"
}
```

``` json
{
    "sid": "<Sesseion ID>",
    "userid": "<User ID>",
    "currency": "USD",
    "gametype": "<Game Type>",
    "gameid": "<Game ID>",
    "gamename": "<Game Title>",
    "transaction": {
        "id": "<Unique transaction ID>",
        "amount": "<Win amount>",
        "jackpot": "<Win amount>",
        "win": "<Win amount>",
        "is_end_round" : "ok"
    },
    "uuid": "<Unique Request ID>"
}
```

## Response from partner(s)

### Parameters 2

|Name|Data Type|Description|
|:---|:---:|:---|
|status|string|* "OK" is a default value. If the response status is a non-200 HTTP response or the arbitrary error codes are created, it will  be considered as an error. <br/>* A non-200 HTTP response is a TEMPORARY_ERROR.<br/>* If the format of HTTP response does not match, it will be considered as a TEMPORARY_ERROR.<br/>* Any values that are not included in the list will be cosidered as an UNKNOWN_ERROR.|
|balance|decimal|Balance (decimal string)|
|uuid|string|A unique ID for each response|
|retransmission|boolean|If response is for a retransmission of original request (I.E. same uuid) then the value should be "true".<br/>(e.g.: If the request is retried due to a network failure, an original response needs to be received with "retransmission" = true.).<br/>'False' for all other cases or 'retransmission' should not be included in response.<br/>For all other cases, "False" or "retransmission" shouldn't be included in response.|

### Example of HTTP BODY 2

``` json
{
    "status": "OK",
    "balance": "<User's balance>",
    "uuid": "<Unique response ID>"
}
```
