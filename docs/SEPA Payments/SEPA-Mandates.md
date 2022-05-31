---
stoplight-id: ucktmmw0snjc2
---

#SEPA Mandate

**Getting Started with Mandates service**

Mandate is a contract betwen a debtor and their bank that a reaccuring payment (i.e. a subscription) will be taken from their bank accout on your behalf for the service you will provide to them. The mandate contains a lot of sensitive info. This service does the following:

1. receives mandate info data, encrypt/tokenize it and return a Token to identify the data
2. retrieve previously encrypted/tokenized mandate data using the Token
3. delete the mandate data

We have two environments: **Sandbox (development/test)** and **Production (live)**. The host/domain of your requests and the secret api key you use _will be different _depending on which environment you are pointed to. The host/domain in sandbox will always contain &#39;-sb&#39; (ex- HTTPS://gateway-sb.clearent.net).

[Request a sandbox api key](https://developer.clearent.com/index.php/getting-an-api-key/)

When you have completed development and are ready to go live you need to do the following:

- Switch this endpoint from  **https://gateway-sb.clearent.net/rest/v2/direct-debit/mandates** to  **https://gateway.clearent.net/rest/v2/direct-debit/mandates**
- Switch your Sandbox secret api key to the Production secret api key.

**Using this endpoint**

Our Mandate service allows you to securely store Mandate information that is referenced by at token. This token can be used when performing SEPA transaction in place of the actual SEPA Transaction data (see Post Transaction under SEPA Transactions). The token replaces routing-number, account-number, account-type and individual name; making those fields unnecessary when paying with a token.

To use this API, send your request in this format:

- Method: GET | POST | DELETE

- Sandbox Host:  gateway-sb.clearent.net
- Production Host: gateway.clearent.net
- Endpoint: /rest/v2/direct-debit/mandates 

Headers:

- Content-Type: application/json
- Accept: application/json
- api-key: PRODUCTION or SANDBOX SECRET APIKEY
