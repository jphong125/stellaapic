# About LuckyMonaco V4

Casino Game API supports different types of games : video slots, video poker, etc. <br/>
and API should not be changed if Casino Operator needs to add more games to their portfolio.

As soon as new game is available, it is added to Game Library with game symbols.

Casino Operator will use provided symbols for StartGame method during opening specific game and Bet requests will be also sent using this symbols.

Game Library will be provided to Casino Operator together with integration package or resent when new games are available.

## Seamless Wallet API
Operator should provide the Seamless Wallet Integration API on their side. <br/>Lucky Monaco will call the methods when **user make a bet or get a win and their balance should be updated**

| Name       | Description                                                                                                                                                                                                                                        |  Remark  |
|:-----------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:--------:|
| Check      | check whether player can bet or not.                                                                                                                                                                                                               | Required |
| Balance    | Returns the balance of a player.                                                                                                                                                                                                                   | Required | 
| Bet        | Checks if the player has enough funds and subtracts money from player’s balance. Returns the value of updated balance.                                                                                                                             | Required |
| Result     | Adds winning amount to player’s balance. Returns the value of updated balance.                                                                                                                                                                     | Required |
| BonusWin   | Notifies the Casino Operator that FREE ROUNDS are over and player’s balance should be increased with bonus amount. (Reserved for future development)                                                                                               | Required |
| JackpotWin | Using this method a Lucky Monaco system will notify Casino Operator about Jackpot winning. (Reserved for future development)                                                                                                                       | Required |
| PromoWin   | Notifies the Casino Operator that TOURNAMENT CAMPAIGN is over and player’s cash balance should be increased with amount in promoWin. (Reserved for future development)                                                                             | Required |
| Cancel     | Notifies the casino Operator that Canceled player’s bet. This method will be used for cancellation of a bet. (i.e. Players connection was lost in any cases so lucky monaco will do retransmission 3 times, then do not receive any bet response.) | Required |
| EndRound   | If the Casino Operator requires to finalize the round that is completed in their system with signal received from the Game Provider.                                                                                                               | Optional |
| Error code | Error codes used in seamless wallet.                                                                                                                                                                                                               | Required |
| SessionExpired | Notifies the Casino Operator that player’s game session has expired in Lucky Monaco system due to inactivity or game client closing.                                                                                                               | Optional |


## Transfer Wallet API

Operator can use this API for game opening and transferring funds to player’s balance in the Lucky Monaco system.

| Name              | Description                                                                                                                                      |  Remark  |
|:------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------|:--------:|
| CreateUser        | This method allows registering a new player on Lucky Monaco system.                                                                              | Required | 
| CreateWallet      | This method allows registering a new player Wallet on Lucky Monaco system.                                                                       | Required |
| DepositBalance    | This method transfers funds in to player’s balance (i.e. deposit) within Lucky Monaco system.                                                    | Required |
| WithdrawlBalance  | This method transfers funds out of the player’s balance (i.e. withdrawal) within Lucky Monaco system.                                            | Required |
| Userinfo   | This method retrieves information about a specific user on Lucky Monaco system.                                                                  | Optional |
| GetBalance        | this method Operator can get the current balance of the player in the Lucky Monaco system.                                                       | Optional |
| GetTransferstatus | This method returns the status of a particular transaction that transferred the money in or out the player’s balance in the Lucky Monaco system. | Optional |
| GetSlotLog        | Using this method Casino Operator can get the user's slot log.                                                                                   | Optional |
| TerminateSession  | Using this method Casino Operator can terminate the current player session and kick him out all games.                                           | Optional |
| Error code        | Error codes used in transfer wallet.                                                                                                             | Required |
| SessionExpired | Notifies the Casino Operator that player’s game session has expired in Lucky Monaco system due to inactivity or game client closing.             | Optional |

## Integration API

Integration API offers generic methods that allow Operators to create a game lobby, get statistics and close player sessions forcefully.

| Name              | Description                                                                                                                                                                                                                                      |  Remark  |
|:------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:--------:|
| Start Game        | Using this method Casino Operator can start game.                                                                                                                                                                                                | required |
| GetCasinoGames    | Using this method Casino Operator can retrieve the list of available games to utilize on their system. Once the new game is released it will be updated to this list. May be used for automatic building games lobby at casino website.          | Optional |
| GetCasinoIconInfo | Using this method Casino Operator can retrieve the icon info of games available for integration.May be used for automatic building games lobby at casino website.                                                                                | Optional |
| GetCasinoIconList | Using this method Casino Operator can retrieve the icon list of games available for integration.May be used for automatic building games lobby at casino website.                                                                                | Optional |
| GetCasinoLanguage | Using this method Casino Operator can retrieve the list of language of games available for integration.                                                                                                                                          | Optional |
| GetCasinoCurrency | Using this method Casino Operator can retrieve the list of about a specific currency of games available for integration.                                                                                                                         | Optional |
| CloseSession      | This method terminates active game sessions of the player.                                                                                                                                                                                       | Optional |
| HealthCheck       | Using this method Casino Operator can check if Lucky Monaco provider API service or Game server are live and ready.                                                                                                                              | Optional |
| Refund         | Refunds player’s balance. This method will be used for cancellation of a bet in the case the game unfinished round. (i.e. Players connection was lost in any cases so the round is remaining unfinished (bet is success, but result is pending)) | Required |

## Player ID
User ID (userId parameter) is unique identifier of the user within Casino Operator system. 


If User is new and its account does not exist in the Lucky Monaco system it will be created automatically on the base of the data sent by Casino Operator server.

If User account already exists in the Lucky Monaco database it will be updated with the response data if necessary.


## Play Session
Play session is a game round in which bet and wins are combined together.

Each round can contain several bets, win and refunds of the bets.

## Transaction Reference
Transaction Reference is unique transaction id within Lucky Monaco system.

Transaction Reference used for bets and wins has to be different.
