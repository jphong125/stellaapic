# Integration API

This is a simple API for Casino Operator to retrieve some data from Lucky Monaco system and send some events to
Lucky Monaco.

API is an HTTP listener, which listens POST requests coming to an URL with the request mappings below.

All responses are in JSON format.

URL of the HTTP service will be provided by Lucky Monaco team member for the Stage and production environments and looks
like: 

``` http
https://<API URL>/v4/<object>
```

Integration simple HTTP Service is securely protected, hence please be sure:
- player’s browser (end) must NOT be used as initiator of requests to the service
- proper IPs are supplied to Lucky Monaco for whitelisting