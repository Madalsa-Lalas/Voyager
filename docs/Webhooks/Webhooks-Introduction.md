---
stoplight-id: 7jezflxyrmyo9
---

# Webhooks-Introduction


## Webhooks

Receive status updates from Xplor Pay by setting up a webhook.

### What is a webhook?
Xplor Pay webhooks provide you with real-time information about the status of your requests. Setting up a webhook means you automatically receive updates when there is a status change with your request.

<!-- theme: info -->

> #### Note
>
> The webhook destination (URL) must use an encrypted connection (https) and must also have a certificate signed by a trusted certificate authority.


### Merchant Demographic Web Hooks



| **Code**  | **Message**  | **Event Type** | **Event** |
|  --- |  --- |  --- |  --- |
| 100 | Fix SSN | ContactFixes | Shown on C &amp; E |
| 101 | Fix Address | ContactFixes | Same as C |
| 102 | Fix DOB | ContactFixes | Same as C |
| 103 | Fix Name (Last) | ContactFixes | Same as C |
| 200 | Fix Secretary of State | BusinessFixes | Shown on B |
| 201 | Fix State of Registration | BusinessFixes | Same as B |
| 202 | Fix Tax ID | BusinessFixes | Same as B |
| 203 | Fix Legal Name | BusinessFixes | Same as B |
| 204 | Fix Physical Address | BusinessFixes | Same as B |
| 300 | Check Name on Account | BankFixes | Shown on A |
| 301 | Please provide a checking account | BankFixes | Same as A |
| 302 | Upload a voided check | BankFixes | Same as A |
| 303 | Please check your routing number | BankFixes | Same as A |
| 304 | Please provide an alternate account | BankFixes | Same as A |
| 305 | Check account number | BankFixes | Same as A |



### Manual Review, Pended, Approved, Declined

{
 
 &quot;Event&quot; : &quot;Pended&quot;,

 &quot;MerchantID&quot; : &quot;6588000000191919&quot;,
 
 &quot;Payload&quot;: null
 
 }

