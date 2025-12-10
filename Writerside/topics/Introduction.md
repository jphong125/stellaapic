# Introduction

## Important

* Partner ID (used for secureLogin) and Token will be issued by Stella team member.
* When you need to add sub-brand, you will be needed an additional PartnerID to do so.
* Please refer to the provided CASINO_SPEC document for integration.

## Overview

Stella API provides interfaces that allow you to use information of operator's existing players in Stella system.

Game Opening with logged in player for inviting into Stella, and you can start an integration between Player's and Partner's Game Money.

## Defines

* Stella : Where the players are playing and progressing the game.
* Partner(s) : Business partners. (i.e. Platform providers, Aggregator or Operators)

## The Flow

Users will be redirected to corresponding game session after getting a game session from API servers when entering to the game. (i.e. Start game)

* IF you are a seamless system, please refer to Seamless Integration.
* If you are a transfer system, please refer to Transfer Integration.

## API call basic specifications

* HTTP methods : POST
* HTTP content format : JSON

## HTTP response code

Standard RFC 2616 HTTP response codes are used to indicate the success or failure of an API request.

* 2XX : Success
* 4XX : Problem with the HTTP request
* 5XX : Error with Stella's servers
