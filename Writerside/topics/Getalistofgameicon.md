# Get Casino Icon Info

## Overview
Using this method Casino Operator will get icon info for the games.

## API URL
Requested get a list of game URL will be notified individually, for security reasons.

###  Request parameters

| Name          |Data Type| Description                                                                                                                                                        | Remark |
|:--------------|:---:|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------|:---------:|
| secureLogin |string| User name for authentacation in the Casino Game API service                                                                                                        | Required |
| token      |string| Token of the player from Authenticate response                                                                                                                                            | Required |

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
    "token" : "<token>"
}
```
## Response

###  Response parameters

|   Name   |                   | Data Type | Description                              |
|:--------:|:-----------------:|:---------:|:-----------------------------------------|
| IconList |                   |   array   | List of game icon info                   |
|          |        id         |  string   | Icon size consisting of width and height |
|          |       width       |  string   | width of icon                            |
|          |      height       |  string   | height of icon                           |
|          |     language      |  string   | language of icon                         |


### Example of body

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
    },
```
