# Data Security by Business Function

## **What Is It?**

Data security by business function controls what financial data users can access and modify based on the specific module (business function) they're working in. It ensures users only see and work with data relevant to their responsibilities within General Ledger, Payables, Receivables, Assets, and other financial modules.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


## **Core Concept**

Data security is applied through **Security Contexts** that are specific to each business function:

| Business Function | Security Context | Controls Access To |
|-------------------|------------------|-------------------|
| General Ledger | Data Access Set | Ledgers, Ledger Sets, Primary Balancing Segment Values |
| Payables | Business Unit | AP Business Units |
| Receivables | Business Unit | AR Business Units |
| Assets | Asset Book | Asset Books |
| Subledger Accounting | Ledger | Ledgers (via Data Access Set) |
| Intercompany | Intercompany Organization | Intercompany Organizations |

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


## **1. General Ledger - Data Access Sets**

### **What Are Data Access Sets?**

Data access sets are the fundamental data security control for General Ledger. They provide users with access to one or more ledgers and are ALWAYS required for GL access.

### **Components of Data Access Sets**

**Access Set Type:**
- **Full Ledger**: Access to entire ledger(s) or ledger set(s)
- **Primary Balancing Segment Value**: Access to specific primary balancing segment values within a ledger

**Access Level:**
- **Read-Only**: View journals, balances, and reports only
- **Read and Write**: Create journals, update balances, view data

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Full Ledger Access Set Type**

Provides access to entire ledger or ledger set.

**Characteristics:**
- Can include one or more ledgers
- Can include ledger sets (grants access to all ledgers in the set)
- Automatically created when ledger/ledger set is created (implicit data access set)
- Can manually create explicit data access sets

**Example:**
```
Data Access Set: US Operations
Type: Full Ledger
Ledgers:
  - US Primary Ledger (Read and Write)
  - US Reporting Ledger (Read Only)
  - US Stat Ledger (Read Only)
```

User with this data access set can:
- Create and post journals in US Primary Ledger
- View journals and balances in all three ledgers
- Run reports across all three ledgers
- Cannot modify US Reporting or Stat Ledgers

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Primary Balancing Segment Value Access Set Type**

Provides access to specific primary balancing segment values within a ledger.

**Use Cases:**
- Restrict access to specific legal entities
- Limit access to specific companies
- Control access by division or region

**Value Selection:**
- **Single Value**: Access to one specific value
- **Parent Value**: Access to parent and all descendants in hierarchy

**Example:**
```
Data Access Set: US Financial Services
Type: Primary Balancing Segment Value
Ledger: US Financial Services Ledger

Primary Balancing Segment Values:
  - 101 (Banks) - Read and Write
  - 102 (Capital) - Read and Write
  - 131 (Insurance) - Read Only
```

User with this data access set can:
- Create journals for companies 101 and 102
- View journals and balances for companies 101, 102, and 131
- Cannot access any other company values in the ledger
- Cannot create journals for company 131

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Combining Data Access Sets with Segment Value Security**

**CAUTION**: Not recommended to use both methods for primary balancing segment.

If you use both:
- Data access set restricts ledger and primary balancing segment access
- Segment value security further restricts account value access
- Creates complexity and potential conflicts

**Recommended Best Practice:**
- Use data access sets for ledger and primary balancing segment control
- Use segment value security for other segments (Department, Account, Cost Center)
- Don't apply dual controls on the same segment

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Setup Process for Data Access Sets**

**Task**: Manage Data Access Set Data Access for Users

**Navigation**: Setup and Maintenance > Search: "Manage Data Access Set"

**Steps:**
1. Select user
2. Select data access set
3. Assign to user
4. Set effective dates

**Automatic Creation:**
- When ledger is created → Implicit data access set created automatically
- Provides full read and write access to that ledger
- Non-updatable

