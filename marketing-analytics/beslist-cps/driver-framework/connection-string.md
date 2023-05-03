---
description: >-
  This section provides information about the driver supported connection string
  to connect with the API
---

# Connection String

### Steps

The [Lyftrondata](https://www.lyftrondata.com/) driver for [Beslist Cps](https://www.lyftrondata.com/integration/beslist-cps/) provides the connection string steps documented below. For more detailed information about driver connectivity, visit the [Connection Steps](../../../erp/dynamics-365-business-central/connection-steps.md) section of this document.

```python
import Lyftrondata.MyConnector.lib.Lyftrondata_MyConnector_Connector as con
lyft = con.Connect("My Lyftrondata license key")
init = lyft.initialise(username="my username",password="my password")
df = lyft.execute_query("Select * from my sys.connectionstring")
print(df)  //my pandas dataframe
```

### Quickstart Steps

Do you have questions about how to use the platform? Don't worry; we've got you covered. Simply follow the quickstart instructions [here](../../../../quickstart-steps.md).

### Questions? <a href="#questions" id="questions"></a>

We're always happy to answer any additional questions you may have! [Set up a meeting with our data experts.](https://www.lyftrondata.com/book-a-meeting/)
