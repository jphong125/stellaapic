# Seamless integration (For game money)

NOTE: We will send you the endpoints for the integration, once you receive them, please send us back your developed API in below format.
* Make sure to use your appropriate URLs instead of "localhost" written below!

EXAMPLE<br/>
{<br/>
    "check" : "http://localhost/check?authToken=xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",<br/>
    "balance" : "http://localhost/balance?authToken= xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx ",<br/>
"win" : "http://localhost/balance?authToken= xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx ",<br/>
"bet" : "http://localhost/balance?authToken= xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx ",<br/>
    "cancel" : "http://localhost/cancel?authToken= xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx ",<br/>
}

## Overview

Should be used for integration of user's Game money with partner's Game money while placing bets and winning in LuckyMonaco.

LuckyMonaco servers will respond to 5 requests related to the user's Game Money.

## Usage

Any changes regarding Game Money in LuckyMonaco will be reported to Partner's servers.

The web server must respond to the following standards, so that any changes to Game Money can be reported.

## API url appointed by Partner

LuckyMonaco will request API call to this designated url, and Partner will response in Json.

## Integration

bet api -> win api

Integration of bet and win methods is By placing a bet (-) with the bet API and processing a win (+) with the win API.

When running Round of spin, at least two API calls are required in the debit -> win order.

## You must connect using one of two methods

You must inform LuckyMonaco of the selected method
so that we can call the API using that method.

## Exception handling flow (Time out, retry, cancel)

It will be considered as exception after total of 30 seconds passed since the initial spin request.

* Each API (debit, credit, round, cancel) has a timeout of 10 seconds.
* If an error or timeout occurs, it will be retried up to 3 times.
* If 3 retries fail, the spin fails and cancel API is called.
* If the cancellation API fails three times, a log is left on the LuckyMonaco server and the request is stopped.
