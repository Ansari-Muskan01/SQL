
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





## SmartBank SQL Project – Business Analysis Questions

- SmartBank wants to identify all customers whose current banking relationship is active. Display their complete customer details.

- Customer & Basic Analysis<Br>
1. SmartBank wants to maintain a customer directory. Display complete details of all registered customers.<br>
2. Management wants to know the different cities from which SmartBank customers are coming. Display the unique customer cities.<br>
3. Identify all customers whose current status is Active.<br>
4. Find active customers who are currently registered in Mumbai.<br>
5. Find customers who are registered in either Mumbai or Pune.<br>
6. Identify customers who are registered in cities other than Mumbai.<br>
7. Find customers whose age falls between 30 and 50 years for customer demographic analysis.<br>
8. Identify customers belonging to Mumbai, Pune, Nashik, or Nagpur.<br>
9. Find customers whose names begin with the letter A.<br>
10. Identify customers whose email address is not available in the bank records.<br>
11. Identify customers who have a registered email address.<br>
12. Display customer accounts from highest to lowest balance to identify high-value accounts.<br>
13. Identify the top 5 accounts with the highest balance for priority customer analysis.<br>

- Customer Profile & Segmentation
1. Identify customers who are between 25 and 40 years old and have an Active status.<br>
2. Find customers whose names contain the letter a for customer name analysis.<br>
3. Display customers from Mumbai who are above 30 years of age.<br>
4. Identify customers whose age is outside the range of 25 to 50 years.<br>
5. Display customers whose city starts with the letter M.<br>
6. Find customers whose email addresses belong to the Gmail domain.<br>

- Account Monitoring & Balance Analysis
1. Display all accounts with their account type, balance, and current status.<br>
2. Identify accounts that are currently Active and have a balance greater than ₹25,000.<br>
3 Find accounts with a balance between ₹20,000 and ₹1,00,000.<br>
4. Identify accounts belonging to customers whose account status is not Active.<br>
5. Display the account with the lowest balance.<br>
6. Calculate the total balance maintained across all customer accounts.<br>
7. Calculate the average balance of all accounts.<br>

- Branch Performance Analysis
1. Display all branches along with their city and state details.<br>
2. Identify branches located in Maharashtra.<br>
3. Find the number of branches operating in each city.<br>
4. Calculate the total number of accounts maintained at each branch.<br>
5. Identify branches having more than 3 customer accounts.<br>
6. Find the branch with the highest number of customers.<br>

- Transaction Activity Analysis
1. Display all transactions along with account details and transaction dates.<br>
2. Identify customers who have performed a Deposit transaction.<br>
3. Find customers who have performed both Deposit and Withdrawal transactions.<br>
4. Identify transactions where the amount is greater than ₹50,000.<br>
5. Calculate the total transaction amount for each transaction type.<br>
6. Find the average transaction amount for each transaction type.<br>
7. Identify the account with the highest total transaction amount.<br>

- Loan Portfolio Analysis
1. Display all Home Loans along with customer names and loan amounts.
2. Identify customers having loans with an amount greater than ₹10,00,000.
3. Find loans with an interest rate greater than 10%.
4. Calculate the total loan amount for each loan type.
5. Calculate the average loan amount for each loan type.
6. Identify the loan type with the highest total loan amount.
7. Find branches where the total loan amount exceeds ₹50,00,000.

- Customer Financial Behavior
1. Identify customers whose account balance is greater than their total loan amount.
2. Identify customers whose total loan amount is greater than their account balance.
3. Find customers who have both an Active account and an Active loan.
4. Identify customers who have multiple accounts.
5. Identify customers who have performed more than 3 transactions.
6. Find customers who have both performed transactions and taken a loan

- Customer & Banking Relationship Analysis
1. Display each customer's name along with the branch where their banking relationship is maintained.<br>
2. Identify all registered customers and display their account details, including customers who have not opened an account yet.<br>
3. Generate a consolidated banking view showing customer name, branch name, account type, account balance, and loan type.<br>
4. Identify branches operating in the same city for branch network analysis.<br>

- Customer & Financial Product Analysis
1. Identify customers who are using both deposit/account and loan services.<br>
2. Identify customers who have an account but have not taken any loan.<br>
3. Identify customers who have a loan but do not currently have an account.<br>
4. Identify the branch with the highest total account balance.<br>
5. Identify the branch with the highest total loan portfolio.<br>
6. Identify customers who have performed at least one Withdrawal transaction.<br>
7. Identify customers who have taken a Home Loan from SmartBank.<br>

- Customer & Financial Risk Classification
1. CASE – Classify customers into Young, Middle-Aged, and Senior categories based on age.
2. CASE – Classify accounts into Low, Medium, and High Balance categories.
3. CASE – Classify transactions into Small, Medium, and Large transactions based on amount.
4. CASE – Classify loans based on their current status as Active, Closed, or Pending.
5. CASE + GROUP BY – Find the number of customers in each age category for demographic analysis.


## PROJECT CONCLUSION

SmartBank SQL analysis provides a complete view of the bank's customers, accounts, branches, transactions, and loans.

The analysis helps SmartBank understand customer demographics,monitor account balances, evaluate branch performance,track transaction activities, and analyze the loan portfolio.

Customer and financial behavior analysis helps the bank identify high-value customers, active banking relationships,multiple-account holders, and customers using different financial products.

CASE-based classification further helps SmartBank segment customers, accounts, transactions, and loans for better analysis.

Overall, this SQL project demonstrates how banking data can be organized, analyzed, and transformed into meaningful business insights for better decision-making.


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
