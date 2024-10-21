# Get Casino Icon Info

## Overview
Using this method Casino Operator will get casino icon (i.e. thumbnail) info for the games.

## Request
Requested get casino icon info URL will be notified individually, for security reasons.

###  Request Parameters

| Name          |Data Type| Description                                                                                                                                                        | Remark |
|:--------------|:---:|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------|:---------:|
| secureLogin |string| Partner name for authentacation in the Casino Game API service                                                                                                        | Required |
| token      |string| Token of the Partner from Authenticate response                                                                                                                                            | Required |
| uuid                |  string   | A unique ID for each request                                             | Required |

### Example of URL
METHOD

``` http
POST
```

URL

``` http
https://<API URL>/V4/GetCasinoIconInfo
```

HEADER

``` http
Content-Type: application/json
```

### Example of HTTP BODY

``` json
{
    "secureLogin" : "<partnerId>",
    "token" : "<token>",
    "uuid": "<uuid>"
}
```
## Response

Example of successful response from LuckyMonaco API servers.

###  Response parameters

|    Name     |                   | Data Type | Remark                                    |
|:-----------:|:-----------------:|:---------:|:------------------------------------------|
|    eroor    |                   |        string             | code of error.                            |
| description |                   | string| Response status short description.        |
|  iconList   |                   |   array   | List of game icon info.                   |
|             |        id         |  string   | Icon size consisting of width and height. |
|             |       width       |  string   | width of icon.                            |
|             |      height       |  string   | height of icon.                           |
|             |     language      |  string   | language of icon.                         |


### Example of Json BODY

``` json
{

  "error": 0,
  "description": "Success",
  "IconList": [
    {

      "id": "150x150",
      "width": 150,
      "height": 150,
      "language": "[\"EN\"]"
    },
    {

      "id": "170x170",
      "width": 170,
      "height": 170,
      "language": "[\"EN\",\"ZH\"]"
    },,,,
```
