# Role Limitations

When integrating NetSuite2.com with external systems, such as a data warehouse, it's crucial to carefully manage roles and permissions for users accessing data through the Connect Service. Below are key considerations:

#### 1. **Role-Based Access:**

* **Connect Service Access**: Users must be assigned roles that allow access to the `NetSuite2.com` data source. Access to data is role-based, meaning users can only retrieve data for records they have permission to access. Users with access to the **Static Data Model** can view the structure and names of record types and fields, but not necessarily the data itself.

#### 2. **Data Warehouse Integrator (DWI) Role:**

* **Full Data Access**: The **Data Warehouse Integrator (DWI)** role provides access to all NetSuite data through `NetSuite2.com`, excluding sensitive information like credit card data.
* **Global Permissions**: Global permissions take precedence over the DWI role. For example, if certain permissions are set to “None,” even users with the DWI role won't be able to access that data.
* **Token-Based Authentication (TBA)**: This role requires the use of **token-based authentication** for access.

#### 3. **Global Permissions and Restrictions:**

* **Global Permissions**: These can override the DWI role and limit access to certain data.
* **Administrator Role**: Typically, the Administrator role does not have access to `NetSuite2.com` unless using **OAuth 2.0** for SuiteAnalytics Connect. However, the **DWI** and **custom roles** are preferred when transferring data to a warehouse.
* **Deprecated or Restricted Roles**: The following roles are restricted from using `NetSuite2.com`:
  * Full Access (Deprecated)
  * Roles that require **two-factor authentication (2FA)**
  * Roles that use **IP restrictions** to access the Connect Service

**Note**: if you want to learn more, Please check this official [documentation](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/section\_3998867068.html#Related-Topics) of NetSuite.&#x20;
