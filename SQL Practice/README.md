# SQL Practice
SQL(stands for Structured Query Language) is a standard language for accessing and manipulating databases.

RDBMS stands for Relational Database Management System.
RDBMS is the basis for SQL, and for all modern database systems such as MS SQL Server, IBM DB2, Oracle, MySQL, and Microsoft Access.
The data in RDBMS is stored in database objects called tables. A table is a collection of related data entries and it consists of columns and rows.

## The SQL SELECT Statement
 The SELECT statement is used to select data from a database.

### SELECT Syntax

```javascript
SELECT column1, column2, ...
FROM table_name;
```


If you want to select all the fields available in the table, use the following syntax:

```javascript
SELECT * FROM table_name;
```
## The SQL WHERE Clause
 The WHERE clause is used to filter records.
 It is used to extract only those records that fulfill a specified condition.

### WHERE Syntax
```javascript
SELECT column1, column2, ...
FROM table_name
WHERE condition;
```
## The SQL AND, OR and NOT Operators
The WHERE clause can be combined with AND, OR, and NOT operators.

The AND and OR operators are used to filter records based on more than one condition:

The AND operator displays a record if all the conditions separated by AND are TRUE.
The OR operator displays a record if any of the conditions separated by OR is TRUE.
The NOT operator displays a record if the condition(s) is NOT TRUE.

### AND Syntax
```javascript
SELECT column1, column2, ...
FROM table_name
WHERE condition1 AND condition2 AND condition3 ...;
```

### OR Syntax
```javascript
SELECT column1, column2, ...
FROM table_name
WHERE condition1 OR condition2 OR condition3 ...;
```
### NOT Syntax
```javascript
SELECT column1, column2, ...
FROM table_name
WHERE NOT condition;
```
## The SQL LIKE Operator
The LIKE operator is used in a WHERE clause to search for a specified pattern in a column.

There are two wildcards often used in conjunction with the LIKE operator:

 The percent sign (%) represents zero, one, or multiple characters
 The underscore sign (_) represents one, single character
### LIKE Syntax
```javascript
SELECT column1, column2, ...
FROM table_name
WHERE columnN LIKE pattern;
```
## The SQL IN Operator
The IN operator allows you to specify multiple values in a WHERE clause.

The IN operator is a shorthand for multiple OR conditions.

### IN Syntax
```javascript
SELECT column_name(s)
FROM table_name
WHERE column_name IN (value1, value2, ...);
```

| Operator | Description |
| --- | --- |
| `LIKE 'a%'` | Finds any values that start with "a" |
| `LIKE '%a'` | Finds any values that end with "a" |
| `LIKE '%or%'` | Finds any values that have "or" in any position |
| `LIKE '_r%'` | Finds any values that have "r" in the second position |
| `LIKE 'a_%'` | Finds any values that start with "a" and are at least 2 characters in length |
| `LIKE 'a__%'` | Finds any values that start with "a" and are at least 3 characters in length |
| `LIKE 'a%o'` | Finds any values that start with "a" and end with "o" |
| `NOT LIKE 'a%'` | Finds any values that do not start with "a" |
| `IN ('value1', 'value2', ...)` | Finds any values that match any of the specified values |
| `NOT IN ('value1', 'value2', ...)` | Finds any values that do not match any of the specified values |

## The SQL ORDER BY Keyword
The ORDER BY keyword is used to sort the result-set in ascending or descending order.

The ORDER BY keyword sorts the records in ascending order by default. To sort the records in descending order, use the DESC keyword.

### ORDER BY Syntax
```javascript
SELECT column1, column2, ...
FROM table_name
ORDER BY column1, column2, ... ASC|DESC;
```
## SQL JOIN
A JOIN clause is used to combine rows from two or more tables, based on a related column between them.

### Syntax
```javascript
SELECT column, another_table_column, …
FROM mytable
INNER JOIN another_table 
    ON mytable.id = another_table.id
WHERE condition(s)
ORDER BY column, … ASC/DESC
LIMIT num_limit OFFSET num_offset;
```
## The SQL INSERT INTO Statement
The INSERT INTO statement is used to insert new records in a table.

### INSERT INTO Syntax
It is possible to write the INSERT INTO statement in two ways:

1. Specify both the column names and the values to be inserted:
```javascript
INSERT INTO table_name (column1, column2, column3, ...)
```

VALUES (value1, value2, value3, ...);
2. If you are adding values for all the columns of the table, you do not need to specify the column names in the SQL query. However, make sure the order of the values is in the same order as the columns in the table. Here, the INSERT INTO syntax would be as follows:


```javascript
INSERT INTO table_name
VALUES (value1, value2, value3, ...);
```
## The SQL UPDATE Statement
The UPDATE statement is used to modify the existing records in a table.

### UPDATE Syntax

```javascript
UPDATE table_name
SET column1 = value1, column2 = value2, ...
WHERE condition;
```
## The SQL DELETE Statement
The DELETE statement is used to delete existing records in a table.

### DELETE Syntax

```javascript
DELETE FROM table_name WHERE condition;
```
## The SQL CREATE TABLE Statement
The CREATE TABLE statement is used to create a new table in a database.

### Syntax
```javascript
CREATE TABLE table_name (
    column1 datatype,
    column2 datatype,
    column3 datatype,
   ....
);
```
## The SQL DROP TABLE Statement
The DROP TABLE statement is used to drop an existing table in a database.

### Syntax

```javascript
DROP TABLE table_name;

```
## SQL ALTER TABLE Statement
The ALTER TABLE statement is used to add, delete, or modify columns in an existing table.

The ALTER TABLE statement is also used to add and drop various constraints on an existing table.

ALTER TABLE - ADD Column
### To add a column in a table, use the following syntax:

```javascript
ALTER TABLE table_name
ADD column_name datatype;
```
[img1](../img/1.png) 
[img2](../img/2.png) 
[img3](../img/3.png) 
[img4](../img/4.png) 
[img4](../img/5.png) 
[img6](../img/6.png) 

[imgDM1](../img/DM1.png) 
[imgDM2](../img/DM2.png) 
[imgDM3](../img/DM3.png) 
[imgDM4](../img/DM4.png) 
[imgDM5](../img/DM5.png) 
[imgDM6](../img/DM6.png) 


## Things I want to know more about