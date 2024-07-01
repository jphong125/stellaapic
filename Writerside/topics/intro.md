# Introduction

## IMPORTANT

* Partner ID and Token will be issued by LuckyMonaco.
* Please refer to the provided SLOT_SPEC document for integration.

## Overview

LuckyMonaco API provides interfaces that allow you to use information from existing players in LuckyMonaco.
Creates a game session with logged in player for inviting into LuckyMonaco, and you can start an integration between Player's and Partner's Game Money.

## Defines

* LuckyMonaco : where the players are playing and progressing the game
* Partner(s) : Business partners (i.e. Platform providers or Operators)

## The Flow

Users get redirected to corresponding game session after getting a game session from API servers when entering game. (Create a Game session)
After entering LuckyMonaco, the user can receive the bet amount and the game results, specified by Partner.  ( Game Money Integration )

## API call basic specifications

* HTTP methods : POST
* HTTP Content format : JSON

## HTTP Response Code

Standard RFC 2616 HTTP response codes are used to indicate the success or failure of an API request.

* 2XX : Success
* 4XX : Problem with the HTTP request
* 5XX : Error with LuckyMonaco's servers
