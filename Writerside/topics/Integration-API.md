# Integration API

This is a simple API for Casino Operator to retrieve some data from Stella system and send some events to
Stella.

API is an HTTP listener, which listens POST requests coming to an URL with the request mappings below.

All responses are in JSON format.

URL of the HTTP service will be provided by Stella team member for the Stage and production environments and looks
like : 

``` http
https://<API URL>/v1/<object>
```

Integration simple HTTP Service is securely protected, hence please be sure :
- player’s browser (end) must NOT be used as initiator of requests to the service.
- proper IPs are supplied to Stella for whitelisting.

## Follow these steps
1. Run "Get Casino Game" to get the list of games
2. Run "Get Casino Icon Info" to get the information about the icon size and language provided. (If you need icons in other sizes, please contact the Stella team.)
3. Run "Get Casino Icon List" to get links to the corresponding game icons in the size and language you want.
4. Run "Get Casino Language" to see which languages are supported.
5. Run "Get Casino Currency" to see which currencies are supported.
6. Run "Health Check" to check if the API server is ready.
7. After completing the above steps, please enter the supported language and currency in "Start Game".