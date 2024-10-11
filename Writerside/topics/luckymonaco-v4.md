# About LuckyMonaco V4

Casino Game API supports different types of games: video slots, video poker, keno, etc. 
and API should not be changed if Casino Operator needs to add more games to their portfolio.

As soon as new game is available, it is added to Game Library with game symbols.

Casino Operator will use provided symbol for StartGame method during opening specific game and Bet requests will be also sent using this symbol.

Game Library will be provided to Casino Operator together with integration package or resent when new games are available.

## Seamless Wallet API
Operator should provide the Seamless Wallet Integration API on their side. Lucky Monaco will call the methods when players make a bet or get a win and their balance should be updated

| Name                  | Description                                                                                                                          |  Remark  |
|:----------------------|:-------------------------------------------------------------------------------------------------------------------------------------|:--------:|
| Balance               | Returns the balance of a player                                                                                                      | Required | 
| Bet                   | Checks if the player has enough funds and subtracts money from player’s balance. Returns the value of updated balance.               | Required |
| Result                | Adds winning amount to player’s balance. Returns the value of updated balance                                                        | Required |
| BonusWin              | Notifies the Casino Operator that free rounds are over and player’s balance should be increased with bonus amount.                   | Required |
| JackpotWin            | Using this method a Lucky Monaco system will notify Casino Operator about Jackpot winning.                                           | Required |
| PromoWin              | Notifies the Casino Operator that tournament campaign is over and player’s cash balance should be increased with amount in promoWin. | Required |
| Refund                | Refunds player’s balance. This method will be used for cancellation of a bet in the case the game cannot be finished.                | Required |
| EndRound              | Notifies the Casino Operator that the game round is over, for transactions finalization purpose.                                     | Optional |
| SessionExpired        | Notifies the Casino Operator that player’s game session has expired in Lucky Monaco system due to inactivity or game client closing. | Optional |
| GetBalancePerGame     | Returns the balance of a player per game.                                                                                            | Optional |
| GetBalancePerCurrency | Returns the balance of a player per Currency.                                                                                        | Optional |


## Transfer Wallet API

Operator can use this API for game opening and transferring funds to player’s balance in the Lucky Monaco system.

| Name                  | Description                                                                                                                                    |  Remark  |
|:----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------|:--------:|
| CreateUser            | This method allows registering a new player on Lucky Monaco side.                                                                              | Required | 
| CreateWallet          | This method allows registering a new player Wallet on Lucky Monaco side.                                                                       | Required |
| DepositBalance        | This method transfers funds in to player’s balance (i.e. deposit) within Lucky Monaco system                                                   | Required |
| WithdrawlBalance      | This method transfers funds out of the player’s balance (i.e. withdrawal) within Lucky Monaco system                                           | Required |
| Userinformation       | This method get information about a specific user on Lucky Monaco side.                                                                        | Required |
| GetBalance            | this method Operator can get the current balance of the player in the Lucky Monaco                                                             | Required |
| GetTransferstatus     | This method returns the status of a particular transaction that transferred the money in or out the player’s balance on the Lucky Monaco side. | Required |

## Integration API

Integration API offers generic methods that allow Operators to create a game lobby, get statistics and close player sessions forcefully.

| Name               | Description                                                                                                                                                      |  Remark  |
|:-------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------|:--------:|
| Start Game         | Using this method Casino Operator can start game                                                                                                                 | required |
| GetCasinoGames     | Using this method Casino Operator can retrieve the list of games available for integration.May be used for automatic building games lobby at casino website      | Optional |
| Getalistofgameicon | Using this method Casino Operator can retrieve the icon of games available for integration.May be used for automatic building games lobby at casino website      | Optional |
| GetCasinoLanguage  | Using this method Casino Operator can retrieve the list of language of games available for integration.                                                          | Optional |
| GetCasinoCurrency  | Using this method Casino Operator can retrieve the list of about a specific currency of games available for integration.                                         | Optional |
| GetBettingTable    | Using this method Casino Operator can retrieve the list of betting table of games available for integration.                                                     | Optional |
| CloseSession       | This method terminates active game sessions of the player.                                                                                                       | Optional |
| TerminateSession   | Using this method Casino Operator can terminate the current player session and kick him out all games                                                            | Optional |
| CancelRound        | Using this method Casino Operator can use any time they want to close player’s round forcefully.                                                                 | Optional |
| HealthCheck        | Using this method Casino Operator can check if Lucky Monaco provider API service or Game server are live and ready.                                              | Optional |
| SessionExpired     | Using this method Casino Operator can get information, that player’s game session has expired in PragmaticPlay system due to inactivity or game client closing. | Optional |

## External Player ID
External Player ID (external userId parameter) is unique identifier of the user within Casino Operator system. 

Before sending to Lucky Monaco any gaming related request Casino Operator should authenticate a player using Authenticate method.

If player is new and its account does not exist in the Lucky Monaco system it will be created automatically on the base of the data sent by Casino Operator server in the Authenticate response.

If player account already exists in the Lucky Monaco database it will be updated with the response data if necessary.

External Player id received in the Authenticate response will be sent with all subsequent requests to Casino Operator.

## Play Session
Play session is a game round in which bet and wins are combined together.

Each round can contain several bets, win and refunds of the bets.

## Transaction Reference
Transaction reference is unique transaction id within Lucky Monaco system.

Transaction reference used for bets and wins has to be different.
