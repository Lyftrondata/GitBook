---
description: >-
  This section explains how to connect Lyftrondata to Dynamics 365 Business
  Central.
---

# Connection Steps

### Establishing a connection

[Lyftrondata](https://www.lyftrondata.com) offers three methods connecting to [Dynamics 365 Business Central](https://www.lyftrondata.com/integration/dynamics-365-business-central/). To establish your connection, use the connection strings described below.

### Basic

This option has been deprecated by Microsoft.

<table><thead><tr><th width="204">Key</th><th width="342">Value</th><th>Field</th></tr></thead><tbody><tr><td>Username</td><td>Your Business Central Username</td><td>Required</td></tr><tr><td>Password</td><td>Your Business Central Access Key</td><td>Required</td></tr><tr><td>Tenant ID</td><td>Your Business Central Tenant ID</td><td>Required</td></tr><tr><td>OData</td><td>Your Business Central OData version. Such as ODataV4</td><td>Required</td></tr><tr><td>Version</td><td>Your Business Central API Version. Such as V1.0</td><td>Required</td></tr></tbody></table>

Follow the steps below to establish a basic connection

{% embed url="https://www.loom.com/share/886175cf879245d7b42412112a142949" %}
Dynamics 365 Business Central Basic
{% endembed %}

### OAuth

This option requires Azure app registration; refer to the [prerequisite](prerequisite.md) section.

| Key          | Value                                                | Field    |
| ------------ | ---------------------------------------------------- | -------- |
| Client ID    | Your Business Central Client ID.                     | Required |
| Secret       | Your Business Central Secret (PW)                    | Required |
| Tenant       | Your Business Central Tenant                         | Required |
| Redirect URL | Your re-directed URL                                 | Required |
| Subdomain    | Your Subdomain                                       | Required |
| OData        | Your Business Central OData version. Such as ODataV4 | Required |
| Version      | Your Business Central API Version. Such as V1.0      | Required |

Follow the steps below to establish an OAuth connection

{% embed url="https://www.loom.com/share/2588747f39504efd8128a26a6fb90736?sid=2f8d26ea-5572-40a1-bfa0-0b236678737d" %}
Dynamics 365 Business Central OAuth2
{% endembed %}

### OAuth2 Client Credentials

This option requires Azure app registration; refer to the [prerequisite](prerequisite.md) section.

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
Dynamics 365 Business Central OAuth2 Client Credentials
{% endembed %}

### Quickstart Steps

Do you have questions about how to use the platform? Don't worry; we've got you covered. Simply follow the quickstart instructions [here](../../quickstart-steps.md).

### Questions? <a href="#questions" id="questions"></a>

We're always happy to help with any other questions you might have! [Set up a meeting with our experts](https://www.lyftrondata.com/book-a-meeting/).
