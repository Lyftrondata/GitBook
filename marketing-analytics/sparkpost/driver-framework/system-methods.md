---
description: >-
  This section describes the Lyftrondata driver framework methods used to
  establish API connectivity and data fetching.
---

# System Methods

### Methods Detail

The [Lyftrondata](https://www.lyftrondata.com/) driver for [Sparkpost](https://www.lyftrondata.com/integration/marketing-analytics/sparkpost//) provides information about the description and usage of the method in the code.

Methods Return Type: <mark style="color:blue;">**tuple(bool, token:str)**</mark>



| Method Name          | Return Type | Parameter                                                                                                                                                                                            | Description                                         |
| -------------------- | ----------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------- |
| initializeAPI        | tuple       | credentials                                                                                                                                                                                          | This method is use to initialize the API            |
| fetchDataFromAPI     | tuple       | <p>table(tablename) </p><p>parameter(schemaname) from_page(start page number) to_page (end page number)</p><p>columName(name of column)</p><p>columnValue(column value) </p><p>limit(rows limit)</p> | This method is use to fetch data from API           |
| execute\_query       | tuple       | string                                                                                                                                                                                               | This method is use to execute query                 |
| get\_schema\_list    | tuple       | ConnectorObj                                                                                                                                                                                         | This method is use to get the schema list           |
| get\_schema\_objects | tuple       | ConnectorObj schema                                                                                                                                                                                  | This method is use to get the schema object details |
| get\_object\_columns | tuple       | <p>ConnectorObj schema </p><p>list </p><p>number_of_page</p>                                                                                                                                         | This method is use to get the object columns detail |
|                      |             |                                                                                                                                                                                                      |                                                     |

### Quickstart Steps

Do you have questions about how to use the platform? Don't worry; we've got you covered. Simply follow the quickstart instructions [here](../driver-framework/README.md).

### Questions? <a href="#questions" id="questions"></a>

We're always happy to answer any additional questions you may have! [Set up a meeting with our data experts.](https://www.lyftrondata.com/book-a-meeting/)


