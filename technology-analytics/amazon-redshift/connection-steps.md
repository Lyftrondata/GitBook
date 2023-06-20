---
description: This section explains how to connect Lyftrondata to Amazon Redshift.
---

# Connection Steps

### Establishing a connection

[Lyftrondata](https://www.lyftrondata.com) offers three methods connecting to [Amazon Redshift](https://www.lyftrondata.com/integration/amazon-redshift/). To establish your connection, use the connection strings described below.

### Basic

| Key         | Value                   | Field    |
| ----------- | ----------------------- | -------- |
| hostname    | Redshift hostname       | Required |
| port        | Redshift port           | Required |
| database    | Redshift  database name | Required |
| username    | Redshift Username       | Required |
| password    | Redshift Password       | Required |
| Access Key  | Redshift Access Key     | Required |
| Secret Key  | Redshift Secret Key     | Required |
| Bucket Name | Redshift  Bucket Name   | Required |

### **Advanced Config:**

The JSON represents advanced configuration settings for a Spark application. It contains a list of key-value pairs with corresponding fields and values. The settings include packages needed for the application, file system details, and credentials for accessing resources.&#x20;

The table summarizes these settings with editable values for some fields.

<table><thead><tr><th>Key</th><th>Value</th><th>Field</th><th data-hidden>Description</th></tr></thead><tbody><tr><td>spark.jars.packages</td><td>com.amazon.redshift:redshift-jdbc42:2.1.0.12,com.google.guava:guava:31.1-jre,org.apache.hadoop:hadoop-aws:3.2.2</td><td>false</td><td>Spark packages</td></tr><tr><td>spark.hadoop.fs.s3a.impl</td><td>org.apache.hadoop.fs.s3a.S3AFileSystem</td><td>false</td><td>File System</td></tr><tr><td>spark.hadoop.fs.s3a.access.key</td><td></td><td>false</td><td>Access Key</td></tr><tr><td>spark.hadoop.fs.s3a.aws.credentials.provider</td><td>org.apache.hadoop.fs.s3a.SimpleAWSCredentialsProvider</td><td>false</td><td>Provider</td></tr><tr><td>spark.hadoop.fs.s3a.secret.key</td><td></td><td>false</td><td>Secret Key</td></tr></tbody></table>

### Policy:&#x20;

This JSON represents a single item in a list of policies, with a key "policy". It contains a text field for specifying a bucket policy.

| Key    | Text   | Type     |
| ------ | ------ | -------- |
| policy | Policy | Required |

### Quickstart Steps

Do you have questions about how to use the platform? Don't worry; we've got you covered. Simply follow the quickstart instructions [here](../../quickstart-steps.md).

### Questions? <a href="#questions" id="questions"></a>

We're always happy to help with any other questions you might have! [Set up a meeting with our experts](https://www.lyftrondata.com/book-a-meeting/).
