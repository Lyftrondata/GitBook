---
description: >-
  This section provides information about the Lyftrondata connector query maker
  method and how to execute ANSI Sql queries
---

# Querying Data

### Executing Query

The [Lyftrondata](https://www.lyftrondata.com/) driver for [Googleadsence](None) provides query maker functionality for querying data. To execute SQL statements that return data, use the cursor object's execute method. Once a query is executed, the result set is fetched from the API. This result set is converted into the relational format and returned which can then be printed out.&#x20;

```shell
import Lyftrondata.MyConnector.lib.Lyftrondata_MyConnector_Connector as con
lyft = con.Connect("My Lyftrondata license key")
init = lyft.initialise(username="my username",password="my password")
df = lyft.execute_query("Select * from my table")
print(df)  //my pandas dataframe
```

### Querying with where clause

We can filter our data directly from the API by providing a where clause for the table.&#x20;

```shell
import Lyftrondata.MyConnector.lib.Lyftrondata_MyConnector_Connector as con
lyft = con.Connect("My Lyftrondata license key")
init = lyft.initialise(username="my username",password="my password")
df = lyft.execute_query("Select * from my table where id=3")
print(df)  //my pandas dataframe
```

### Querying Sys & Data Tables&#x20;

The connector possesses system table definition that provides information about the connector framework metadata, and data tables that are used to discover the connector business information in the [ERD Data Model](../../../Marketing Analytics/googleadsence/data-model/erd.md).&#x20;

```shell
import Lyftrondata.MyConnector.lib.Lyftrondata_MyConnector_Connector as con
lyft = con.Connect("My Lyftrondata license key")
init = lyft.initialise(username="my username",password="my password")
df = lyft.execute_query("Select * from my sys.tables")
print(df)  //my pandas dataframe
```

### Querying Sys Views&#x20;

The connector possesses views definition that provides information about how these views are used to discover the connector business information in the [ERD Data Model](../../../Marketing Analytics/googleadsence/data-model/erd.md).&#x20;

```shell
import Lyftrondata.MyConnector.lib.Lyftrondata_MyConnector_Connector as con
lyft = con.Connect("My Lyftrondata license key")
init = lyft.initialise(username="my username",password="my password")
df = lyft.execute_query("Select * from my sys.views")
print(df)  //my pandas dataframe
```

### Usage Logging&#x20;

You will simply need to set two connection properties to begin capturing provider logging.

* For the usage logging you have to execute a query "select \* from sys.usage", which will return all the usage of the connector from the beginning.
* It shows how much time left, time spent and total allotted time of the connector.&#x20;

You can also access the timestamp.txt from the current driver directory which contains information, such as when authentication is performed or queries are executed. The specified file will be created by the driver in your working directory.&#x20;

```shell
import Lyftrondata.MyConnector.lib.Lyftrondata_MyConnector_Connector as con
lyft = con.Connect("My Lyftrondata license key")
init = lyft.initialise(username="my username",password="my password")
df = lyft.execute_query("Select * from my sys.usage")
print(df)  //my pandas dataframe
```

### Quickstart Steps

Do you have questions about how to use the platform? Don't worry; we've got you covered. Simply follow the quickstart instructions [here](../driver-framework/README.md).


### Questions? <a href="#questions" id="questions"></a>

We're always happy to answer any additional questions you may have! [Set up a meeting with our data experts.](https://www.lyftrondata.com/book-a-meeting/)

