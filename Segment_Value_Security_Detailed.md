# Segment Value Security

## **What Is It?**

Segment value security controls user access to specific values in the Chart of Accounts segments. It restricts which account values users can see and use in transactions, reporting, and accounting.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


## **Key Concepts**

### **1. Chart of Accounts Structure**
- Made up of segments (e.g., Company, Department, Account, Cost Center)
- Each segment has a value set containing allowed values
- Example: Account segment might have values like 1000, 2000, 3000

### **2. Security Control**
Instead of giving users access to ALL account values, you can restrict them to specific values:
- User A can only use accounts 1000-1999
- User B can only use accounts 2000-2999
- User C can see all accounts but only modify certain ones

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


## **How It Works**

### **Three Main Components:**

1. Secured Value Sets
- Enable security on specific chart of accounts segments
- Mark which segments need access control

2. Security Rules (Policies)
- Define WHICH account values users can access
- Use operators to specify values

3. Rule Assignments
- Assign rules to specific users
- Specify business function, security context, and access level

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


## **Security Rule Operators**

| Operator | What It Does | Example |
|----------|--------------|---------|
| Equal To | Access to exact value | Account = 1000 |
| Not Equal To | Access to all EXCEPT this value | Account ≠ 9999 |
| Between | Access to range of values | Accounts 1000-1999 |
| Starts With | Access to values starting with | Accounts starting with "1" |
| Ends With | Access to values ending with | Accounts ending with "00" |
| Contains | Access to values containing | Accounts containing "50" |
| Is Descendant Of | Access to parent + all children in hierarchy | Department 100 and all sub-departments |
| Is Last Descendant Of | Access to parent + leaf nodes only | Department 100 and lowest-level departments |

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


## **Access Levels**

Read-Write Access: Users can:
- Create and update transactions
- Enter account values
- View accounting
- Run reports

Read-Only Access: Users can:
- View transactions
- Query data
- Run reports
- **Cannot** create or modify transactions with those accounts

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


## **Business Function Enforcement**

You can apply segment value security by business function:

| Business Function | Security Context | Example |
|-------------------|------------------|---------|
| General Ledger | Data Access Set | User can use account 1000 only in Vision Corp ledger |
| Payables | Business Unit | User can use account 2000 only in US Business Unit |
| Receivables | Business Unit | User can use account 3000 only in EMEA Business Unit |
| Assets | Asset Book | User can use account 4000 only in Corporate Asset Book |

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


## **Setup Process**

### **Step 1: Select Business Functions**
Choose which modules enforce segment value security:
- General Ledger
- Payables
- Receivables
- Assets

### **Step 2: Enable Security on Value Set**
Mark specific chart of accounts segments as "secured"

### **Step 3: Deploy Accounting Flexfield**
Publish the configuration

### **Step 4: Create Security Rules**
Use Manage Segment Value Security Rules spreadsheet:

Rules Worksheet - Define policies:
- Policy Name
- Segment Value Security Role
- Operator (Starts With, Between, etc.)
- From/To Values

Rule Assignments Worksheet - Assign to users:
- User Name
- Policy Name
- Business Function
- Security Context
- Security Context Value
- Access Level (Read-Write or Read-Only)
- Start/End Dates

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


## **Real-World Example**

Scenario: User KUMAR works with Fixed Assets

Setup:
- Asset Book: HR CONSULTING CORP
- Read-Write access to accounts: 3111, 3888
- Read-Only access to accounts: 3121, 3999

Result:
- KUMAR can add assets using accounts 3111 and 3888
- KUMAR can view assets with accounts 3121 and 3999
- KUMAR cannot add assets using accounts 3121 and 3999
- KUMAR cannot see any assets with other account values

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


## **Default Behavior**

Important: If NO rules are assigned to a user, they have access to ALL account values in the secured value set.

You only need to create rules for users who need restricted access.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


## **Best Practices**

1. Create dedicated security roles - Don't use existing job roles (like Accounts Payable Manager) for segment value security
2. Share rules - Multiple users with same access needs can share one rule
3. Use hierarchies - Leverage "Is Descendant Of" for easier maintenance
4. Test access - Verify users can access what they need before going live
5. Document policies - Keep clear records of who has access to what and why

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


## **Where It's Enforced**

✅ Enforced in:
- Transaction entry (invoices, journals, receipts)
- Account value selection
- Viewing accounting distributions
- Running reports
- Web services (Create, Update, Delete)

❌ NOT enforced in:
- Setup tasks
- Certain system processes
- Transaction Account Builder (Assets)
