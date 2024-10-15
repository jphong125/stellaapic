# User Info

## Overview
You can obtain information about a specific user by calling the URL provided by Lucky Monaco.
By calling the API, you can get the amount held by each wallet.

## API URL
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
    "userId": "tester",
}
```

## Response Example

### Response Parameters

| Name        | Data Type  | Description                                                 | Ramark                          |
|:------------|:----------:|:------------------------------------------------------------|---------------------------------|
| secureLogin |   string   | User name for authentication in the Casino Game API service | Required                        |
| playerId    |   string   | Id of the player within the Operator system.                | Required                        |
| at_create   |   string   | at create (yyyy-MM-dd HH:mm:ss)                             |  Required |
| at_login    |   string   | at login (yyyy-MM-dd HH:mm:ss)                              |     Required |
| wallet      | dictionary | wallets                                                     |      Required |
| currency    |    string  | each balance of currency                                    |      Required |
| error       |   number   | error code                                                  |     Required |
| descrition  |   string   | Description of the error for troubleshooting.               |     Required |

### Success Example

``` json
{
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

