---
stoplight-id: w3pfzhclj6954
---

# SEPA Payments API

**SEPA Transaction**



**Getting Started with Direct Debit service or Credit Transfer service**

Direct Debit transaction collects money of your customers into your bank account. This service does the following:

1. receive Direct Debit payment instruction, validates the data and the mandate referenced with a Token received
2. publishes a message with the payment info on a queue for further processing
3. store the payment info in a database

Credit Transfer transaction moves the money previously collected into your bank account to the bank accounts of your merchants. This service does similar to Direct Debit but now for Credit Transfer payment instructions. :

1. receive Credit Transfer payment instruction, validates the data and the mandate referenced with a Token received
2. publishes a message with the payment info on a queue for further processing
3. store the payment info in a database

We have two environments: **Sandbox (development/test)** and **Production (live)**. The host/domain of your requests and the secret api key you use _will be different _depending on which environment you are pointed to. The host/domain in sandbox will always contain &#39;-sb&#39; (ex- HTTPS://gateway-sb.clearent.net).


[Request a sandbox api key](https://developer.clearent.com/index.php/getting-an-api-key/)

When you have completed development and are ready to go live you need to do the following:


- Switch this endpoint from  **https://gateway-sb.clearent.net/rest/v2/direct-debit/transactions** to  **https://gateway.clearent.net/rest/v2/direct-debit/transactions**
- Switch your Sandbox secret api key to the Production secret api key.


**Using this endpoint**

Endpoints:

- POST /rest/v2/direct-debit/transactions/credit
- POST /rest/v2/direct-debit/transactions/debit
- GET /rest/v2/direct-debit/transactions
- GET /rest/v2/direct-debit/transactions/{transactionKey}

Method GET retrieves transactions by various criteria:

- By type
- By status
- By merchant
- By date range
- By its ID
- By multiple fields


To use this API, send your request in this format:

- Method:          GET | POST |
- Sandbox Host:    gateway-sb.clearent.net 
- Production Host: gateway.clearent.net 
- Endpoint:        /rest/v2/direct-debit/transactions |

Headers:

- Content-Type: application/json
- Accept: application/json
- api-key: PRODUCTION or SANDBOX SECRET APIKEY
