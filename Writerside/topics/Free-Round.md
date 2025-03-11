# Free Round 

Free Rounds Bonus (FRB) allows the player to play a specified number of free rounds in a game. Free rounds created Free Rounds API may be configured to be played with a certain bet value specified for each game and currency. During Free rounds game play, bets are not deducted from the player's balance, but all wins are collected for the Free Round Bonus in the Lucky Monaco’s system.

**After all free rounds are played the Lucky Monaco system sends a bonusWin API call to Operator server to add money to the  player's balance.** 
Please note that not all games support FRB.
Free rounds can be awarded to players registered within the Lucky Monaco system using API. If a player is not registered in the Lucky Monaco system yet a new player account will be created automatically.
Free Rounds Bonus HTTP service is a simple API for game Operator to manage Free Rounds. API is an HTTP listener, which listens POST requests coming to an URL with the request mappings below.
All responses should be in JSON format.
URL of the FRB HTTP service will be provided by Lucky Monaco for the production and test environments and 
looks  like: https://{API service domain}/IntegrationService/v4/http/FreeRoundsBonusAPI/

Free Rounds HTTP service is securely protected, hence please be sure:
- player’s browser (end) must NOT be used as initiator of requests to the service;
- proper IPs are supplied to Lucky Monaco for whitelisting

## Overview

Free rounds is a promotional tool to grant spinning to player for "free of charge".
Usage and policy for the Free Round must be consulted with Lucky Monaco team.

IMPORTANT : PLEASE NOTE THAT, FREE ROUND IS CURRENTLY NOT SUPPORTED IN TRANSFER WALLET TYPE.


## APIs

1. get_info - Get freeround information.
2. bet_info - Obtain a list of betting amounts for specific slots and currencies.
3. create - Create a freeround.
4. delete - Remove freeround.
