# Transfer Integration

## Overview

Define a method for integration transfers

## Usage

You can create a user, create a wallet, and adjust the amount by calling the API provided by Lucky Monaco. 
!! AS the Seamless is the default type for Lucky Monaco, Please consult with Lucky Monaco team first if you wish to integrating the Transfer Wallet type.

## APIs

* /user/create - Create a user.
* /user/create_wallet - Create a wallet for a specific currency (include both fiat or crypto).
* /user/info - Search user information. (All wallet information is also searched.)
* /user/balance - Check the user's holdings of a specific currency (include both fiat or crypto).
* /user/charge - Provides specific currency (include both fiat or crypto) to users.
* /user/refund - Receive specific currency (include both fiat or crypto) back from the user.
* /log/get - Get the game log.