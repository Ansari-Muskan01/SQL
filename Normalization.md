# Normalization 

Normalization is a database design process used to organize data into multiple related tables to reduce duplicate data and avoid data-related problems.

Normalization = Organizing data properly by splitting a large table into smaller related tables.

| Customer_ID | Customer_Name | Branch  | Branch_Manager | City   |
| ----------- | ------------- | ------- | -------------- | ------ |
| C001        | Aarav         | Andheri | Rahul          | Mumbai |
| C002        | Priya         | Andheri | Rahul          | Mumbai |
| C003        | Rohan         | Bandra  | Neha           | Mumbai |
| C004        | Anaya         | Andheri | Rahul          | Mumbai |

Here, Andheri, Rahul, Mumbai are repeated for every customer belonging to that branch. This creates duplicate data.

If the branch manager changes from Rahul to Amit, we have to update multiple rows. If we miss one row, the database will contain incorrect information.

# After Normalization

Customers

| Customer_ID | Customer_Name | Branch_ID |
| ----------- | ------------- | --------- |
| C001        | Aarav         | 1         |
| C002        | Priya         | 1         |
| C003        | Rohan         | 2         |
| C004        | Anaya         | 1         |


Branches

| Branch_ID | Branch_Name | Branch_Manager | City   |
| --------- | ----------- | -------------- | ------ |
| 1         | Andheri     | Rahul          | Mumbai |
| 2         | Bandra      | Neha           | Mumbai |

Now the branch information is stored only once. Branch_ID connects the two tables.


# Normal Forms

- Normalization is commonly explained using Normal Forms:<br>
1. 1NF – First Normal Form <br>
2. 2NF – Second Normal Form <br>
3. 3NF – Third Normal Form <br>


# 1NF – First Normal Form

- A table is in 1NF when:<br>
- Each column contains atomic/single values<br>
- There are no multiple values in one cell<br>
- There are no repeating groups<br>
