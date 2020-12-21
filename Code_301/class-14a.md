# Database Normalization
---

The following notes were distilled from *Kris Wenzel's* article ["Database Normalization *(Explained in Simple English)*"](https://www.essentialsql.com/get-ready-to-learn-sql-database-normalization-explained-in-simple-english/).


### Introduction

**Database Normalization** is the process of organizing a database into tables and columns. This process is based on the concept that each table should pertain to a specific topic and should only include data that supports that topic. Limiting a table to a single purpose, reduces the amount of duplicated data within our database. In turn, this helps to eliminate some of the issues which arise from database modification.

There are established rules to accomplish the previously mentioned objectives. As we implement these rules, new labes will be formed. There are three successive forms of normalization that most databases tend to adhere to. As they progress through these tiers, databases become less prone to modification anomalies as they become more tightly focused on specific topics or purposes.

### Reasoning

Databases should be normalized for tbree reasons:

1. Minimization of duplicate data
1. Avoid or reduce data modification issues
1. Simplify queries

Consider the following table:

**SalesStaff**


| ***EmployeeID*** | **SalesPerson** | **SalesOffice** | **OfficeNumber** | **Customer1** | **Customer2** | **Customer3** |
| --- | --- | --- | --- | --- | --- | --- |
| 1003 | Mary Smith | Chicago | 312-555-1212 | Ford | GM | - |
| 1004 | John Hunt | New York | 212-555-1212 | Dell | HP | Apple |
| 1005 | Martin Hap | Chicago | 312-555-1212 | Boeing | - | - |

***EmployeeID*** is the primary key column.

This table *Serves many purposes* as opposed to a single one:

1. Identify salespeople
1. List sales offices and phone numbers
1. salesperson and sales office association
1. Displaying a salesperson's clients

Because this table serves many purposes, it is prone to data duplication, data update issues and it increses the effort needed to query it.

### Data Duplication/Modification Anomalies

The table lists both the SalesOffice and the OfficeNumber for each SalesPerson. It is duplicaed information and presents multiple problems:

1. increases storage
1. decreases performance
1. becomes harder to maintain data changes

If the location of an office were to change, all of the entries on this table would have to be updated. This is known as a **modification anomaly**. There are three types of modification anomalies which can occur:

- **Insert Anomaly** - There are facts which cannot be recorded until all of the data for the entire row is know
- **Update Anomaly** - Having the same data in several rows means that if an element changes multiples updates with have to be made. If they aren't all changed to reflect the new data, they can lead to inconsistencies.

- **Deletion Anomaly** - Deletion of a row removes multuple sets of facts. *(in the example below, the New York SalesOffice and the OfficeNumber is also lost when the SalesPeron John Hunt is removed.)*

| ***EmployeeID*** | **SalesPerson** | **SalesOffice** | **OfficeNumber** | **Customer1** | **Customer2** | **Customer3** |
| --- | --- | --- | --- | --- | --- | --- |
| 1003 | Mary Smith | Chicago | 312-555-1212 | Ford | GM | - |
| ~~1004~~ | ~~John Hunt~~ | ~~New York~~ | ~~212-555-1212~~ | ~~Dell~~ | ~~HP~~ | ~~Apple~~ |
| 1005 | Martin Hap | Chicago | 312-555-1212 | Boeing | - | - |

### Searching and Sorting

The final issue with this table is that it makes queries to find data such as specific customers more difficule by requiring a longer or more convoluted query. If all of the customer data were in one column of the table it would make such a query simpler. This table would also make sorting by customer challenging, requiring three separate `UNION` queries to complete.

These issues can be mitigated by separating the information an putting it into multiple tables, each serving a more singular purpose.

### Definition

There are 3 progressive forms of database normaliztion, each successive form building upon the previous form:

- **First Normal Form** - Information is stored in a realtion table. Each column contains an atomis value and there are no repeating groups of columns

- **Second Normal Form** - All of the tables depend on its primary key

- **Third Normal Form** - None of the table's columns are transitively dependent on the primary key.

[Back to Main](../README.md)