**Manual Creation:**
- Create explicit data access sets for custom access patterns
- Combine multiple ledgers
- Specify primary balancing segment values
- Set different access levels

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Example: Data Access Set with Legal Entity Security**

**Scenario**: Secure access by legal entity using primary balancing segment values.

**Setup:**
```
Ledger: Vision Corporation Global
Chart of Accounts: Company segment = Primary Balancing Segment
Legal Entities mapped to Company values:
  - Company 3111 = Legal Entity A
  - Company 3121 = Legal Entity B
  - Company 4888 = Legal Entity C

Data Access Set: Legal Entity A Access
Type: Primary Balancing Segment Value
Ledger: Vision Corporation Global
Values:
  - 3111 (Read and Write)
```

**Result:**
User assigned this data access set can:
- Create and post journals for company 3111 only
- View balances for company 3111 only
- Run reports filtered to company 3111
- Cannot see or access companies 3121 or 4888

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


## **2. Payables - Business Unit Security**

### **What Is Business Unit Security?**

Controls which AP business units users can access for payables transactions.

### **Security Context: Business Unit**

Users must be granted access to specific business units to:
- Create and manage invoices
- Process payments
- View supplier information
- Run payables reports

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **How It Works**

**Task**: Manage Data Access for Users

**Navigation**: Setup and Maintenance > Search: "Manage Data Access for Users"

**Assignment Process:**
1. Select user
2. Select security context type: Business Unit
3. Select business function: Payables
4. Select specific business units
5. Set access level (Read-Write or Read-Only)

**Example:**
```
User: AP Clerk
Role: Accounts Payable Specialist
Business Unit Access:
  - US East BU (Read-Write)
  - US West BU (Read-Write)
  - Canada BU (Read-Only)
```

User can:
- Create invoices in US East and US West BUs
- Process payments in US East and US West BUs
- View invoices in Canada BU
- Cannot create invoices in Canada BU
- Cannot access any other business units

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Combining with Segment Value Security**

You can further restrict access within business units using segment value security.

**Example:**
```
User: AP Clerk
Business Unit: US East BU (Read-Write)
Segment Value Security:
  - Business Function: Payables
  - Security Context: Business Unit
  - Security Context Value: US East BU
  - Account Values: 2000-2999 (Liability accounts only)
```

User can:
- Create invoices in US East BU
- Only use liability accounts (2000-2999)
- Cannot use expense accounts or other account ranges

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


## **3. Receivables - Business Unit Security**

### **What Is Business Unit Security?**

Controls which AR business units users can access for receivables transactions.

### **Security Context: Business Unit**

Users must be granted access to specific business units to:
- Create and manage invoices
- Process receipts
- Apply credit memos
- Run receivables reports

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **How It Works**

**Task**: Manage Data Access for Users

**Assignment Process:**
1. Select user
2. Select security context type: Business Unit
3. Select business function: Receivables
4. Select specific business units
5. Set access level (Read-Write or Read-Only)

**Example:**
```
User: AR Specialist
Role: Accounts Receivable Specialist
Business Unit Access:
  - EMEA BU (Read-Write)
  - APAC BU (Read-Write)
```

User can:
- Create customer invoices in EMEA and APAC BUs
- Process receipts in EMEA and APAC BUs
- Apply credit memos in EMEA and APAC BUs
- View accounting for these business units
- Cannot access Americas BUs

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Access Levels in Receivables**

**Read-Write Access** allows:
- Create, save, and complete transactions
- Credit transactions
- Update account values in distributions
- Post transactions to General Ledger
- Apply and unapply receipts
- Manage adjustments
- Create draft subledger accounting
- Use web services (Get, Create, Update, Delete, Reverse)

**Read-Only Access** allows:
- Create and save transactions (but not complete)
- View transaction distributions
- Run reports

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Segment Value Security in Receivables**

**Global Access:**
- All business functions
- All security contexts
- All security context values
- Use for users working across multiple modules (AR, GL, FA)

