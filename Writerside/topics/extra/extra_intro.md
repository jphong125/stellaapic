# Extra Integration

## Overview

LuckyMonaco advises the use of Round API integration.

Possible we might need both API calls (bet and win), depending on the circumstances of the company.

Hence the need for an additional API integration.

## Integration

Round API calls are replaced with the Bet API & Win API calls.

Prev) spin -> round -> spin result
Change) spin -> bet -> win -> spin result


Handling a timeout and cancel a retry are equivalent to the Round API.

### Important
1. Bet API and win API use the same Transaction.id.
2. Bet API and win API calls are made in sequential order.

### Flow for an API Call, Canellation
1. Bet -> Error -> Cancel (Win API is not getting called, Bet API request must  be cancelled.)
2. Bet -> Win -> Error -> Cancel (Bet and Win API requests must be cancelled.)
