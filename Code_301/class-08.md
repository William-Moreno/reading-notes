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

### Inserting and Updating Rows

- `INSERT` declares which table to write into, which data in which columns, and a number of rows to insert. Multiple rows can be inserted by listing them sequentially in the same INSERT command.
- `UPDATE` allows rows to be altered by specifying exactly which table, columns and rows to update. The datatypes of the columns must still match.

```SQL
UPDATE table
SET cloumn = value or expr
WHERE condition;
```

**!** ***Take care not to update wrong rows or all rows***


[Back to Main](../README.md)