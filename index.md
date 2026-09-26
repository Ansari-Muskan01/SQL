# SQL INDEX

An index helps MySQL find data quickly without checking every row in the table.

## Sample Employees Table

CREATE TABLE Employees (<br>
    emp_id INT PRIMARY KEY,<br>
    emp_name VARCHAR(50),<br>
    department VARCHAR(20),<br>
    salary INT<br>
);<br>

INSERT INTO Employees VALUES<br>
(1, 'Aditi', 'IT', 75000),<br>
(2, 'Rahul', 'IT', 55000),<br>
(3, 'Sneha', 'HR', 48000),<br>
(4, 'Karan', 'HR', 55000),<br>
(5, 'Meena', 'HR', 60000),<br>
(6, 'Vikas', 'Sales', 50000),<br>
(7, 'Priya', 'Sales', 75000),<br>
(8, 'Farhan', 'Sales', 45000),<br>
(9, 'Divya', 'IT', 60000),<br>
(10, 'Aman', 'IT', 58000);<br>


### Employees Table

| emp_id | emp_name | department | salary |
| -----: | -------- | ---------- | -----: |
|      1 | Aditi    | IT         |  75000 |
|      2 | Rahul    | IT         |  55000 |
|      3 | Sneha    | HR         |  48000 |
|      4 | Karan    | HR         |  55000 |
|      5 | Meena    | HR         |  60000 |
|      6 | Vikas    | Sales      |  50000 |
|      7 | Priya    | Sales      |  75000 |
|      8 | Farhan   | Sales      |  45000 |
|      9 | Divya    | IT         |  60000 |
|     10 | Aman     | IT         |  58000 |

## Before Creating Index

First, check how MySQL executes the query.<br>

EXPLAIN SELECT * FROM Employees WHERE department = 'IT';<br>

Example output:

| id | select_type | table     | type | possible_keys | key  | rows | Extra       |
| -: | ----------- | --------- | ---- | ------------- | ---- | ---: | ----------- |
|  1 | SIMPLE      | Employees | ALL  | NULL          | NULL |   10 | Using where |

Here:

* `ALL` means MySQL checks the complete table.
* `possible_keys = NULL` means there is no index available for this query.
* `key = NULL` means no index is being used.
* `rows = 10` means MySQL may check all 10 rows.

The query returns these records:<br>
SELECT * FROM Employees WHERE department = 'IT';<br>


### Output

| emp_id | emp_name | department | salary |
| -----: | -------- | ---------- | -----: |
|      1 | Aditi    | IT         |  75000 |
|      2 | Rahul    | IT         |  55000 |
|      9 | Divya    | IT         |  60000 |
|     10 | Aman     | IT         |  58000 |

## Create Index

Now create an index on the `department` column.<br>


CREATE INDEX idx_department ON Employees (department);<br>

`idx_department` is the name given to the index.<br>

## Check Index

SHOW INDEX FROM Employees;


Example output:

| Table     | Key_name       | Column_name | Non_unique | Index_type |
| --------- | -------------- | ----------- | ---------: | ---------- |
| Employees | PRIMARY        | emp_id      |          0 | BTREE      |
| Employees | idx_department | department  |          1 | BTREE      |

Here:

* `PRIMARY` is the index created for the primary key.
* `idx_department` is the index we created.
* `department` is the column on which the index is created.
* `Non_unique = 0` means duplicate values are not allowed.
* `Non_unique = 1` means duplicate values are allowed.
* `BTREE` is the index structure used by MySQL.

## Check Query Again

Now run the same query again.

EXPLAIN SELECT * FROM Employees WHERE department = 'IT';

Example output when MySQL uses the index:

| id | select_type | table     | type | possible_keys  | key            | rows | Extra |
| -: | ----------- | --------- | ---- | -------------- | -------------- | ---: | ----- |
|  1 | SIMPLE      | Employees | ref  | idx_department | idx_department |    4 | NULL  |

Here:

* `possible_keys` shows the index that MySQL can use.
* `key` shows the index actually used.
* `ref` means MySQL is using the index to find matching values.
* `rows = 4` means MySQL expects to check approximately 4 matching rows.

The query output remains the same:

| emp_id | emp_name | department | salary |
| -----: | -------- | ---------- | -----: |
|      1 | Aditi    | IT         |  75000 |
|      2 | Rahul    | IT         |  55000 |
|      9 | Divya    | IT         |  60000 |
|     10 | Aman     | IT         |  58000 |

The **result of the query does not change**. The index changes how MySQL finds the data.

### Without Index vs With Index

| Without Index            | With Index              |
| ------------------------ | ----------------------- |
| MySQL may check all rows | MySQL can use the index |
| `type = ALL`             | `type = ref`            |
| `key = NULL`             | `key = idx_department`  |
| Full table scan          | Index-based search      |

