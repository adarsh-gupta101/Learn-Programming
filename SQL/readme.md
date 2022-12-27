[![Adarsh gupta](https://miro.medium.com/fit/c/96/96/1*t-ya5MdH4ALyrJ-TMnWneQ.png)

<!-- ](https://medium.com/?source=post_page-----fb7be2dd3233--------------------------------)[Adarsh gupta](https://medium.com/?source=post_page-----fb7be2dd3233--------------------------------)Follow

Dec 27

·11 min read -->

Complete SQL guide for Developers
=================================

SQL (Structured Query Language) is a programming language used to manage and manipulate data stored in relational databases. It is a standard language for interacting with databases and is used to create, update, delete, and retrieve data from a database.

SQL is used to define the structure of a database, including the data types, relationships, and constraints that determine how data can be stored and accessed. It is also used to write queries that retrieve data from a database based on specific criteria, as well as to perform other operations such as inserting, updating, and deleting data.

Download and install MySQL
==========================

You can download the MySQL Community Server from the [MySQL website](https://dev.mysql.com/downloads/mysql/). Follow the installation wizard to complete the process.

Once the installation is finished, you can run the following command to access the MySQL command line interface:

```
mysql -u username -p
```

Note: You may need to set the environment variables in order to start working with MySQL.

Basic SQL Commands
==================

Data definition language (DDL)
------------------------------

Data definition language (DDL) is a subset of SQL that is used to define the database schema. It consists of a set of commands that can be used to create, modify, and delete database objects such as tables, indices, and views.

CREATE TABLE
------------

The `CREATE TABLE` statement is used to create a new table in a database.

```
CREATE TABLE table\_name (  
  column_1 datatype [constraint],  
  column_2 datatype [constraint],  
  ...  
  column_n datatype [constraint]  
);
```

Here, `table_name` is the name of the table that you want to create, and `column_1`, `column_2`, etc. are the names of the columns in the table. Each column has a data type that specifies the type of data that it can store, such as `INTEGER`, `VARCHAR`, or `DATE`. You can also specify constraints for each column, which are rules that determine how the data in the column can be used or modified.

Here is an Example:-

```
CREATE TABLE users (  
  id SERIAL PRIMARY KEY,  
  name VARCHAR(255) NOT NULL,  
  email VARCHAR(255) NOT NULL,  
  age INTEGER CHECK (age > 0)  
);
```

This `CREATE TABLE` statement would create a table called "users" with four columns: "id", "name", "email", and "age". The "id" column is of type `SERIAL` and is the primary key of the table, meaning that it is a unique identifier for each row. The "name" and "email" columns are of type `VARCHAR` and cannot be `NULL`. The "age" column is of type `INTEGER` and has a `CHECK` constraint that ensures that the value is greater than 0.

ALTER
-----

The `ALTER` command is used to modify existing database objects. For example:

```
ALTER TABLE users ADD COLUMN phone VARCHAR(255);
```

This `ALTER` statement would add a new column called "phone" to the "users" table.

DROP
----

The `DROP` command is used to delete existing database objects. For example:

```
DROP TABLE users;
```

This `DROP` statement would delete the "users" table.

Data manipulation
-----------------

Data manipulation refers to the process of modifying, adding, or deleting data in a database

Select
------

The `SELECT` statement is one of the most commonly used SQL commands, and is used to retrieve data from a database. Here is a guide to using the `SELECT` statement in SQL:

```
SELECT column\_1, column\_2, ..., column\_n  
FROM table\_name;
```

Here, `column_1`, `column_2`, etc. are the names of the columns that you want to retrieve data from, and `table_name` is the name of the table that contains the data. You can specify as many columns as you want, separated by commas.

Wildcard

If you want to retrieve all columns from a table, you can use the `*` wildcard in place of the column list:

```
SELECT \*  
FROM table\_name;
```

**WHERE Clause**

You can use the `WHERE` clause to specify criteria for which rows to include in the results. For example:

```
SELECT column\_1, column\_2, ..., column\_n  
FROM table\_name  
WHERE condition;
```

Here, `condition` is a boolean expression that specifies the criteria for inclusion. For example, the following query would retrieve all rows where the value of `column_1` is greater than 10:

```
SELECT column\_1, column\_2, ..., column\_n  
FROM table\_name  
WHERE column\_1 > 10;
```

LIMIT Clause
------------

The `LIMIT` clause allows you to specify a maximum number of rows to include in the results. For example:

```
SELECT column\_1, column\_2, ..., column\_n  
FROM table\_name  
LIMIT num\_rows;
```

Here, `num_rows` is the maximum number of rows to include in the results.

ORDER BY Clause
---------------

The `ORDER BY` the clause allows you to specify the order in which the rows should be returned. For example:

```
SELECT column\_1, column\_2, ..., column\_n  
FROM table\_name  
ORDER BY column\_name \[ASC | DESC\];
```

Here, `column_name` is the name of the column that you want to use to order the results, and `ASC` or `DESC` specifies whether the results should be sorted in ascending or descending order, respectively.

Examples
--------

Here are some examples of `SELECT` statements using the various clauses and options discussed above:

```
\-- Retrieve all columns from the "users" table  
SELECT \* FROM users;  
  
\-- Retrieve only the "name" and "email" columns from the "users" table  
  
SELECT name, email FROM users;  
\-- Retrieve all columns from the "users" table, but only for rows where the "age" column is greater than 30  
SELECT \* FROM users WHERE age > 30;  
\-- Retrieve all columns from the "users" table, but only the first 10 rows  
SELECT \* FROM users LIMIT 10;  
\-- Retrieve all columns from the "users" table, ordered by the "name" column in ascending order  
SELECT \* FROM users ORDER BY name ASC;  

```

INSERT
------

The `INSERT` statement is used to add new rows to a table in a database.

```
INSERT INTO table\_name (column\_1, column\_2, ..., column\_n)  
VALUES (value\_1, value\_2, ..., value\_n);
```

Here is an example of an `INSERT` statement that adds a new row to a table called "users":

```
INSERT INTO users (name, email, age)  
VALUES ('John Smith', 'john@example.com', 35);
```

This `INSERT` statement would add a new row to the "users" table with the values 'John Smith', '[john@example.com](mailto:john@example.com)', and 35 in the "name", "email", and "age" columns, respectively.

**Additional Options**

There are several additional options that you can use with the `INSERT` statement:

*   `RETURNING`: This clause allows you to return the values of the inserted row.

```
INSERT INTO users (name, email, age)  
VALUES ('John Smith', 'john@example.com', 35)  
RETURNING id, name, email, age;
```

*   `SELECT`: This clause allows you to insert data from a `SELECT` statement into a table.

```
INSERT INTO users (name, email, age)  
SELECT name, email, age FROM old\_users WHERE age > 30;
```

*   `DEFAULT VALUES`: This clause allows you to insert a row with the default values for all columns.

```
INSERT INTO users DEFAULT VALUES;
```

UPDATE
------

The `UPDATE` statement is used to modify existing rows in a table in a database.

```
UPDATE table\_name  
SET column\_1 = value\_1, column\_2 = value\_2, ..., column\_n = value\_n  
WHERE condition;
```

Here is an example of an UPDATE statement that updates the “age” column for all rows in the “users” table:

```
UPDATE users  
SET age = age + 1;
```

This `UPDATE` statement would increase the value of the "age" column by 1 for all rows in the "users" table.

There are several additional options that you can use with the `UPDATE` statement:

*   `RETURNING`: This clause allows you to return the values of the updated rows.

```
UPDATE users  
SET age = age + 1  
RETURNING id, name, email, age;
```

*   `FROM`: This clause allows you to update a table based on data from another table.

```
UPDATE users  
SET name = new\_users.name, email = new\_users.email  
FROM new\_users  
WHERE users.id = new\_users.id;
```

*   `JOIN`: This clause allows you to update a table based on a join with another table

```
UPDATE users  
SET name = old\_users.name, email = old\_users.email  
FROM old\_users  
JOIN users ON old\_users.id = users.id;
```

DELETE
======

The `DELETE` the statement is used to delete rows from a table in a database.

```
DELETE FROM table\_name  
WHERE condition;
```

Here is an example of a `DELETE` statement that deletes all rows from the "users" table:

```
DELETE FROM users;
```

Sorting and Filtering Data
--------------------------

You can use the `ORDER BY` and `WHERE` clauses to sort and filter data in a table.

```
\-- Sort the results of a SELECT statement by the "name" column in ascending order  
SELECT \* FROM users ORDER BY name ASC;  
  
\-- Filter the results of a SELECT statement to include only rows where the "age" column is greater than 30  
SELECT \* FROM users WHERE age > 30;
```

Aggregate Functions
-------------------

SQL provides several aggregate functions that allow you to perform calculations on a set of values. Some common aggregate functions include:

*   `AVG`: Calculates the average of a set of values
*   `COUNT`: Counts the number of rows in a table or the number of non-NULL values in a column
*   `MAX`: Finds the maximum value in a set of values
*   `MIN`: Finds the minimum value in a set of values
*   `SUM`: Calculates the sum of a set of values

For example:

```
\-- Find the average age of all users  
SELECT AVG(age) FROM users;  
\-- Count the number of users in the table  
SELECT COUNT(\*) FROM users;
```

NULL Values
-----------

SQL has a special value called `NULL` that represents an unknown or missing value. You can use the `IS NULL` and `IS NOT NULL` operators to test for NULL values in a column. For example:

```
\-- Find all users where the "email" column is NULL  
SELECT \* FROM users WHERE email IS NULL;  
  
\-- Find all users where the "email" column is NOT NULL  
SELECT \* FROM users WHERE email IS NOT NULL;
```

Joins
=====

INNER JOIN
----------

An `INNER JOIN` returns only the rows that match the join condition in both tables. For example:

```
SELECT \*  
FROM users INNER JOIN orders  
ON users.id = orders.user\_id;
```

This `SELECT` statement would return all rows from the "users" and "orders" tables where the "id" column in the "users" table matches the "user\_id" column in the "orders" table.

LEFT JOIN
---------

A `LEFT JOIN` (also called a "left outer join") returns all rows from the left table, and any matching rows from the right table. If there is no match, NULL values are returned for the right-side columns. For example:

```
SELECT \*  
FROM users LEFT JOIN orders  
ON users.id = orders.user\_id;
```

This `SELECT` statement would return all rows from the "users" table, and any matching rows from the "orders" table where the "id" column in the "users" table matches the "user\_id" column in the "orders" table. If there is no match, NULL values would be returned for the columns from the "orders" table.

RIGHT JOIN
----------

A `RIGHT JOIN` (also called a "right outer join") is similar to a `LEFT JOIN`, but it returns all rows from the right table, and any matching rows from the left table. If there is no match, NULL values are returned for the left-side columns.

FULL JOIN
---------

A `FULL JOIN` (also called a "full outer join") returns all rows from both tables, regardless of whether there is a match. If there is no match, NULL values are returned for the non-matching columns.

I hope this helps! Let me know if you have any questions about `JOIN`s in SQL.

Subqueries
==========

A subquery is a SELECT statement that is nested within another SELECT, INSERT, UPDATE, DELETE, or SET statement, or within another subquery. Subqueries can be used to return data that will be used in the main query as a condition or as a value.

Syntax
------

The basic syntax of a subquery is as follows:

```
SELECT column\_1, column\_2, ...  
FROM table\_name  
WHERE column\_name \[operator\] (  
  SELECT column\_name  
  FROM table\_name  
  WHERE condition  
);
```

Here, the subquery is placed within parentheses and is executed first. The results of the subquery are then used in the main query.

Example
-------

Here is an example of a subquery that returns the names of all users who have placed an order:

```
SELECT name  
FROM users  
WHERE id IN (  
  SELECT user\_id  
  FROM orders  
);
```

This `SELECT` statement would return the names of all users in the "users" table where the "id" column matches the "user\_id" column in the "orders" table.

Data control language (DCL)
---------------------------

Data control language (DCL) is a subset of SQL that is used to control access to the database. It consists of a set of commands that can be used to grant and revoke privileges to users, and to manage transactions.

GRANT
-----

The `GRANT` command is used to give a user or role access to database objects. For example:

```
GRANT SELECT, INSERT, UPDATE ON users TO user\_1;
```

This `GRANT` statement would give the user "user\_1" the ability to `SELECT`, `INSERT`, and `UPDATE` rows in the "users" table.

REVOKE
------

The `REVOKE` command is used to remove access to database objects from a user or role. For example:

```
REVOKE SELECT, INSERT, UPDATE ON users FROM user\_1;
```

This `REVOKE` statement would remove the ability of the user "user\_1" to `SELECT`, `INSERT`, and `UPDATE` rows in the "users" table.

COMMIT
------

The `COMMIT` command is used to save the changes made in a transaction to the database. For example:

```
BEGIN TRANSACTION;  
  UPDATE users SET age = age + 1 WHERE id = 1;  
  UPDATE users SET age = age + 2 WHERE id = 2;  
COMMIT;
```

This `COMMIT` statement would save the changes made by the two `UPDATE` statements to the "users" table.

ROLLBACK
--------

The `ROLLBACK` command is used to undo the changes made in a transaction. For example:

```
BEGIN TRANSACTION;  
  UPDATE users SET age = age + 1 WHERE id = 1;  
  UPDATE users SET age = age + 2 WHERE id = 2;  
ROLLBACK;
```

This `ROLLBACK` statement would undo the changes made by the two `UPDATE` statements to the "users" table.

Indexes
-------

An index is a data structure that is used to improve the performance of database queries. Indexes allow the database to quickly locate and retrieve the rows that match a specific condition, without having to scan the entire table.

```
CREATE INDEX index\_name ON table\_name (column\_name);
``````
CREATE UNIQUE INDEX email\_index ON users (email);
```

This `CREATE INDEX` statement would create a unique index called "email\_index" on the "email" column of the "users" table. This would ensure that there are no duplicate values in the "email" column.

Stored procedures and functions
===============================

A stored procedure is a group of SQL statements that are stored in the database and can be executed as a single unit.

Stored procedures can accept input parameters and return output parameters, and can be used to perform a wide range of tasks, from simple queries to complex business logic.

```
\`CREATE PROCEDURE procedure\_name (  
  IN parameter\_1\_name datatype,  
  IN parameter\_2\_name datatype,  
  ...  
  OUT output\_parameter\_name datatype  
)  
BEGIN  
  -- SQL statements go here  
END;
```

Here, `procedure_name` is the name of the stored procedure, `parameter_1_name` and `parameter_2_name` are the names of the input parameters, `output_parameter_name` is the name of the output parameter, and `datatype` is the data type of the parameter.

Here is an example of a stored procedure that returns the names of all users who have placed an order:

```
CREATE PROCEDURE get\_customers (  
  OUT output\_parameter\_name VARCHAR(255)  
)  
BEGIN  
  SELECT name INTO output\_parameter\_name  
  FROM users  
  WHERE id IN (  
    SELECT user\_id FROM orders  
  );  
END;
```

This stored procedure would accept an output parameter called “output\_parameter\_name” of type `VARCHAR(255)`, and would return the names of all users in the "users" table where the "id" column matches the "user\_id" column in the "orders" table.

Transactions
============

In SQL, a "transaction" is a unit of work that is performed as a single logical operation. Transactions allow you to execute a series of SQL statements as a single unit, either committing the changes to the database if all statements are successful, or rolling back the changes if any errors occur.

```
BEGIN TRANSACTION;  
  
\-- SQL statements go here  
  
COMMIT;
```

To roll back the changes made in a transaction, you can use the `ROLLBACK` statement instead of `COMMIT`.

```
BEGIN TRANSACTION;  
  UPDATE users SET age = age + 1 WHERE id = 1;  
  UPDATE users SET age = age + 2 WHERE id = 2;  
COMMIT;
```

This transaction would update the “age” column of the rows with “id” 1 and 2 in the “users” table, and would commit the changes to the database. If any errors occurred while executing the `UPDATE` statements, the changes would be rolled back and the database would remain unchanged.

Conclusion

SQL is a powerful and versatile language that is essential for anyone looking to work with data. Whether you are just starting out with SQL or are an experienced user, there is always more to learn and ways to improve your skill.

This detailed blog is enough for you to start working with SQL.

Follow @Adarsh-gupta for more
