---
description: >-
  This section describes the prerequisites for connecting Netsuite Erp to
  Lyftrondata. To complete the prerequisites, the user must have admin access to
  Netsuite Erp.
---

# Prerequisite

Setup Instructions

Follow the steps below to create an API Credentials for the [Netsuite Erp](https://www.lyftrondata.com/integration/finance-analytics/netsuite-erp/) driver setup with [Lyftrondata](https://www.lyftrondata.com)

## Suite Talk Vs SuiteQL:

\
**SuiteTalk** is the older SOAP-based API for communication with NetSuite, supporting various entities and full data manipulation capabilities. However, its data retrieval tools are limited, resulting in poor SELECT performance, and it lacks advanced features like joins and aggregations.

**SuiteQL** is the newer API offering SQL-like queries for NetSuite. It excels in join support, group by, and aggregations, providing efficient data selection. It's ideal for data retrieval. Use SuiteTalk for both retrieval and modification. Select the appropriate API through the Schema setting, considering their distinct connection options.

## **NetSuite Web Services Permissions:**

The provider communicates with NetSuite through the NetSuite Web services. This means that any connecting user must have permissions on the specified **AccountId** to connect through NetSuite Web services. Please see the Permission Configurations for greater details on required and optional permissions.

**Create or edit a role for Web services permissions**

<table data-header-hidden><thead><tr><th width="90"></th><th></th></tr></thead><tbody><tr><td><strong>Step</strong></td><td><strong>Action</strong></td></tr><tr><td>1</td><td>Log into NetSuite, navigate to Setup, and access User/Roles -> Manage Roles -> New or edit an existing role</td></tr><tr><td>2</td><td>Click Permissions, choose Setup, and add "SOAP Web Services" and "REST Web Services" permissions, along with other required permissions</td></tr><tr><td>3</td><td>Within Setup, go to User/Roles -> Manage Users, select the user</td></tr><tr><td>4</td><td>On the Access tab, add the new role and save the user</td></tr></tbody></table>

## Authenticating to NetSuite:

NetSuite provides the following methods for connecting to its API:

1. #### Basic (Deprecated) <a href="#token-based-authentication" id="token-based-authentication"></a>
2. #### Token Based Authentication <a href="#token-based-authentication" id="token-based-authentication"></a>
3. #### OAuth <a href="#token-based-authentication" id="token-based-authentication"></a>

#### Token Based Authentication: <a href="#token-based-authentication" id="token-based-authentication"></a>

Enable token-based authentication in NetSuite

* Select Setup > Company > Enable Features.

![](https://docs.devart.com/odbc/netsuite/netsuite\_enable\_features.png)

* On the Enable Features screen, select Suite Cloud.

<figure><img src="../../../.gitbook/assets/image (2).png" alt=""><figcaption><p>Enable Feature</p></figcaption></figure>

1. In the Manage Authentication section, enable the Token-Based Authentication and OAUTH 2.0 checkboxes.

![Setup Authentication](https://docs.devart.com/odbc/netsuite/netsuite\_enable\_tba.png)

2. Create a role with the necessary privileges for token-based authentication and access to the necessary objects, and assign it to the user that will be used for authentication.

<table data-header-hidden><thead><tr><th width="107"></th><th></th></tr></thead><tbody><tr><td><strong>Step</strong></td><td><strong>Action</strong></td></tr><tr><td>1</td><td>Navigate to Setup > User/Roles > Manage Roles > New.</td></tr><tr><td>2</td><td>Create a role and assign necessary permissions for the integration with the Provider. At least the Web Services and User Access Tokens privileges are required.</td></tr><tr><td>3</td><td>Select Lists > Employees > Edit User > Access Roles > Roles, and assign the role to the necessary user.</td></tr></tbody></table>

An administrator can assign users to the modified token-based authentication roles. TBA is available for many types of NetSuite users, including customers, employees, partners, and vendors.





3. Create an integration record with token-based authentication enabled.

<table data-header-hidden><thead><tr><th width="96"></th><th></th></tr></thead><tbody><tr><td><strong>Step</strong></td><td><strong>Action</strong></td></tr><tr><td>1</td><td>Navigate to Setup > Integrations > Manage Integrations > New.</td></tr><tr><td>2</td><td>Open the Integration window, Enter a Name for the application, Select Token-Based Authentication checkbox, Ensure TBA: Authorization Flow is not selected, Click Save</td></tr></tbody></table>

<div align="center" data-full-width="true">

<figure><img src="../../../.gitbook/assets/image (3).png" alt="" width="160"><figcaption><p>Integration Screen</p></figcaption></figure>

</div>

On the confirmation screen, copy the generated Consumer Key and Consumer Secret. Save these values somewhere because you will not be able to retrieve them once you leave this screen; otherwise, you will have to re-generate them, which makes the old ones to stop working.

<figure><img src="../../../.gitbook/assets/image (4).png" alt=""><figcaption><p>Token Based Authentication</p></figcaption></figure>

**Create an access token.**

<table data-header-hidden><thead><tr><th width="99"></th><th></th></tr></thead><tbody><tr><td><strong>Step</strong></td><td><strong>Action</strong></td></tr><tr><td>1</td><td>Select Setup > Users/Roles > Access Tokens > New.</td></tr></tbody></table>

\


<figure><img src="../../../.gitbook/assets/image (5).png" alt=""><figcaption><p>Access Token</p></figcaption></figure>

On the confirmation screen, copy the generated Token ID and Token Secret. Save these values somewhere because you will not be able to retrieve them once you leave this screen; otherwise, you will have to re-generate them, which makes the old ones to stop working.

<figure><img src="../../../.gitbook/assets/image (6).png" alt=""><figcaption><p>Confirmation Access Token</p></figcaption></figure>

\
After completing the above steps, insert the obtained Consumer Key, Consumer Secret, Token ID, and Token into the appropriate fields. Please check our [Connection Steps Guide](../connection-steps.md).\


### Quickstart Steps

Do you have questions about how to use the platform? Don't worry; we've got you covered. Simply follow the quickstart instructions [here](../).

### Questions? <a href="#questions" id="questions"></a>

We're always happy to help with any other questions you might have! [Set up a meeting with our experts](https://www.lyftrondata.com/book-a-meeting/).
