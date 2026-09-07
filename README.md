
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





## -- SmartBank SQL Project – Business Analysis Questions

- SmartBank wants to identify all customers whose current banking relationship is active. Display their complete customer details.

- Customer & Basic Analysis
-1.  SmartBank wants to maintain a customer directory. Display complete details of all registered customers.
- Management wants to know the different cities from which SmartBank customers are coming. Display the unique customer cities.
-- Identify all customers whose current status is Active.
-- Find active customers who are currently registered in Mumbai.
-- Find customers registered in either Mumbai or Pune.
-- Identify customers who are registered in cities other than Mumbai.
-- Find customers whose age falls between 30 and 50 years for customer demographic analysis.
-- Identify customers belonging to Mumbai, Pune, Nashik, or Nagpur.
-- Find customers whose names begin with the letter A.
-- Identify customers whose email address is not available in the bank records.
-- Identify customers who have a registered email address.
-- Display customer accounts from highest to lowest balance to identify high-value accounts.
-- Identify the top 5 accounts with the highest balance for priority customer analysis.

-- Customer & Banking Relationship Analysis
-- Display each customer's name along with the branch where their banking relationship is maintained.
-- Identify all registered customers and display their account details, including customers who have not opened an account yet.
-- Generate a consolidated banking view showing customer name, branch name, account type, account balance, and loan type.
-- Identify branches operating in the same city for branch network analysis.

-- Customer & Financial Product Analysis
-- Identify customers who are using both deposit/account and loan services.
-- Identify customers who have an account but have not taken any loan.
-- Identify customers who have a loan but do not currently have an account.
-- Identify the branch with the highest total account balance.
-- Identify the branch with the highest total loan portfolio.
-- Identify customers who have performed at least one Withdrawal transaction.
-- Identify customers who have taken a Home Loan from SmartBank.
-- Identify customers maintaining an account balance above ₹50,000, along with their branch details.

-- Customer & Financial Risk Classification
-- CASE – Classify customers into Young, Middle-Aged, and Senior categories based on age.
-- CASE – Classify accounts into Low, Medium, and High Balance categories.
-- CASE – Classify transactions into Small, Medium, and Large transactions based on amount.
-- CASE – Classify loans based on their current status as Active, Closed, or Pending.
-- CASE + GROUP BY – Find the number of customers in each age category for demographic analysis.


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
