**# Technical Paper**
# **Basic SQL, Joins and Aggregations in SQL.**
---
![SQL Logo](https://mpng.subpng.com/20181122/hjb/kisspng-logo-computer-icons-brand-computer-file-portable-n-5bf73769032952.747995641542928233013.jpg)

## *What is SQL?*
SQL is Structured Query Language, which is a computer language for storing, manipulating and retrieving data stored in relational database.
SQL is the standard language for Relation Database System. All relational database management systems like MySQL, MS Access, Oracle, Sybase, Informix, postgres and SQL Server use SQL as standard database language.

Also, they are using different dialects, such as:
* MS SQL Server using T-SQL,
* Oracle using PL/SQL,
* MS Access version of SQL is called JET SQL (native format) etc.
---
## *Why SQL?*
* Allows users to access data in relational database management systems.
* Allows users to describe the data.
* Allows users to define the data in database and manipulate that data.
* Allows to embed within other languages using SQL modules, libraries & pre-compilers.
* Allows users to create and drop databases and tables.
* Allows users to create view, stored procedure, functions in a database.
* Allows users to set permissions on tables, procedures and views
---
## *History:*
* 1970 -- Dr. E. F. "Ted" of IBM is known as the father of relational databases. He described a relational model for databases.
* 1974 -- Structured Query Language appeared.
* 1978 -- IBM worked to develop Codd's ideas and released a product named System/R.
* 1986 -- IBM developed the first prototype of relational database and standardized by ANSI. The first relational database was released by Relational Software and its later becoming Oracle.
---
## *SQL Process:*
When you are executing an SQL command for any RDBMS, the system determines the best way to carry out your request and SQL engine figures out how to interpret the task.

There are various components included in the process. These components are:
* Query Dispatcher.
* Optimization Engines.
* Classic Query Engine.
* SQL Query Engine, etc.

Classic query engine handles all non-SQL queries,but SQL query engine won't handle logical files.

Following is a simple diagram showing SQL Architecture:
![SQL Architecture](https://static.javatpoint.com/sqlpages/images/sql-process.png)

---
## *Common SQL Commands:*
* ### <span style="color:green">ALTER TABLE</span>
``` sql
ALTER TABLE table_name 
ADD column_name datatype;
```
ALTER TABLE lets you add columns to a table in a database.

* ### <span style="color:green">AND / OR</span>
``` sql
SELECT column_name(s)
FROM table_name
WHERE column_1 = value_1
  AND|OR column_2 = value_2;
```
AND is an operator that combines two conditions. Both conditions must be true for the row to be included in the result set.
OR is an operator that filters the result set to only include rows where either condition is true.
* ### <span style="color:green">BETWEEN</span>
``` sql
SELECT column_name(s)
FROM table_name
WHERE column_name BETWEEN value_1 AND value_2;
```
The BETWEEN operator is used to filter the result set within a certain range. The values can be numbers, text or dates.
* ### <span style="color:green">CREATE TABLE</span>
```sql
CREATE TABLE table_name (
  column_1 datatype, 
  column_2 datatype, 
  column_3 datatype
);
```
CREATE TABLE creates a new table in the database. It allows you to specify the name of the table and the name of each column in the table.
* ### <span style="color:green">DELETE</span>
```sql
DELETE FROM table_name
WHERE some_column = some_value;
```
DELETE statements are used to remove rows from a table.
* ### <span style="color:green">GROUP BY</span>
```sql
SELECT column_name, COUNT(*)
FROM table_name
GROUP BY column_name;
```
GROUP BY is a clause in SQL that is only used with aggregate functions. It is used in collaboration with the SELECT statement to arrange identical data into groups.
* ### <span style="color:green">INSERT</span>
```sql
INSERT INTO table_name (column_1, column_2, column_3) 
VALUES (value_1, 'value_2', value_3);
```
INSERT statements are used to add a new row to a table.
* ### <span style="color:green">LIKE</span>
```sql
SELECT column_name(s)
FROM table_name
WHERE column_name LIKE pattern;
```
LIKE is a special operator used with the WHERE clause to search for a specific pattern in a column.
* ### <span style="color:green">SELECT</span>
```sql
SELECT column_name 
FROM table_name;
```
SELECT statements are used to fetch data from a database. Every query will begin with SELECT.
* ### <span style="color:green">WHERE</span>
```sql
SELECT column_name(s)
FROM table_name
WHERE column_name operator value;
```
WHERE is a clause that indicates you want to filter the result set to include only rows where the following condition is true.
* ### <span style="color:green">WITH</span>
```sql
WITH temporary_name AS (
   SELECT *
   FROM table_name)
SELECT *
FROM temporary_name
WHERE column_name operator value;
```
WITH clause lets you store the result of a query in a temporary table using an alias. You can also define multiple temporary tables using a comma and with one instance of the WITH keyword.
The WITH clause is also known as common table expression (CTE) and subquery factoring.
## *SQL Joins.*
The SQL Joins clause is used to combine records from two or more tables in a database. A JOIN is a means for combining fields from two tables by using values common to each.
### *SQL Join Types:*
There are different types of joins available in SQL:
* #### <span style="color:green">INNER JOIN:</span>
```sql
SELECT column_name(s)
FROM table1
INNER JOIN table2
ON table1.column_name = table2.column_name;
```
Returns rows when there is a match in both tables.
![Inner Join](https://static.javatpoint.com/sqlpages/images/types-of-sql-join.png)
* #### <span style="color:green">LEFT JOIN:</span>
```sql
SELECT column_name(s)
FROM table1
LEFT JOIN table2
ON table1.column_name = table2.column_name;
```
Returns all rows from the left table, even if there are no matches in the right table.
![Left Join](https://static.javatpoint.com/sqlpages/images/types-of-sql-join4.png)
* #### <span style="color:green">RIGHT JOIN:</span>
```sql
SELECT column_name(s)
FROM table1
RIGHT JOIN table2
ON table1.column_name = table2.column_name;
```
Returns all rows from the right table, even if there are no matches in the left table.
![Right Join](https://static.javatpoint.com/sqlpages/images/types-of-sql-join6.png)
* #### <span style="color:green">FULL JOIN or FULL OUTER JOIN:</span>
```sql
SELECT column_name(s)
FROM table1
FULL OUTER JOIN table2
ON table1.column_name = table2.column_name
WHERE condition; 
```
Returns rows when there is a match in one of the tables.
![Full Join](https://static.javatpoint.com/sqlpages/images/types-of-sql-join8.png)
* #### <span style="color:green">SELF JOIN:</span>
```sql
SELECT column_name(s)
FROM table1 T1, table1 T2
WHERE condition;
```
Is used to join a table to itself as if the table were two tables, temporarily renaming at least one
table in the SQL statement.
* #### <span style="color:green">CARTESIAN JOIN:</span>
```sql
SELECT column_name(s)
FROM table1
CROSS JOIN table2;

```
Returns the Cartesian product of the sets of records from the two or more joined tables.

## SQL Aggregate Functions.
In database management an aggregate function is a function where the values of multiple rows are grouped together as input on certain criteria to form a single value of more significant meaning.
### SQL Aggregate Functions Types:
There are different types of agregate functions in SQL.
* #### <span style="color:green">COUNT()</span>
```sql
SELECT COUNT(column_name)
FROM table_name;
```
COUNT() is a function that takes the name of a column as an argument and counts the number of rows where the column is not NULL.
* #### <span style="color:green">SUM()</span>
```sql
SELECT SUM(column_name)
FROM table_name;
```
SUM() is a function that takes the name of a column as an argument and returns the sum of all the values in that column.
* #### <span style="color:green">MIN()</span>
```sql
SELECT MIN(column_name)
FROM table_name;
```
MIN() is a function that takes the name of a column as an argument and returns the smallest value in that column.
* #### <span style="color:green">MAX()</span>
```sql
SELECT MAX(column_name)
FROM table_name;
```
MAX() is a function that takes the name of a column as an argument and returns the largest value in that column.
* #### <span style="color:green">AVG()</span>
```sql
SELECT AVG(column_name)
FROM table_name;
```
AVG() is an aggregate function that returns the average value for a numeric column.
## *References.*
* https://beginner-sql-tutorial.com/sql.htm
* https://www.sqltutorial.org
* https://www.w3schools.com/sql
