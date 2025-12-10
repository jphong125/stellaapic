# Seamless Wallet API

This is a simple API for Stella gaming platform to connect to player's wallet. API is an HTTP listener, which listens
application/json POST requests.

In POST requests can be sent HTTP Header:
- Content-Type: application/json

For application/json, the body of the HTTP message sent to the Seamless Wallet API is essentially one
giant query string where name/value pairs are separated by the ampersand (,), and names are separated from values by
the  equals symbol (:). An example of this would be (please see request examples for each call below):

"parameter1":"value1","parameter2":"value2"

All responses should be in JSON format (please see response examples for each call below).

URL of the Seamless Wallet API should be provided by Casino Operator for the production and Stage environments.