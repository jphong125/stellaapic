# Error code for Transfer Wallet

Below table contains the error codes that the Lucky Monaco system will return in the response to Balance Transfer API calls.

Only responses with HTTP Status: 200 should be accepted by operator as valid response Responses with HTTP Status other than 200 should not be accepted as valid (recommended actions are the same  as for error: 1, description “Internal error. Try later please.”)

For each API account, retry frequency for failed "Transfer" or “GetTransferStatus” method requests, should be not more than one call per minute and not longer than 1 hour. (after 1 hour Error reason should be checked in relevant support channel)


| Name |Data Type| Description                                                   | Remark   |
|:-----|:---:|:--------------------------------------------------------------|----------|
| 1    |string| Internal error. Try later please.                             | Required |
| 2    |string| Incorrect secure LOGIN and secure password combination.       | Required |
| 6    |string| Game is not found or is not allowed for your system.          | Required |
| 7    |string| One or several input parameters is not set or set incorrectly | Required |
| 8    |string| Transaction already exists No action required.                | Required |
| 17   |string| Player not found Verify request values Verify request values. | Required |
| 21   |string| Currency code is incorrect or unsupported                     | Required |
