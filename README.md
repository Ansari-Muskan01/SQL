
## SmartBank – Banking Management System 

Scenario:

SmartBank is a growing banking company that provides financial services to customers across different cities in Maharashtra.
The bank has several branches, and each branch is managed by a branch manager.

The bank wants to develop a Banking Management System to store and manage its daily banking activities in a structured database.

The system will maintain information about customers, branches, accounts, transactions, and loans.

### 1. Customers

The bank stores personal information about every customer, such as their name, email, phone number, city, age, gender, registration date, and customer status.
A customer is registered with a particular branch and can have one or more bank accounts.

### 2. Branches

SmartBank operates through multiple branches in cities such as Mumbai, Pune, Thane, Navi Mumbai, Nashik, and Nagpur.
For each branch, the bank stores the branch name, city, state, branch manager, contact number, IFSC code, and opening date.
A branch can have many customers and many accounts.

### 3. Accounts

Customers can open different types of accounts, such as:
- Savings Account
- Current Account
- Salary Account

Each account is linked to a customer and a branch. The system stores the account balance, account type, account status, and account opening date.
A customer can have multiple accounts.

### 4. Transactions

Customers perform different banking transactions through their accounts.
The system records transactions such as:
- Deposit
- Withdrawal
- Transfer
- Payment

For every transaction, the bank stores the transaction amount, date, type, and description.
One account can have many transactions.

### 5. Loans

SmartBank also provides different types of loans to eligible customers, such as:
- Home Loan
- Personal Loan
- Car Loan
- Education Loan
- Business Loan

For each loan, the system stores the loan amount, interest rate, loan term, loan status, and start date.
A customer can have one or more loans, and each loan is associated with a particular branch.








# SQL

# 🏦 BankingDB Project

```text
BANKINGDB PROJECT
       │
       ▼
   SQL DATABASE
       │
       ├── Customers
       ├── Branches
       ├── Accounts
       ├── Transactions
       └── Loans
       │
       ▼
   SQL ANALYSIS
       │
       ├── SELECT
       ├── WHERE
       ├── GROUP BY
       ├── HAVING
       ├── JOIN
       ├── SUBQUERY
       └── VIEWS
       │
       ▼
   POWER BI
       │
       ├── Data Connection
       ├── Data Cleaning
       ├── Data Modeling
       ├── Relationships
       ├── DAX
       ├── KPIs
       ├── Charts
       └── Interactive Dashboard
