# Incremental Load

Lyftrondata supports incremental data loading from NetSuite by leveraging the `last_modified_date` column. This approach ensures that only the records that have been changed or added since the last sync are retrieved, optimizing data transfer and reducing load times.



<table data-header-hidden><thead><tr><th width="305">Column</th><th>Description</th></tr></thead><tbody><tr><td>Last_Modified_Date</td><td>Date filtering is supported in fewer endpoints which have Last Date Modified.</td></tr></tbody></table>
