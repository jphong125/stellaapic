# Get a list of game icon

## Overview
Using this method Casino Operator will get to use URLs below in order to get icons for the games :

## API URL
Requested get a list of game URL will be notified individually, for security reasons.

###  Request parameters

| Name          |Data Type| Description                                                                                                                                                        | Remark |
|:--------------|:---:|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------|:---------:|
| gameid        |string| Symbolic unique identifier of the game within the Lucky Monaco system.                                                                                                       | Required | 
| gameIdnumeric |string| Numeric value of gameId | Required |


size 150x150 
``` http
https://<server domain>/icons/<gameid>/<gameIdNumeric>_150x150.png
```
size 170x170
``` http
https://<server domain>/icons/<gameid>/<gameIdNumeric>_170x170.png
```

size 170x170_ZH
``` http
https://<server domain>/icons/<gameid>/<gameIdNumeric>_170x170_CN.png
```

size 200x270
``` http  
https://<server domain>/icons/<gameid>/<gameIdNumeric>_200x270.png
```

size 200x270_ZH
``` http 
https://<server domain>/icons/<gameid>/<gameIdNumeric>_200x270_CN.png
```

size 300x300_ZH-TW 
``` http 
https://<server domain>/icons/<gameid>/<gameIdNumeric>_300x300_CN2.png
```

size 340x340
``` http 
https://<server domain>/icons/<gameid>/<gameIdNumeric>_340x340.png
```

size 340x340_ZH
``` http 
https://<server domain>/icons/<gameid>/<gameIdNumeric>_340x3400_CN.png
```

size 400x540
``` http 
https://<server domain>/icons/<gameid>/<gameIdNumeric>_400x540.png
```

size 400x540_ZH
``` http 
https://<server domain>/icons/<gameid>/<gameIdNumeric>_400x540_CN.png
```

size 700x840
``` http 
https://<server domain>/icons/<gameid>/<gameIdNumeric>_700x840.png
```

size 760x539
``` http 
https://<server domain>/icons/<gameid>/<gameIdNumeric>_760x539.png
```


