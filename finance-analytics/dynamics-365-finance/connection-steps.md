---
description: This section explains how to connect Lyftrondata to Dynamics 365 Finance.
---

# Connection Steps

### Establishing a connection

[Lyftrondata](https://www.lyftrondata.com) offers the following methods connecting to [Dynamics 365 Finance](https://www.lyftrondata.com/integration/finance-analytics/dynamics-365-finance). To establish your connection, use the connection strings described below.

### OAuth

This option requires Azure app registration; refer to the prerequisite section.

| Key       | Value                                                | Field    |
| --------- | ---------------------------------------------------- | -------- |
| Client ID | Your Business Central Client ID.                     | Required |
| Secret    | Your Business Central Secret (PW)                    | Required |
| Tenant    | Your Business Central Tenant                         | Required |
| Subdomain | Your Subdomain                                       | Required |
| OData     | Your Business Central OData version. Such as ODataV4 | Required |
| Version   | Your Business Central API Version. Such as V1.0      | Required |

Follow the steps below to establish an OAuth connection

{% embed url="https://www.loom.com/share/2588747f39504efd8128a26a6fb90736?sid=2f8d26ea-5572-40a1-bfa0-0b236678737d" %}
Dynamics 365 Nav OAuth2
{% endembed %}

### OAuth2 Client Credentials

This option requires Azure app registration; refer to the prerequisite section.

| Key       | Value                                                | Field    |
| --------- | ---------------------------------------------------- | -------- |
| Client ID | Your Business Central Client ID.                     | Required |
| Secret    | Your Business Central Secret (PW)                    | Required |
| Tenant    | Your Business Central Tenant                         | Required |
| Subdomain | Your Subdomain                                       | Required |
| Odata     | Your Business Central OData version. Such as ODataV4 | Required |
| Version   | Your Business Central API Version. Such as V1.0      | Required |

Follow the steps below to establish an Oauth2 client credential connection. These steps are similar to those in the OAuth video above. Simply choose the OAuth2 client credentials from the OAuth Type drop-down.

{% embed url="https://www.loom.com/share/2588747f39504efd8128a26a6fb90736?sid=0c12e2d0-c0a1-4c22-94ff-66d96638c85f" %}
Dynamics 365 Nav Client Credentials
{% endembed %}

### Quickstart Steps

Do you have questions about how to use the platform? Don't worry; we've got you covered. Simply follow the quickstart instructions [here](./).

### Questions? <a href="#questions" id="questions"></a>

We're always happy to help with any other questions you might have! [Set up a meeting with our experts](https://www.lyftrondata.com/book-a-meeting/).
