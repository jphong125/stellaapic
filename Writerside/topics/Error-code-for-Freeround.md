# Error code for Freeround

The table below contains the error codes that the Lucky Monaco system will return in the response to Variable Free Rounds API calls.


| Name |Data Type| Description                                                                                                                          | Remark   |
|:-----|:---:|:-------------------------------------------------------------------------------------------------------------------------------------|----------|
| 0    |string| Request was successfully processed.                                                                                                  | Required |
| 1    |string| Authentication failed. Incorrect secure login and secure password combination.                                                       | Required |
| 2    |string| Validation failed. Empty mandatory field '{field name}'.                                                                             | Required |
| 3    |string| Game(s) are not supported: {list of the game id}.                                                                                    | Required |
| 4    |string| Game(s) do not support Free round bonus: {list of the game id}                                                                       | Required |
| 5    |string| Bonus code already exists.                                                                                                           | Required |
| 6    |string| The requested Free Round bonus is not found in the system.                                                                           | Required |
| 7    |string| Free round bonus is canceled.                                                                                                        | Required |
| 8    |string| Free round bonus is closed or started to play.                                                                                       | Required |
| 9    |string| Currency code '{ISO code}' is incorrect or unsupported.                                                                              | Required |
| 10   |string| Player does not have active Free round bonuses.                                                                                      | Required |
| 11   |string| Free round bonus cannot be created. Expiration date limit (30 days) has been exceeded                                                | Required |
| 12   |string| Free round bonus cannot be created. Expiration date is in the past.                                                                  | Required |
| 14   |string| Bonus code already exists with another parameters.                                                                                   | Required |
| 1000 |string| Internal server error. Lucky Monaco will return this error code if their system has internal problem and cannot process the request. | Required |
