---
description: >-
  This section discusses the SQL syntax for the Lyftrondata driver. Our driver
  adheres to ANSI standards, and all of our Python drivers adhere to the Sql
  Alchemy framework.
---

# SQL Standard

### Select Statements

The [Lyftrondata](https://www.lyftrondata.com/) driver for [Smadex](https://www.lyftrondata.com/integration/smadex/) provides ANSI SQL standard support. A SELECT statement can consist of the following basic clauses.

* SELECT
* INTO
* FROM
* JOIN
* WHERE
* GROUP BY
* HAVING
* UNION
* ORDER BY
* LIMIT
* PAGESIZE LIMIT

### SELECT Syntax

The following syntax diagram outlines the syntax supported by the SQL engine of the provider:

{% code overflow="wrap" %}
```html
SELECT {  [ TOP <numeric_literal> | DISTINCT ]  {    *| {<expression> [ [ AS ] <column_reference> ]        | { <table_name> | <correlation_name> } .*      } [ , ... ]}  [ INTO csv:// [ filename= ] <file_path> [ ;delimiter=tab ] ]  {    FROM <table_reference> [[ AS ] <identifier> ]  } [ , ... ]  [ [       INNER | { { LEFT | RIGHT | FULL } [ OUTER ] }    ] JOIN <table_reference> [ ON <search_condition> ] [ [ AS ] <identifier> ]  ] [ ... ]  [ WHERE <search_condition> ]  [ GROUP BY <column_reference> [ , ... ]  [ HAVING <search_condition> ]  [ UNION [ ALL ] <select_statement> ]  [    ORDER BY    <column_reference> [ ASC | DESC ] [ NULLS FIRST | NULLS LAST ]  ]  [    LIMIT <expression>    [      { OFFSET | , }      <expression>    ]  ]} | SCOPE_IDENTITY() <expression> ::=  | <column_reference>  | @ <parameter>  | ?  | COUNT( * | { [ DISTINCT ] <expression> } )  | { AVG | MAX | MIN | SUM | COUNT } ( <expression> )  | NULLIF ( <expression> , <expression> )  | COALESCE ( <expression> , ... )  | CASE <expression>      WHEN { <expression> | <search_condition> } THEN { <expression> | NULL } [ ... ]    [ ELSE { <expression> | NULL } ]    END  | <literal>  | <sql_function> <search_condition> ::=  {<expression> {{= | > | < | >= | <= | <> | != | LIKE | NOT LIKE | IN | NOT IN | IS NULL | IS NOT NULL | AND | OR | CONTAINS | BETWEEN } [ <expression> ]  }} [ {{ AND | OR }} ... ]
```
{% endcode %}

### Examples

1.  Return all columns:

    | <mark style="color:blue;">`SELECT * FROM employee;`</mark> |
    | ---------------------------------------------------------- |
2.  Rename a column:

    | <mark style="color:blue;">`SELECT [age] AS MY_Age FROM address;`</mark> |
    | ----------------------------------------------------------------------- |
3.  Cast a column's data as a different data type:

    | <mark style="color:blue;">`SELECT CAST(mobile AS VARCHAR) AS Str_Mobile FROM customer;`</mark> |
    | ---------------------------------------------------------------------------------------------- |
4.  Search data:

    | <mark style="color:blue;">`SELECT * FROM customer WHERE company_name = 'lyftrondata';`</mark> |
    | --------------------------------------------------------------------------------------------- |
5.  Return the number of items matching the query criteria:

    | <mark style="color:blue;">`SELECT COUNT(*) AS TotolRows FROM customer;`</mark> |
    | ------------------------------------------------------------------------------ |
6.  Return the number of unique items matching the query criteria:

    | <mark style="color:blue;">`SELECT COUNT(DISTINCT name) FROM customer;`</mark> |
    | ----------------------------------------------------------------------------- |
7.  Return the unique items matching the query criteria:

    | <mark style="color:blue;">`SELECT DISTINCT name FROM customer;`</mark> |
    | ---------------------------------------------------------------------- |
8.  Summarize data:

    | <mark style="color:blue;">`SELECT priority, MAX(subscriptions) FROM customer GROUP BY subscriptions;`</mark> |
    | ------------------------------------------------------------------------------------------------------------ |
9.  Retrieve data from multiple tables.

    | <mark style="color:blue;">`SELECT c.name, a.street FROM customer c INNER JOIN address a ON c.customer_id = a.customer_id`</mark> |
    | -------------------------------------------------------------------------------------------------------------------------------- |
10. Sort a result set in ascending order:

    | <mark style="color:blue;">`SELECT customer_id, subscriptions FROM customer  ORDER BY subscriptions ASC`</mark> |
    | -------------------------------------------------------------------------------------------------------------- |
11. Restrict a result set to the specified number of rows:

    | <mark style="color:blue;">`SELECT customer_id, subscriptions FROM customer LIMIT 10`</mark> |
    | ------------------------------------------------------------------------------------------- |
12. Parameterize a query to pass in inputs at execution time. This enables you to create prepared statements and mitigate SQL injection attacks.

    | <mark style="color:blue;">`SELECT * FROM incident WHERE category = @param`</mark> |
    | --------------------------------------------------------------------------------- |

13\. Restrict a result set to the specified number of pages

&#x20;                <mark style="color:blue;">SELECT \* FROM sales\_invoice lyftstartpage 1 lyftendpage 10</mark>

### Quickstart Steps

Do you have questions about how to use the platform? Don't worry; we've got you covered. Simply follow the quickstart instructions [here](../../../../quickstart-steps.md).

### Questions? <a href="#questions" id="questions"></a>

We're always happy to answer any additional questions you may have! [Set up a meeting with our data experts.](https://www.lyftrondata.com/book-a-meeting/)