**Receivables Business Function Only:**
- Receivables business function
- Business unit security context
- All business units
- Use for AR users needing same account access across all BUs

**Specific Business Unit:**
- Receivables business function
- Business unit security context
- Specific business unit name
- Use for AR users restricted to one business unit

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


## **4. Assets - Asset Book Security**

### **What Is Asset Book Security?**

Controls which asset books users can access for fixed asset transactions.

### **Security Context: Asset Book**

Users must be granted access to specific asset books to:
- Add assets
- Change asset details
- Retire assets
- Track asset information
- Run asset reports

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Data Privileges for Asset Books**

Access is controlled by specific data privileges:

| Data Privilege | What It Allows |
|----------------|----------------|
| Add Fixed Asset Data | Create new assets |
| Change Fixed Asset Data | Modify existing assets |
| Retire Fixed Asset Data | Retire assets |
| Track Fixed Asset Data | View asset information |
| Submit Fixed Assets Reports | Run asset reports |

**Example:**
```
User: Asset Accountant
Asset Book: Corporate Asset Book
Privileges:
  - Add Fixed Asset Data
  - Change Fixed Asset Data
  - Track Fixed Asset Data
  - Submit Fixed Assets Reports

Asset Book: Leased Assets Book
Privileges:
  - Track Fixed Asset Data
  - Submit Fixed Assets Reports
```

User can:
- Add and modify assets in Corporate Asset Book
- Only view assets in Leased Assets Book
- Cannot retire assets in either book
- Run reports for both books

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Setup Process**

**Step 1**: Assign job role using Security Console
- Example: Asset Accountant role

**Step 2**: Grant asset book access using Manage Data Access for Users
- Select user
- Select security context: Asset Book
- Select specific asset books
- Select data privileges

**Step 3**: Set default asset book (optional)
- Use Default Book profile option
- Set at site, product, or user level
- Automatically populates in transactions
- User can override if needed

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Combining with Segment Value Security**

**Example:**
```
User: KUMAR
Asset Book: HR CONSULTING CORP
Segment Value Security:
  - Business Function: Assets
  - Security Context: Asset Book
  - Security Context Value: HR CONSULTING CORP
  - Account Values: 3111, 3888 (Read-Write)
  - Account Values: 3121, 3999 (Read-Only)
```

**Asset Additions:**
- KUMAR can add assets using accounts 3111 and 3888
- KUMAR can view assets with accounts 3121 and 3999
- KUMAR cannot add assets using accounts 3121 and 3999

**Edit Source Lines:**
- KUMAR can edit Depreciation Expense Account using 3111 and 3888
- KUMAR cannot edit accounts 3121 and 3999

**Asset Transfers:**
- KUMAR can transfer assets referencing accounts 3111 and 3888
- KUMAR cannot transfer assets referencing other accounts

**Viewing Accounting:**
- KUMAR can view accounting lines for all granted accounts (both Read-Write and Read-Only)

**Reports:**
- KUMAR can run reports showing all granted accounts

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Where Segment Value Security Is NOT Enforced in Assets**

❌ **Transaction Account Builder**
- Used to drive depreciation expense account for mass addition lines
- Defaults accounts based on organizational rules
- Not subject to user's secured account grants

❌ **Setup Tasks**
- Implementation tasks in Functional Setup Manager
- Setup activities don't enforce data security

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


## **5. Subledger Accounting - Data Security**

### **What Is Subledger Accounting Security?**

Subledger Accounting is an intermediate processing layer that converts transaction information from subledgers into accounting entries. Data security is governed by the job role and associated business function.

### **How Data Security Works**

**No Specific Security Context:**
- Subledger Accounting doesn't have its own business function
- Security is inherited from the source subledger or General Ledger
- Cumulative effect of all data access grants applies

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Data Security by Job Role**

