# Getting a game session (ENTER)

## Overview

In order to connect to servers, creates a game session for users.

## Usage

After requesting a game session with individual notified API URL, API servers will respond accordingly.

Redirect a user to received game session URL for entering LuckyMonaco.

## API URL

Requested game session API URL will be notified individually, for security reasons.

## Request for a game session ( request )

Requesting a game session to LuckyMonaco API Servers.

### Request parameters

| Name                  |                   |     | Data Type | Description                                                                                                                           |
|:----------------------|:-----------------|:-----|:---------:|:--------------------------------------------------------------------------------------------------------------------------------------|
| uuid                  |                      |  |  string   | Unique request ID, each requested ID must be unique.<br/>(uuid4)                                                                      |
| [gametype](define.md) |                      |  |  string   | Choose to launch slot game or table game (table game are not available now)                                                           |
| [gameid](define.md)   |                      |  |  string   | "Gameid" is a unique ID for each games, you can find from separately provided "SLOT_SPEC" document.                                   |
| player                |                      |  |  object   | Contain player details.                                                                                                               |
|                       |           id          | |  string   | Player's ID.                                                                                                                          |
|                       |        nickname       | |  string   | Player's nickname.                                                                                                                    |
|                       | [language](define.md) | |  string   | In-game UI language determined by ISO 639-1 2-digit code<br/>Refer separately provided "SLOT_SPEC" document "Language support" sheet. |
|                       |        currency        | |  string   | Currency code (ISO 4217 3-digit code)<br/>Refer seperately provided SLOT_SPEC document "Currency support" sheet.                      |
|                       |        session         | |  object   | Contain player session details.                                                                                                       |
|    |                        |    id       |string| Player's session ID, assigned by Partner.                                                                                             |
|    |                        |  ip |  string   | Player's session IP address.                                                                                                          |

### Examples

METHOD

``` html
POST
```

URL

``` html
https://<API URL>/api/session?MEMB_ID=<Partner ID>&HASH=<TOKEN>
```

HEADER

``` html
Content-Type: application/json
```

## Successful response to the game session ( response )

Example of successful response from LuckyMonaco API servers. Use URL parameters.


|Name|Data Type|Description|
|:---|:---:|:---:|
|url|string|used for player redirection.|

### Example of response BODY

``` json
{
    "url": "https://example.com/index.html?token=f8hf^234&@!$22893fhsf..."
}
```

## Failure response for a game session ( response )

Example of failure response from LuckyMonaco API servers.

In case of failure, LuckyMonaco servers will return  'HTTP status 4XX' or 'HTTP status 5XX' and following response body.

### Example of BODY

``` json
{
    "errors": {
        "code": "G.0",
        "message": "Could not authenticate, please review sent data and try again. If problem persists, contact customer support "
    }
}
```

### Error Codes

Error codes are classified into following categories.

* G - generic failures
* V - validation of input parameters failed

|Code|Description (omitting error codes)|
|:---|:---:|
|G.01|System error, should be retried, in case of constant occurrences should be reported to LuckyMonaco.|

Error codes will be additionally updated
