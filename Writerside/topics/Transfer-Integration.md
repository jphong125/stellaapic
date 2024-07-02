# Transfer Integration

## Overview

Define a method for integration transfers

## Usage

You can create a user, create a wallet, and adjust the amount by calling the API provided by Lucky Monaco. 
!! It can only be used if an agreement has been reached with Lucky Monaco to use the structure.

## APIs

* /user/create - Create a user.
* /user/create_wallet - Create a wallet for a specific good.
* /user/info - Search user information. (All wallet information is also searched.)
* /user/balance - Check the user's holdings of a specific good.
* /user/charge - Provides specific goods to users.
* /user/refund - Receive specific goods back from the user.
* /log/get - Get the game log.