| Job Role Type | Default Data Security |
|---------------|---------------------|
| **General Ledger Job Roles** (General Accounting Manager, Financial Specialist) | For ledgers user has access to: <br>• Review/create subledger accounting for ALL subledgers <br>• Account transactions, transfer to GL, drill down for ALL subledgers <br>• Inquiry and reporting for ALL subledgers |
| **Subledger Job Roles** (Payables Supervisor, Receivables Specialist, Asset Accountant) | For specific security context (BU, Asset Book) user has access to: <br>• Review/create subledger accounting for THAT subledger only <br>• Account transactions, transfer to GL, drill down for THAT subledger <br>• Inquiry and reporting for THAT subledger |

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Segment Value Security in Subledger Accounting**

**When Viewing from Subledger Accounting Pages:**
- General Ledger business function context is applied
- Cumulative effect of all Data Access Set grants applies
- No specific Data Access Set context selection

**When Viewing from Transaction (View Accounting):**
- Business function of the source subledger applies
- Example: Viewing accounting from AP invoice → Payables business function applies

**When Segment Value Security Defined for "All Business Functions":**
- Access to subledger accounting entries is controlled by cumulative grants
- All data access contexts are considered together

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Example Scenario**

```
User: Accounts Payable Supervisor
Job Role: Accounts Payable Supervisor
Business Unit Access: US East BU
Ledger Access: US Primary Ledger (via Data Access Set)

Capabilities:
1. Create AP invoices in US East BU
2. View subledger accounting for AP invoices in US East BU
3. Transfer AP accounting to General Ledger
4. Drill down from GL to AP transaction
5. Run AP subledger accounting reports
6. Cannot view AR or FA subledger accounting
```

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


## **6. Oracle Transactional Business Intelligence (OTBI) Reporting**

### **How OTBI Security Works**

OTBI reporting has unique security considerations because:
- Reports can cross multiple business functions
- User doesn't directly select data security context
- Cumulative data access assignments apply simultaneously

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Segment Value Security in OTBI**

**Key Differences from Transactional Security:**
- Enforcement by business function is NOT supported
- Once a chart of accounts value set is secured, security is enforced across ALL business functions
- Applies to GL, AP, AR, FA, Intercompany, and Subledger Accounting

**For General Ledger Subject Area:**
- User's currently selected data access set determines applicable security
- Stored in profile option
- Applied when reporting on ledgers with secured chart of accounts

**For Non-GL Subject Areas:**
- User's cumulative assigned data access sets apply simultaneously
- No specific data security context selection

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Reporting Roles**

**Business Intelligence Consumer Role:**
- View reports only
- Cannot create new reports
- Inherited by all self-service reporting duties

**Business Intelligence Author Role:**
- Create new reports from subject areas
- Inherited by job roles that need authoring capability

**Transaction Analysis Duty Roles:**
- Grant access to specific subject areas
- Must be assigned along with Financials duty roles

**Example:**
```
Job Role: Accounts Payable Manager
Inherits:
  - Payables Balance Analysis (Financials role)
  - Payables Invoice Transaction Analysis Duty (OBI role)
  - BI Consumer Role
```

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Custom Job Roles for OTBI**

If you create custom job role with OTBI access, you MUST assign BOTH:
1. **OBI version** of Transaction Analysis Duty role
2. **Financials version** of Transaction Analysis Duty role

**Example:**
```
Custom Role: Custom Fixed Asset Analyst
Must Inherit:
  - Fixed Asset Transaction Analysis Duty (OBI version)
  - Fixed Asset Transaction Analysis (Financials version)
```

This ensures:
- Function security for running reports
- Data security for accessing financial data
- Access to BI functionality

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


## **7. Features Without Data Security Context**

### **What Are They?**

Some features work with financial data but can't establish a specific data security context.

**Examples:**
- Standard Subledger Accounting Publisher reports (can involve multiple ledgers)
- Non-GL OTBI reports (no specific security context selection)
- Cross-module reports

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **How Security Is Applied**

