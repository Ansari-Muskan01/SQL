# SQL INDEX

## 1. Without Index

```sql
EXPLAIN
SELECT *
FROM Employees
WHERE department = 'IT';
```

### Output

| id | select_type | table     | type | possible_keys | key  | rows | Extra       |
| -: | ----------- | --------- | ---- | ------------- | ---- | ---: | ----------- |
|  1 | SIMPLE      | Employees | ALL  | NULL          | NULL |   10 | Using where |

### Explanation

* `type = ALL` → MySQL is checking the table rows.
* `key = NULL` → No index is being used.
* `rows = 10` → MySQL may check all 10 rows.
* This is called a **Full Table Scan**.

---

## 2. Create Index

```sql
CREATE INDEX idx_department
ON Employees (department);
```

The index is created on the `department` column.

---

## 3. Check the Index

```sql
SHOW INDEX FROM Employees;
```

### Output

| Table     | Key_name       | Column_name | Index_type |
| --------- | -------------- | ----------- | ---------- |
| Employees | PRIMARY        | emp_id      | BTREE      |
| Employees | idx_department | department  | BTREE      |

### Explanation

* `PRIMARY` → Index created automatically for the Primary Key.
* `idx_department` → Index created by us.
* `department` → Column on which we created the index.
* `BTREE` → Type of index structure used by MySQL.

---

## 4. With Index

Run the same query again:

```sql
EXPLAIN
SELECT *
FROM Employees
WHERE department = 'IT';
```

### Output when MySQL uses the index

| id | select_type | table     | type | possible_keys  | key            | rows | Extra |
| -: | ----------- | --------- | ---- | -------------- | -------------- | ---: | ----- |
|  1 | SIMPLE      | Employees | ref  | idx_department | idx_department |    4 | NULL  |

### Explanation

* `possible_keys = idx_department` → MySQL can use this index.
* `key = idx_department` → MySQL selected this index.
* `type = ref` → MySQL is using the index to find matching rows.
* `rows = 4` → Approximately 4 matching rows need to be checked.

---

## Simple Comparison

| Without Index            | With Index              |
| ------------------------ | ----------------------- |
| MySQL may check all rows | MySQL can use the index |
| `type = ALL`             | `type = ref`            |
| `key = NULL`             | `key = idx_department`  |
| Full Table Scan          | Index-based search      |

> **Note:** MySQL does not always use an index. The optimizer decides whether using the index is efficient. For a very small table, MySQL may still choose a Full Table Scan.
