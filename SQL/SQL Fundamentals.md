
## 1. Database Basics

**Database** → organised collection of data.

**DBMS (Database Management System)** → software used to interact with databases.

Examples:

* MySQL
* PostgreSQL
* SQLite
* Microsoft SQL Server

### Relational database

Data is organised into **tables**.

A table contains:

* **Columns** → attributes/fields
* **Rows** → individual records
* **Primary Key** → uniquely identifies each row
* **Foreign Key** → links one table to another

Example:

| id | username | password    |
| -: | -------- | ----------- |
|  1 | alice    | password123 |
|  2 | bob      | hunter2     |

`id` could be the **primary key**.

---

# 2. Basic SQL Structure

SQL statements generally look like:

```sql
SELECT column
FROM table
WHERE condition;
```

Example:

```sql
SELECT username
FROM users
WHERE id = 1;
```

SQL keywords are usually written in uppercase for readability, but SQL is generally **case-insensitive** for keywords.

---

# 3. Database & Table Statements

### Show databases

```sql
SHOW DATABASES;
```

### Select a database

```sql
USE database_name;
```

### Show tables

```sql
SHOW TABLES;
```

### Create a database

```sql
CREATE DATABASE database_name;
```

### Create a table

```sql
CREATE TABLE users (
    id INT,
    username VARCHAR(50),
    password VARCHAR(100)
);
```

### Delete a database

```sql
DROP DATABASE database_name;
```

### Delete a table

```sql
DROP TABLE users;
```

⚠️ `DROP` removes the object itself.

---

# 4. CRUD Operations

CRUD = **Create, Read, Update, Delete**

## CREATE → INSERT

Add data:

```sql
INSERT INTO users (username, password)
VALUES ('alice', 'password123');
```

## READ → SELECT

Retrieve data:

```sql
SELECT * FROM users;
```

Retrieve specific columns:

```sql
SELECT username, password
FROM users;
```

## UPDATE

Modify existing data:

```sql
UPDATE users
SET password = 'newpassword'
WHERE username = 'alice';
```

⚠️ **Always be careful with `UPDATE` without `WHERE`.**

```sql
UPDATE users
SET password = 'newpassword';
```

This could modify **every row**.

## DELETE

Remove data:

```sql
DELETE FROM users
WHERE username = 'alice';
```

⚠️ Without `WHERE`, you can delete every row:

```sql
DELETE FROM users;
```

---

# 5. SELECT — The Most Important One

### Everything

```sql
SELECT * FROM users;
```

`*` = all columns.

### Specific columns

```sql
SELECT username, email
FROM users;
```

### Rename a result with AS

```sql
SELECT username AS user
FROM users;
```

---

# 6. WHERE — Filtering

```sql
SELECT *
FROM users
WHERE username = 'alice';
```

Common comparisons:

```sql
=       Equal
!=      Not equal
<>      Not equal
>       Greater than
<       Less than
>=      Greater than or equal
<=      Less than or equal
```

Example:

```sql
SELECT *
FROM users
WHERE id > 10;
```

---

# 7. AND / OR / NOT

### AND

Both conditions must be true:

```sql
SELECT *
FROM users
WHERE username = 'alice'
AND id = 1;
```

### OR

Either condition can be true:

```sql
SELECT *
FROM users
WHERE username = 'alice'
OR username = 'bob';
```

### NOT

Negates a condition:

```sql
SELECT *
FROM users
WHERE NOT username = 'alice';
```

---

# 8. Useful Clauses

## ORDER BY

Sort results.

Ascending:

```sql
SELECT *
FROM users
ORDER BY id ASC;
```

Descending:

```sql
SELECT *
FROM users
ORDER BY id DESC;
```

`ASC` = ascending
`DESC` = descending

---

## LIMIT

Restrict the number of results:

```sql
SELECT *
FROM users
LIMIT 5;
```

Useful when you only want the first few records.

---

## DISTINCT

Remove duplicate results:

```sql
SELECT DISTINCT username
FROM users;
```

---

## GROUP BY

Group records based on a column:

```sql
SELECT department, COUNT(*)
FROM employees
GROUP BY department;
```

---

## HAVING

Filter grouped results:

```sql
SELECT department, COUNT(*)
FROM employees
GROUP BY department
HAVING COUNT(*) > 5;
```

Think:

**WHERE → filters rows**

**HAVING → filters groups**

---

# 9. LIKE

Used for pattern matching.

### Starts with

```sql
SELECT *
FROM users
WHERE username LIKE 'admin%';
```

`%` = any number of characters.

### Ends with

```sql
WHERE username LIKE '%admin';
```

### Contains

```sql
WHERE username LIKE '%admin%';
```

`_` = exactly one character.

```sql
WHERE username LIKE 'adm_n';
```

---

# 10. NULL

`NULL` means **no value / unknown value**.

Don't use:

```sql
WHERE email = NULL;
```

Use:

```sql
WHERE email IS NULL;
```

Or:

```sql
WHERE email IS NOT NULL;
```

---

# 11. Operators

### Logical

```sql
AND
OR
NOT
```

### Comparison

```sql
=
!=
<>
>
<
>=
<=
```

### Range

```sql
BETWEEN
```

Example:

```sql
SELECT *
FROM users
WHERE id BETWEEN 10 AND 20;
```

### Multiple possible values

```sql
IN
```

Example:

```sql
SELECT *
FROM users
WHERE username IN ('alice', 'bob', 'charlie');
```

---

# 12. SQL Functions

Functions perform operations on data.

### COUNT

Count rows:

```sql
SELECT COUNT(*)
FROM users;
```

### SUM

```sql
SELECT SUM(price)
FROM products;
```

### AVG

```sql
SELECT AVG(price)
FROM products;
```

### MIN

```sql
SELECT MIN(price)
FROM products;
```

### MAX

```sql
SELECT MAX(price)
FROM products;
```

---

# 13. Common SQL Query Pattern

When you see a database question, think:

```sql
SELECT columns
FROM table
WHERE conditions
ORDER BY column
LIMIT number;
```

Example:

```sql
SELECT username, email
FROM users
WHERE id > 10
ORDER BY username ASC
LIMIT 5;
```

Read it as:

> Get the username and email from users where the ID is greater than 10, sort by username, and give me the first 5 results.

---

# 14. SQL in Cybersecurity

SQL matters in cybersecurity because web applications frequently use databases.

Typical flow:

```text
User
  ↓
Web Application
  ↓
SQL Query
  ↓
Database
  ↓
Result
  ↓
Web Application
  ↓
User
```

For example, a login might cause an application to query:

```sql
SELECT *
FROM users
WHERE username = 'alice'
AND password = 'password123';
```

This is why understanding SQL is important before learning **SQL injection**.

The important cybersecurity idea is:

> **User input can become part of a database query.**

If an application doesn't properly handle input, an attacker may be able to manipulate the query.

---

# 15. The SQL Commands Worth Memorising

For Cyber Security 101, prioritise these:

```text
SHOW DATABASES;
USE database;
SHOW TABLES;

SELECT * FROM table;
SELECT column FROM table;

WHERE
AND
OR
NOT

INSERT INTO
UPDATE
DELETE

ORDER BY
LIMIT
DISTINCT
GROUP BY
HAVING

LIKE
IN
BETWEEN
IS NULL
IS NOT NULL

COUNT()
SUM()
AVG()
MIN()
MAX()
```

