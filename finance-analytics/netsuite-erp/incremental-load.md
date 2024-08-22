# Incremental Load

Lyftrondata supports incremental data loading from NetSuite by leveraging the `last_modifie_ddate` column. This approach ensures that only the records that have been changed or added since the last sync are retrieved, optimizing data transfer and reducing load times.

| Last\_Modified\_Date | Date filtering is supported in fewer endpoints which have Last Date Modified. |
| -------------------- | ----------------------------------------------------------------------------- |
