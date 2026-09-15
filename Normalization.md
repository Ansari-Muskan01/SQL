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


| Customer_ID | Customer_Name | Phone                  |
| ----------- | ------------- | ---------------------- |
| C001        | Aarav         | 9876543210, 9988776655 |
| C002        | Priya         | 9876543211             |

In 1NF

| Customer_ID | Customer_Name | Phone      |
| ----------- | ------------- | ---------- |
| C001        | Aarav         | 9876543210 |
| C001        | Aarav         | 9988776655 |
| C002        | Priya         | 9876543211 |

Each cell now contains one value.

# 2NF – Second Normal Form

It is already in 1NF and there is no partial dependency.

| Student_ID | Course_ID | Student_Name | Course_Name |
| ---------- | --------- | ------------ | ----------- |
| S01        | C01       | Aarav        | SQL         |
| S01        | C02       | Aarav        | Excel       |
| S02        | C01       | Priya        | SQL         |

Suppose the primary key is: (Student_ID, Course_ID)

But:
Student_Name depends only on Student_ID
Course_Name depends only on Course_ID

This is called partial dependency.

Students
| Student_ID | Student_Name |
| ---------- | ------------ |
| S01        | Aarav        |
| S02        | Priya        |

Courses
| Course_ID | Course_Name |
| --------- | ----------- |
| C01       | SQL         |
| C02       | Excel       |

Enrollments
| Student_ID | Course_ID |
| ---------- | --------- |
| S01        | C01       |
| S01        | C02       |
| S02        | C01       |

