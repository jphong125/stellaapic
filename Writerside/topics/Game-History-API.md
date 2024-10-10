# Game History API

History API provides game rounds played by the player, with their details. Operator can get a list of games played, game rounds that the player has played during a particular day and hour, and the screen of the game at the end of the game round.

History HTTP service is a simple API for game Operator to get player’s game history. 
API is an HTTP listener, which listens POST requests coming to an URL with the request mappings below.

All responses should be in JSON format.

URL of the history HTTP service will be provided by Lucky Monaco for the production and test environments and looks like:


https://{API service domain}/IntegrationService/v4/http/HistoryAPI/
History HTTP service is securely protected, hence please be sure:

- player’s browser (end) must NOT be used as initiator of requests to the service;
- proper IPs are supplied to Lucky Monaco for whitelisting