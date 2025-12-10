# Transfer Wallet API 

This is a simple API for game Operator to connect to the Stella game system. API is an HTTP listener, which listens
POST requests coming to an URL with the request mappings below.

All responses should be in JSON format and should contain error code and error description, which is empty in the case if
no error occurs.

URL of the HTTP service will be provided by Stella for the production and test environments and looks
like: https://{API service domain}/IntegrationService/v1/http/CasinoGameAPI

Transfer HTTP service is securely protected, hence please be sure:

- player’s browser (end) must NOT be used as initiator of requests to the service;

- proper IPs are supplied to Stella for whitelisting