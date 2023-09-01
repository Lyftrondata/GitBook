---
description: >-
  This section provides information on how to connect the connector from the
  code.
---

# Connecting from Code

### Working with the connector

The [Lyftrondata](https://www.lyftrondata.com/) driver for [Adrecord ](../../adrecord-/driver-framework/None/)provides simple connectivity steps from code. The primary functionality of the Lyftrondata Python Connector lies in querying, which interacts directly with the available services for your connector. However, many of these stored procedures rely on information stored in the provider's tables. These tables must be populated by the user and will contain all of the information that a certain user has on their connector account. The tables will rely on user data provided by connector on their endpoints.

Once the needed input data is present, one can execute <mark style="color:blue;">SELECT</mark> queries by running the query maker function of Lyftrondata\_Connector.

### Connecting from code

See wheel \[installation]\(../../../Marketing Analytics/adrecord-/driver-framework/installation.md) for the prerequisite information you need to deploy the source connector.

```python
import Lyftrondata.MyConnector.lib.Lyftrondata_MyConnector_Connector as con
lyft = con.Connect("My Lyftrondata license key")
init = lyft.initialise(username="my username",password="my password")
```

### Quickstart Steps

Do you have questions about how to use the platform? Don't worry; we've got you covered. Simply follow the quickstart instructions [here](./).

### Questions? <a href="#questions" id="questions"></a>

We're always happy to answer any additional questions you may have! [Set up a meeting with our data experts.](https://www.lyftrondata.com/book-a-meeting/)
