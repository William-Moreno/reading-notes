# SQL
---
## Structured Query Language

SQL is Structured Query Language which was designed to allow users to run querieson or manipulate and transform the data from relational databases. Relational databases represent a collection of related tables, that are similar to a spreadsheet. Columns are like properties and rows are like instances. A *schema* dictates the structure of each tables and the datatypes that their columns can contain. This structuring can allow databases to be more efficient.

SELECT qureies are used to retrieve data from SQL databases. They declare what data we are looking for, where to find it in the database, and, sometimes, how to transform it. A basic SELECT command looks like this:

```SQL
SELECT column, another_column, ...
FROM sometable;
```
 To filter or constrain results, we use a WHERE clause in our query *(the * indicates all columns)*:

 ```SQL
 SELECT *
 FROM sometable
 WHERE condition;
 ```
More complex clauses can be constructed by using logical operators, numerical/evaluation operators and/or string operators.

### Logical Operators

These include the operators `AND` and `OR`.

### Numerical Operators

| **Operator** | **Description** |
| --- | --- |
| `=` , `!=` , `<` , `<=` , `>` , `>=` | Evaluation operators |
| `BETWEEN... AND...` | Number is within the range *(inclusive)* |
| `NOT BETWEEN... AND...` | Number is not within range *(inclusive)* |
| `IN(...)` | Number exists in list |
| `NOT IN(...)` | Number does not exist in list |

### String/Text Operators

| **Operator** | **Description** |
| --- | --- |
| `=` | Case sensitive exact equality |
| `!=` *or* `<>` | Case sensitive exact inequality |
| `LIKE` | Case **in**sensitive exact equality |
| `NOT LIKE` | Case **in**sensitive exact inequality |
| `%` | Used to match a sequence od 0 or more characters (only used in ***LIKE*** or ***NOT LIKE*** operations) |
| `-` | Used in a string to match a single character (only used in ***LIKE*** or ***NOT LIKE*** operations) |
| `IN(...)` | String exists in list (only used in ***LIKE*** or ***NOT LIKE*** operations) |
| `NOT IN(...)` | String does not exist in list (only used in ***LIKE*** or ***NOT LIKE*** operations) |


* *Strings must always be in quotes*

## More Commands 

### Filtering and Sorting Queries

- `DISTINCT` allows us to blindly discard rows that have duplicate column values. *(There are ways to do this more specifically)*
- `ORDER BY` sorts results in either ascending (ASC) or descending (DESC) order.
- `LIMIT` reduces the number of rows returned.
- `OFFSET` specifies where to begin counting the rows from.

### Inserting, Updating and Deleting Rows

- `INSERT` declares which table to write into, which data in which columns, and a number of rows to insert. Multiple rows can be inserted by listing them sequentially in the same INSERT command.
- `UPDATE` allows rows to be altered by specifying exactly which table, columns and rows to update. The datatypes of the columns must still match.

```SQL
UPDATE table
SET cloumn = value or expr
WHERE condition;
```

**!!!** ***Take care not to update wrong rows or all rows!***

- `DELETE` irrevocably removes a row or rows from the table. It is important to use a `WHERE` condition with this command.

**!!!** ***Take care not to delete wrong rows or all rows!***

## Table Commands

### Creating Tables

Tables can be created by with the `CREATE` command in which we designate the name of the table, a title for each column, the type of data allowed in those columns, and possibly constrainments or default values for any of the columns. The optional `IF NOT EXISTS` may be added to prevent overwriting an existing table.

```SQL
CREATE TABLE IF NOT EXISTS tabeltitle (
  column DataType TableConstraints DEFAULT default_value,
  another column DataType TableConstraints DEFAULT default_value,
  ...
);
```

When creating a table, we must designate datatypes for each of the columns. It is also possible to add constraints to each column if we wish.

#### Datatypes

| **DataType** | **Description** |
| --- | --- |
| `INTEGER` , `BOOLEAN` | Whole numbers and `true`/`false` values. The Booleans are sometimes stored as 0 or 1 |
| `FLOAT` , `DOUBLE` , `REAL` | Numbers more accurate than integers, with varying degrees of precision |
| `CHARACTER(num_char)` , `VARCHAR(num_char)` , `TEXT` | Strings of characters, a maximum number of characters is designated when using the first two |
| `DATE` , `DATETIME` | Stores dates/times |
| `BLOB` | Binary data |

#### Constraints

| **Constraint** | **Description** |
| --- | --- |
| `PRIMARY KEY` | Values in column are unique and can only be used on a single row of the table. They can therefore be used to identify that row |
| `AUTOINCREMENT` | Used in integer columns. It is auto-filled and incremented with each row of insertions |



[Back to Main](../README.md)