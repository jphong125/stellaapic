# Game Money Integration

## Overview

Should be used for integration of user's Game Money with Partner's Game Money while placing bets and winning in LuckyMonaco.

LuckyMonaco servers will respond to 6 requests related to the user's Game Money.

## Usage

Any changes regarding Game Money in LuckyMonaco will be reported to Partner's servers.

The web server must respond to the following standards, so that any changes to Game Money can be reported.

## API url appointed by Partner

LuckyMonaco will request API call to this designated url, and Partner will response in Json.

## Integration

API integration is possible in two ways.

Type 1 (debit api -> credit api)

Integration of debit and credit methods is By placing a bet (-) with the debit API and processing a win (+) with the credit API.

When running one spin, two API calls are required in the debit -> win order.

Type 2 (round api)

The round method of linking is round is possible with one API call, and both bets (-) and wins (+) are sent to the call.

## You must connect using one of two methods

You must inform LuckyMonaco of the selected method
so that we can call the API using that method.

## Exception handling flow (Time out, retry, cancel)

A total of 80 seconds have passed since the spin request began, before the spin request fails.

* Each API (debit, credit, round, cancel) has a timeout of 10 seconds.
* If an error or timeout occurs, it will be retried up to 3 times.
* If 3 retries fail, the spin fails and cancel API is called.
* If the cancellation API fails three times, a log is left on the LuckyMonaco server and the request is stopped.
