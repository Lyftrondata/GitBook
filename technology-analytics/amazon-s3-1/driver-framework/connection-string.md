---
description: >-
  This section provides information about the driver supported connection string
  to connect with the API
---

# Connection String

### Steps

The [Lyftrondata](https://www.lyftrondata.com/) driver for [S3Excel](https://lyftron.com/source/data-migration-from-amazon-s3-to-snowflake-google-bigquery-amazon-redshift-and-azure-sql-database/) provides the connection string steps documented below. For more detailed information about driver connectivity, visit the [Connection Steps](../../../erp/dynamics-365-business-central/connection-steps.md) section of this document.

```python
import Lyftrondata.MyConnector.lib.Lyftrondata_MyConnector_Connector as con
lyft = con.Connect("My Lyftrondata license key")
init = lyft.initialise(username="my username",password="my password")
df = lyft.execute_query("Select * from my sys.connectionstring")
print(df)  //my pandas dataframe
```

### Quickstart Steps

Do you have questions about how to use the platform? Don't worry; we've got you covered. Simply follow the quickstart instructions [here](https://app.gitbook.com/o/wtkDnJM7XX3whUqN09p1/s/lTEE4RQvO3RwZSpc3Y6M/\~/changes/14/technology-analytics/amazon-s3-1).

### Questions? <a href="#questions" id="questions"></a>

We're always happy to answer any additional questions you may have! [Set up a meeting with our data experts.](https://www.lyftrondata.com/book-a-meeting/)