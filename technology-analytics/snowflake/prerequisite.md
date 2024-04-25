---
description: >-
  This section describes the prerequisites for connecting Snowflake to
  Lyftrondata. To complete the prerequisites, the user must have admin access to
  Snowflake.
---

# Prerequisite

### Setup Instructions

Setting up the Snowflake connector involves configuring Snowflake entities (warehouse, database, schema, user, and role) in the Snowflake console and setting up the Snowflake destination connector using the [Lyftrondata](https://www.lyftrondata.com/).

* A Snowflake account with the [ACCOUNTADMIN](https://docs.snowflake.com/en/user-guide/security-access-control-considerations.html) role. If you don’t have an account with the `ACCOUNTADMIN` role, contact your Snowflake administrator to set one up for you.

#### Network policies[​](https://docs.airbyte.com/integrations/destinations/snowflake#network-policies) <a href="#network-policies" id="network-policies"></a>

By default, Snowflake allows users to connect to the service from any computer or device IP address. A security administrator (i.e. users with the SECURITYADMIN role) or higher can create a network policy to allow or deny access to a single IP address or a list of addresses.

If you have any issues connecting with Lyftrondata please make sure that the list of IP addresses is on the allowed list

To determine whether a network policy is set on your account or for a specific user, execute the _SHOW PARAMETERS_ command.

**Account**

```sql
SHOW PARAMETERS LIKE 'network_policy' IN ACCOUNT;
```

**User**

```sql
SHOW PARAMETERS LIKE 'network_policy' IN USER <username>;
```

\
**Setup guide**

#### Step 1: Set up Lyftrondata-specific entities in Snowflake <a href="#step-1-set-up-airbyte-specific-entities-in-snowflake" id="step-1-set-up-airbyte-specific-entities-in-snowflake"></a>

To set up the Snowflake connector, you first need to create Lyftrondata-specific Snowflake entities (a warehouse, database, schema, user, and role) with the OWNERSHIP permission to write data into Snowflake, track costs pertaining to Lyftrondata, and control permissions at a granular level.

1. Log into your Snowflake account.
2. Edit the following script to change the password to a more secure password and to change the names of other resources if you desire.

You can use the following script in a new Snowflake worksheet to create the entities:

\


### Video Instruction

{% embed url="https://www.loom.com/share/3e750239532e4f60a20d8ba928cfe7a9?sid=eec63825-d24e-4b92-97e2-2c62008a12de" %}

### Quickstart Steps

Do you have questions about how to use the platform? Don't worry; we've got you covered. Simply follow the quickstart instructions [here](./).

### Questions? <a href="#questions" id="questions"></a>

We're always happy to help with any other questions you might have! [Set up a meeting with our experts](https://www.lyftrondata.com/book-a-meeting/).
