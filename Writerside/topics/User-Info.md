# User Info

## Overview
You can obtain information about a specific user by calling the URL provided by Lucky Monaco.
By calling the API, you can get the amount held by each wallet.

## Request
Requested user info API URL will be notified individually, for security reasons.

## Request Example

METHOD

``` http
 POST
```

URL

``` http
https://<API URL>/userInfo
```

HEADER

``` http
Content-Type: application/json
```

### Request Parameters

| Name        | Data Type  | Description                         |Ramark|
|:------------|:----------:|:------------------------------------|---|
| secureLogin |string| User name for authentication in the Casino Game API service | Required |
| userId     |string| Id of the player within the Operator system.                | Required |
| uuid        |  string   | A unique ID for each request                                             | Required |
| token       |string| Token of the player from Authenticate response              | Required |

### Example of Request Body

``` json
{
    "secureLogin" : "<partnerId>",
    "token" : "<token>"
    "userId": "tester",
}
```

## Response

Example of successful response from LuckyMonaco API servers.

### Response Parameters

| Name        | Data Type  | Description                                                 | Remark                          |
|:------------|:----------:|:------------------------------------------------------------|---------------------------------|
| secureLogin |   string   | User name for authentication in the Casino Game API service | Required                        |
| userId     |   string   | Id of the player within the Operator system.                | Required                        |
| at_create   |   string   | at create (i.e. 2024-10-15 14:30:00)                        |  Required |
| at_login    |   string   | at login (i.e. 2024-10-16 10:01:32)                         |     Required |
| wallet      | dictionary | wallets                                                     |      Required |
| currency    |    string  | each balance of currency                                    |      Required |
| error       |   number   | error code                                                  |     Required |
| descrition  |   string   | Description of the error for troubleshooting.               |     Required |

### Example of response BODY

``` json
{
    "secureLogin" : "<partnerId>",
    "token" : "<token>"
    "error": "0",
    "description" : "success",
    "userId" : "test",
    "at_create" : "2024-07-02 11:50:12"
    "at_login" : "2024-07-02 12:10:32"
    "wallet" : {
        "USD" : "100.0",
        "CNY" : "1023"
    }
}
```

