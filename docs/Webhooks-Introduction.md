---
stoplight-id: 7jezflxyrmyo9
---

# Webhooks-Introduction


Debitsuccess uses webhooks to notify your application when an event occurs in your account. Notifications are the only way you&#39;ll receive automatic updates about events that are not triggered by a request from your side, for example when the account suspension schedules are changed.

Currently, we support limited events but may include additional events in the future. You can create webhooks for:

- [Account Suspension Notifications](https://debitsuccess.atlassian.net/wiki/spaces/DDE/pages/1257473235/Webhooks#Account-Suspension-Notifications)
- [Payment Status Notifications](https://debitsuccess.atlassian.net/wiki/spaces/DDE/pages/1257473235/Webhooks#Payment-Status-Notifications)

To receive notifications, you would need to:

1. Subscribe to Debitsuccess notifications
2. Create an endpoint on your server
3. Accept notifications
4. Test and go live

## Securing Webhooks

Once your server is configured to receive payloads, it&#39;ll listen for any payload sent to the endpoint you configured. For security reasons, you probably want to consider whitelisting our IP(can be provided during subscription) and/or limit requests to those coming from Debitsuccess.

You could also opt to receive a token to authenticate the messages. The token will be a static text - 256 chars max length.

This will be passed in the request header - X-Token

## Delivery attempts and retries

Successful delivery expects a http status code 200 response

Whenever any webhook fails to send data to the desired notification URL Debitsuccess retries three times every 180 seconds. If a message fails to deliver after 3 retries an email would be triggered to the email address nominated during the subscription and the webhook would be disabled.

Incase you would want any specific messages delivered please contact Debitsuccess.

---

## Subscribe to Debitsuccess Notifications

To subscribe to Debitsuccess webhook notifications, send an email to either [testapi.support@debitsuccess.com](mailto:testapi.support@debitsuccess.com) or [liveapi.support@debitsuccess.com](mailto:testapi.support@debitsuccess.com) with the following information:

- URL - The webhook notification endpoint.
- Token - A unique static text of 256 characters max, that is returned in the notification header (see [Securing webhooks](https://debitsuccess.atlassian.net/wiki/spaces/DDE/pages/1257473235/Webhooks#Securing-Webhooks) section). If not provided, Debitsuccess generates and assigns one for you.
- Facility - The facility/facilities information for notification subscription.
- Events - Events which you wish to receive notifications for.
- Email Address - A nominated email address to receive update in case of notification failure.

![Shape2](RackMultipart20220524-1-otweac_html_237499165a11f2b9.gif)

## Testing

Test webhooks notification in integrations test environment. Separate registration from prod environment

![Shape3](RackMultipart20220524-1-otweac_html_237499165a11f2b9.gif)

## Account Suspension Notifications

| **Notification Type** | **Description** |
| --- | --- |
| [customer.Schedule.Suspension.Added](/C:/wiki/spaces/DDE/pages/2610561048/customer.Schedule.Suspension.Added) | Suspension Schedule Added |
| [customer.Schedule.Suspension.Deleted](/C:/wiki/spaces/DDE/pages/2610724871/customer.Schedule.Suspension.Deleted) | Suspension Schedule Deleted |
| [customer.Schedule.Suspension.Updated](/C:/wiki/spaces/DDE/pages/2610462754/customer.Schedule.Suspension.Updated) | Suspension Schedule Updated |

## Payment Status Notifications

| **Notification Type** | **Description** |
| --- | --- |
| [Realtime.Account.Payment.Authorized](/C:/wiki/spaces/DDE/pages/2610626598/Realtime.Account.Payment.Authorized) | Realtime Payment Authorized |
| [Realtime.Account.Payment.Declined](/C:/wiki/spaces/DDE/pages/2610135089/Realtime.Account.Payment.Declined) | Realtime Payment Declined |