**Modified Enforcement:**
- Percentage value (%) substituted for certain rule assignment attributes
- Indicates no specific value needs to be matched
- Broader basis of rule assignment matching
- Still limits access to granted secured accounts
- Applied on non-specific basis

**Result:**
- User's access to secured accounts is still restricted
- But not tied to specific security context value
- Cumulative grants apply

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


## **Complete Security Setup Examples**

### **Example 1: Multi-Module Finance Manager**

**User**: Regional Finance Manager
**Responsibilities**: GL, AP, AR for EMEA region

**Setup:**

**Job Roles:**
- General Accounting Manager
- Accounts Payable Manager
- Accounts Receivable Manager

**Data Access:**

General Ledger:
```
Data Access Set: EMEA Operations
Type: Full Ledger
Ledgers:
  - EMEA Primary Ledger (Read-Write)
  - EMEA Reporting Ledger (Read-Only)
```

Payables:
```
Security Context: Business Unit
Business Units:
  - EMEA North BU (Read-Write)
  - EMEA South BU (Read-Write)
```

Receivables:
```
Security Context: Business Unit
Business Units:
  - EMEA North BU (Read-Write)
  - EMEA South BU (Read-Write)
```

**Segment Value Security:**
```
Business Function: All business functions
Security Context: All security contexts
Account Values: Companies 300-399 (EMEA companies)
Access Level: Read-Write
```

**Result:**
User can:
- Create journals in EMEA ledgers for companies 300-399
- Process AP invoices in EMEA BUs for companies 300-399
- Process AR invoices in EMEA BUs for companies 300-399
- View accounting across all EMEA transactions
- Run reports for EMEA region
- Cannot access other regions

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Example 2: Specialized AP Clerk**

**User**: AP Invoice Processor
**Responsibilities**: Invoice entry only for specific business unit

**Setup:**

**Job Roles:**
- Accounts Payable Specialist

**Data Access:**

Payables:
```
Security Context: Business Unit
Business Units:
  - US East BU (Read-Write)
```

General Ledger (for viewing accounting):
```
Data Access Set: US Primary Ledger Access
Type: Full Ledger
Ledgers:
  - US Primary Ledger (Read-Only)
```

**Segment Value Security:**
```
Business Function: Payables
Security Context: Business Unit
Security Context Value: US East BU
Account Values: 2000-2999 (Liability accounts)
Access Level: Read-Write
```

**Result:**
User can:
- Create invoices in US East BU only
- Use liability accounts (2000-2999) only
- View accounting in US Primary Ledger
- Cannot process payments
- Cannot access other business units
- Cannot use other account ranges

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Example 3: Read-Only Financial Analyst**

**User**: Financial Analyst
**Responsibilities**: View and report across all modules

**Setup:**

**Job Roles:**
- Financial Analyst

**Data Access:**

General Ledger:
```
Data Access Set: All Ledgers
Type: Full Ledger
Ledgers:
  - All ledgers (Read-Only)
```

Payables:
```
Security Context: Business Unit
Business Units:
  - All business units (Read-Only)
```

Receivables:
```
Security Context: Business Unit
Business Units:
  - All business units (Read-Only)
```

Assets:
```
Security Context: Asset Book
Asset Books:
  - All asset books
Privileges:
  - Track Fixed Asset Data
  - Submit Fixed Assets Reports
```

**Reporting Roles:**
- BI Consumer Role
- All Transaction Analysis Duty roles

**Result:**
User can:
- View all financial data across all modules
- Run reports and analytics
- Query transactions and balances
- Cannot create or modify any transactions
- Cannot post or approve

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


## **Summary Table: Security Context by Business Function**

