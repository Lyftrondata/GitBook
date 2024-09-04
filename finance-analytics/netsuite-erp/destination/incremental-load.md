# Incremental Load

Lyftrondata supports incremental data loading for NetSuite and NetSuite2 data sources. To enable incremental loading, the target table must meet specific criteria:

#### NetSuite2.com & NetSuite.com Data Source

A table from the NetSuite data source will be updated incrementally if it contains:

* A numeric primary key.
* One of the following columns:
  * `lastmodified`
  * `lastmodifieddate`
  * `linelastmodifieddate`

This ensures that only records changed or added since the last sync are retrieved, optimizing data transfer and reducing load times.
