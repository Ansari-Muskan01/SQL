# SQL INDEX

An index is used to make searching data faster.

For example, if we frequently search employees based on their department, we can create an index on the `department` column.

### Before Creating Index

```sql
EXPLAIN
SELECT *
FROM Employees
WHERE department = 'IT';
```

Example output:

| type | possible_keys | key  | rows |
| ---- | ------------- | ---- | ---: |
| ALL  | NULL          | NULL |   10 |

Here:

* `ALL` means MySQL checks the complete table.
* `possible_keys = NULL` means no index is available for this query.
* `key = NULL` means no index is used.
* `rows = 10` means MySQL may check all 10 rows.

### Create Index

```sql
CREATE INDEX idx_department
ON Employees (department);
```

Now the `department` column has an index named `idx_department`.

### Check Index

```sql
SHOW INDEX FROM Employees;
```

Example output:

| Key_name       | Column_name | Index_type |
| -------------- | ----------- | ---------- |
| PRIMARY        | emp_id      | BTREE      |
| idx_department | department  | BTREE      |

Here:

* `PRIMARY` is the index created for the primary key.
* `idx_department` is the index we created.
* `department` is the column on which the index is created.
* `BTREE` is the index structure used by MySQL.

### Check Query Again

```sql
EXPLAIN
SELECT *
FROM Employees
WHERE department = 'IT';
```

Example output when MySQL uses the index:

| type | possible_keys  | key            | rows |
| ---- | -------------- | -------------- | ---: |
| ref  | idx_department | idx_department |    4 |

Here:

* `possible_keys` shows the index that MySQL can use.
* `key` shows the index actually used.
* `ref` means MySQL is using the index to find matching values.
* `rows` shows the approximate number of rows MySQL expects to check.

So, without an index, MySQL may scan the complete table.
With an index, MySQL can use the index to find the required rows more efficiently.

**Note:** If the table contains very few rows, MySQL may still choose a full table scan even after creating an index. The final decision is made by the MySQL optimizer.