| Business Function | Security Context | Assignment Task | Access Levels | Segment Value Security Supported |
|-------------------|-----------------|-----------------|---------------|----------------------------------|
| General Ledger | Data Access Set | Manage Data Access Set Data Access for Users | Read-Only, Read-Write | Yes (by Data Access Set) |
| Payables | Business Unit | Manage Data Access for Users | Read-Only, Read-Write | Yes (by Business Unit) |
| Receivables | Business Unit | Manage Data Access for Users | Read-Only, Read-Write | Yes (by Business Unit) |
| Assets | Asset Book | Manage Data Access for Users | Data Privileges | Yes (by Asset Book) |
| Subledger Accounting | Ledger (indirect) | Via GL Data Access Set | Inherited from GL | Yes (cumulative) |
| Intercompany | Intercompany Organization | Manage Data Access for Users | Read-Only, Read-Write | Yes (by IC Org) |

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


## **Best Practices**

### **1. Data Access Set Management**
- Create explicit data access sets for common access patterns
- Use Full Ledger type for simple ledger access
- Use Primary Balancing Segment Value type for legal entity security
- Don't combine with segment value security on same segment

### **2. Business Unit Security**
- Grant access only to necessary business units
- Use Read-Only for inquiry users
- Combine with segment value security for finer control
- Document business unit assignments

### **3. Asset Book Security**
- Use granular data privileges (Add, Change, Retire, Track, Report)
- Set default asset book for users with single book access
- Restrict retirement privileges to authorized users
- Combine with segment value security for account control

### **4. Cross-Module Access**
- For users working across modules, grant access in each module's security context
- Use "All business functions" for segment value security when appropriate
- Ensure consistent access levels across modules
- Test cross-module workflows

### **5. Reporting Security**
- Assign both OBI and Financials duty roles for custom roles
- Use BI Consumer Role for view-only report access
- Use BI Author Role for report creation capability
- Understand cumulative security in OTBI

### **6. Subledger Accounting**
- GL roles get access to all subledger accounting
- Subledger roles get access to their specific subledger only
- No specific security context selection
- Cumulative grants apply

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


## **Troubleshooting Data Access Issues**

### **Issue: User can't see ledger**

Check:
1. Data access set assigned to user?
2. Ledger included in data access set?
3. Access level appropriate (Read-Only vs Read-Write)?
4. Effective dates valid?

### **Issue: User can't access business unit**

Check:
1. Business unit access granted in Manage Data Access for Users?
2. Correct business function selected (Payables vs Receivables)?
3. Access level appropriate?
4. Business unit active and valid?

### **Issue: User can't see asset book**

Check:
1. Asset book access granted?
2. Required data privileges assigned?
3. Default book profile option set (if applicable)?
4. Asset book assigned to correct ledger?

### **Issue: User can't see specific account values**

Check:
1. Segment value security rules assigned?
2. Business function matches usage context?
3. Security context matches (Data Access Set, Business Unit, Asset Book)?
4. Security context value matches?
5. Access level appropriate?

### **Issue: OTBI report shows no data**

Check:
1. Transaction Analysis Duty roles assigned?
2. BI Consumer Role assigned?
3. Data access granted for underlying security contexts?
4. Segment value security not blocking all data?
5. Currently selected data access set (for GL reports)?

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


## **Key Takeaways**

1. **Each business function has its own security context**: GL uses Data Access Sets, AP/AR use Business Units, FA uses Asset Books

2. **Data Access Sets are required for General Ledger**: No GL access without data access set assignment

3. **Two types of data access sets**: Full Ledger (entire ledger) and Primary Balancing Segment Value (specific values)

4. **Access levels matter**: Read-Only vs Read-Write determines what users can do

5. **Segment value security can be combined** with business function security for granular control

6. **OTBI reporting has unique security**: Enforcement across all business functions, cumulative grants apply

7. **Subledger Accounting inherits security**: From source subledger or General Ledger, no specific context

8. **Custom OTBI roles need both duty roles**: OBI version and Financials version

9. **Setup tasks don't enforce data security**: Only transactional activities are secured

10. **Test thoroughly**: Verify users can access what they need before go-live
