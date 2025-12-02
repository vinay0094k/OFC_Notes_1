# General Ledger Setup

## **What Is General Ledger?**

General Ledger is the core financial module in Oracle Fusion Financials that maintains accounting records, processes journals, tracks balances, and produces financial reports. It's the central repository where all financial transactions from subledgers (Payables, Receivables, Assets, etc.) are recorded and consolidated.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


## **Key Components of General Ledger**

### **1. Chart of Accounts**
The structure that defines how you organize and record financial information.

### **2. Journals**
Transactions that record debits and credits to accounts.

### **3. Balances**
Cumulative totals maintained for each account combination.

### **4. Period Status**
Controls which accounting periods are open for transaction entry.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


## **1. Chart of Accounts**

### **What Is It?**

A chart of accounts is the structure that defines your account combinations. It consists of segments that, when combined, create unique accounts for recording transactions and organizing financial information.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Components of Chart of Accounts**

**Segments:**
- Individual components that make up an account
- Each segment has a value set defining allowed values
- Combined together to create account combinations

**Example Account Structure:**
```
Company - Department - Account - Cost Center - Product
  3111  -     00     -  11010  -     000     -  0000

Full Account: 3111-00-11010-000-0000
```

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Segment Labels**

Segment labels assign special functionality to specific segments:

| Segment Label | Purpose | Functionality |
|---------------|---------|---------------|
| **Primary Balancing Segment** | Ensures journals balance | All journals must balance for each primary balancing segment value. Typically represents Company or Legal Entity. |
| **Second Balancing Segment** | Additional balancing level | Optional second level of balancing (e.g., Division within Company). |
| **Third Balancing Segment** | Additional balancing level | Optional third level of balancing. |
| **Natural Account** | Account classification | Determines account type (Asset, Liability, Expense, Revenue, Equity). Used for financial statement reporting and year-end close. |
| **Cost Center** | Expense tracking | Groups natural accounts by functional cost types. Tracks business expenses across accounts. |

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Segment Details**

**Value Set:**
- Defines the set of values for a segment
- Controls formatting (length, data type)
- Provides validation rules

**Example:**
```
Segment: Company
Value Set: Company Values
Format: 4 digits numeric
Values: 1000, 2000, 3000, 3111, 3121, 4888
```

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Account Hierarchies**

Hierarchies organize segment values for reporting and security:

**Purpose:**
- Roll up detail values to summary levels
- Support financial reporting
- Enable security by parent value

**Example Natural Account Hierarchy:**
```
Total Assets (Parent)
├── Current Assets
│   ├── Cash (11010)
│   ├── Accounts Receivable (12000)
│   └── Bad Debt Reserve (12010)
└── Fixed Assets
    ├── Equipment (15000)
    └── Accumulated Depreciation (15100)
```

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Setup Process**

**Task:** Create Chart of Accounts, Ledger, Legal Entities, and Business Units in Spreadsheet

**Navigation:** Setup and Maintenance > Define Financials Configuration for Rapid Implementation

**Steps:**

1. **Download Rapid Implementation Workbook**
   - From Manage Chart of Accounts Configurations task
   - Or from implementation project

2. **Complete Worksheets:**
   - Chart of Accounts, Calendar, and Ledger
   - Natural Accounts
   - Additional segment sheets (auto-generated)
   - Business Units
   - Companies and Legal Entities

3. **Define Segments:**
   - Segment name
   - Segment label (if applicable)
   - Value set
   - Segment order

4. **Enter Segment Values:**
   - Define values for each segment
   - Create hierarchies
   - Set account types (for Natural Account)

5. **Validate Spreadsheet:**
   - Click "Step 1: Validate"
   - Review and fix errors
   - Preview sample financial report

6. **Generate Files:**
   - Step 2: Generate Chart of Accounts File (ChartOfAccounts.xml)
   - Step 3: Generate Ledger, LE, and BU File (FinancialsCommonEntities.xml)

7. **Upload Files:**
   - Upload Chart of Accounts file first
   - Upload Ledger, Legal Entities, and Business Units file second

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Important Considerations**

**CAUTION:** Once you begin using your chart of accounts, making changes to fundamental attributes is neither recommended nor supported:
- Chart of accounts segments
- Segment labels
- Segment characteristics
- Calendar structure or pattern

**Best Practices:**
- Plan your chart of accounts structure carefully before implementation
- Use standard segment labels (Primary Balancing, Natural Account, Cost Center)
- Create hierarchies for reporting and security
- Test with sample data before go-live
- Document your chart of accounts design

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Example Chart of Accounts**

**Structure:**
```
Segment 1: Company (Primary Balancing Segment)
Segment 2: Line of Business
Segment 3: Account (Natural Account)
Segment 4: Cost Center
Segment 5: Product
```

**Sample Account Combinations:**
```
3111-00-11010-000-0000  (Cash - Company 3111)
3111-00-12010-000-0000  (Bad Debt Reserve - Company 3111)
3111-00-21010-000-0000  (Accounts Payable - Company 3111)
3111-00-31001-000-0000  (Common Stock - Company 3111)
3111-00-40110-000-0000  (Revenue - Company 3111)
3111-00-52110-000-0000  (Cost of Goods Sold - Company 3111)
```

**Account Types (Natural Account):**
- 11010 = Asset (Cash)
- 12010 = Asset (Bad Debt Reserve)
- 21010 = Liability (Accounts Payable)
- 31001 = Equity (Common Stock)
- 40110 = Revenue (White Wine Revenue)
- 52110 = Expense (Cost of Goods Sold)

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


## **2. Journals**

### **What Are Journals?**

Journals are the transactions that record financial activity in General Ledger. They consist of journal lines with debits and credits that must balance.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Types of Journals**

| Journal Type | Source | Description |
|--------------|--------|-------------|
| **Manual Journals** | General Ledger | Created directly in GL by users for adjustments, accruals, reclassifications |
| **Subledger Journals** | Payables, Receivables, Assets, etc. | Automatically created from subledger transactions via Create Accounting |
| **Imported Journals** | External Systems | Loaded via FBDI (File-Based Data Import) or integration |
| **Recurring Journals** | General Ledger | Template journals that repeat each period |
| **Allocation Journals** | General Ledger | Distribute amounts across multiple accounts based on rules |

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Journal Components**

**Journal Header:**
- Ledger
- Journal source
- Journal category
- Accounting period
- Currency
- Journal description

**Journal Lines:**
- Line number
- Account combination
- Debit amount
- Credit amount
- Line description

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Journal Lifecycle**

**1. Create**
- Enter journal header and lines
- Journal status: Unposted

**2. Validate**
- Check balancing
- Verify account combinations
- Validate against cross-validation rules

**3. Approve (Optional)**
- Route through approval workflow
- Based on journal approval rules

**4. Post**
- Update GL balances
- Journal status: Posted
- Cannot be modified after posting

**5. Reverse (Optional)**
- Create reversing entry
- Typically in next period

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Example Journal Entry**

**Scenario:** Record purchase of equipment for $10,000 cash

```
Journal Header:
  Ledger: US Primary Ledger
  Source: General Ledger
  Category: Adjustment
  Period: Jan-2025
  Currency: USD
  Description: Purchase equipment

Journal Lines:
  Line 1:
    Account: 3111-00-15000-000-0000 (Equipment)
    Debit: 10,000.00
    Credit: 0.00
    Description: Equipment purchase

  Line 2:
    Account: 3111-00-11010-000-0000 (Cash)
    Debit: 0.00
    Credit: 10,000.00
    Description: Cash payment

Total Debits: 10,000.00
Total Credits: 10,000.00
Status: Balanced ✓
```

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Journal Processing Options**

**AutoPost:**
- Automatically post journals based on criteria
- Define AutoPost Criteria Sets
- Specify source, category, amount thresholds

**Journal Approval:**
- Route journals through approval workflow
- Define Journal Approval Rules
- Based on amount, source, category

**Journal Reversal:**
- Automatically reverse journals
- Define Journal Reversal Criteria Sets
- Specify reversal period and method

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Journal Import**

**FBDI (File-Based Data Import):**
- Import journals from external systems
- Use Load Interface File for Import process
- Then run Import Journals process

**Privileges:**
- Run Import Journals Program (full access)
- Run Import Journals Program without FBDI Access (restricted)

**Security Consideration:**
- Separate FBDI import access from other journal import
- Prevent unauthorized mass imports
- Assign appropriate privileges based on user role

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Subledger Journals**

**Create Accounting Process:**
- Converts subledger transactions to accounting entries
- Uses Subledger Accounting rules
- Creates journal entries in GL

**Transfer to GL:**
- Post Subledger Journal Entry to General Ledger
- Updates GL balances
- Maintains drill-down link to source transaction

**Example Flow:**
```
AP Invoice Created
    ↓
Create Accounting (Subledger Accounting)
    ↓
Subledger Journal Created
    ↓
Transfer to GL
    ↓
GL Journal Posted
    ↓
GL Balances Updated
```

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Journal Security**

**Data Access:**
- Users need data access set for ledger
- Segment value security may restrict accounts
- Business function: General Ledger

**Function Security:**
- Create journals
- Post journals
- Approve journals
- Reverse journals
- Import journals

**Example:**
```
User: General Accountant
Data Access Set: US Primary Ledger (Read-Write)
Segment Value Security: All accounts

Can:
- Create manual journals
- Post journals
- View all journal entries
- Run journal reports

Cannot:
- Access other ledgers
- Import journals via FBDI (if privilege not assigned)
```


## **3. Balances**

### **What Are GL Balances?**

GL balances are the cumulative totals maintained for each account combination. They're updated when journals are posted and provide the foundation for financial reporting and inquiry.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **GL Balances Cube**

**What Is It?**
- Essbase-based multidimensional database
- Stores aggregated balance data
- Optimized for fast query and reporting
- Created automatically during ledger setup

**Characteristics:**
- One cube per unique chart of accounts and calendar combination
- Each segment becomes a dimension in the cube
- Standard dimensions: Period, Currency, Scenario

**Example:**
```
Ledger: US Primary Ledger
Chart of Accounts: US COA (5 segments)
Calendar: US Calendar

Balances Cube Dimensions:
- Company (from COA segment 1)
- Line of Business (from COA segment 2)
- Account (from COA segment 3)
- Cost Center (from COA segment 4)
- Product (from COA segment 5)
- Period
- Currency
- Scenario
```

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Balance Types**

| Balance Type | Description | When Updated |
|--------------|-------------|--------------|
| **Period Balance** | Balance for specific accounting period | When journals posted in that period |
| **Beginning Balance** | Balance at start of period | Carried forward from prior period |
| **Ending Balance** | Balance at end of period | Beginning Balance + Period Activity |
| **Year-to-Date Balance** | Cumulative balance from fiscal year start | Updated each period |
| **Quarter-to-Date Balance** | Cumulative balance from quarter start | Updated each period |

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **How Balances Are Updated**

**Journal Posting:**
```
1. User creates journal
2. Journal validated
3. Journal posted
4. GL balances updated in real-time
5. Balances cube updated (periodic refresh)
```

**Example:**
```
Account: 3111-00-11010-000-0000 (Cash)
Period: Jan-2025

Beginning Balance: $100,000
Journal Posted: +$50,000 (debit)
Ending Balance: $150,000

Period Balance: +$50,000
YTD Balance: +$50,000 (first period of year)
```

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Balance Inquiry**

**Tools for Viewing Balances:**

**1. Account Monitor**
- View balances by account
- Filter by period, ledger
- Drill down to journal details

**2. Smart View**
- Excel-based inquiry tool
- Query balances cube directly
- Create custom balance reports
- Requires Smart View client installation

**3. Account Analysis Report**
- Standard GL report
- Shows beginning balance, activity, ending balance
- Can filter by account, period, ledger

**4. Trial Balance Report**
- Lists all accounts with balances
- Shows debits and credits
- Verifies ledger is in balance

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Balances Cube Setup**

**Automatic Creation:**
- Created during ledger setup
- No manual configuration needed
- One cube per COA and calendar combination

**Database Connection (for Financial Reporting):**
- Required for Financial Reporting Center
- Connects to Essbase cube
- Enables report creation

**Setup Steps:**
1. Complete ledger setup (cube created automatically)
2. Define Essbase database connection
3. Configure Smart View client for users
4. Publish account hierarchies (for security)

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Balance Security**

**Data Access Set:**
- Controls which ledgers user can query
- Restricts primary balancing segment values (if applicable)

**Segment Value Security:**
- Restricts which account values user can see
- Applied when querying balances
- Enforced in Account Monitor, Smart View, reports

**Example:**
```
User: Financial Analyst
Data Access Set: US Primary Ledger (Read-Only)
Segment Value Security: Companies 3111, 3121 only

Can View Balances For:
- US Primary Ledger
- Companies 3111 and 3121 only
- All periods
- Cannot see other company balances

Cannot:
- Create or post journals (Read-Only access)
- View other ledgers
- See balances for other companies
```

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Example Trial Balance**

```
US Primary Ledger - Trial Balance
Period: Jan-2025
Currency: USD

Account          Description              Beginning    Debits      Credits     Ending
                                         Balance                              Balance
─────────────────────────────────────────────────────────────────────────────────────
11010           Cash                     0.00         90,000.00   0.00        90,000.00
12010           Bad Debt Reserve         0.00         10,000.00   0.00        10,000.00
21010           Accounts Payable         0.00         0.00        20,000.00   -20,000.00
31001           Common Stock             0.00         0.00        50,000.00   -50,000.00
40110           Revenue                  0.00         0.00        60,000.00   -60,000.00
52110           Cost of Goods Sold       0.00         30,000.00   0.00        30,000.00
─────────────────────────────────────────────────────────────────────────────────────
Total                                    0.00         130,000.00  130,000.00  0.00

Ledger is in balance ✓
```

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


## **4. Period Status**

### **What Is Period Status?**

Period status controls which accounting periods are open for transaction entry and posting. It's a critical control mechanism for financial close processes.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Period Status Values**

| Status | Description | Transactions Allowed |
|--------|-------------|---------------------|
| **Never Opened** | Initial status for future periods | None |
| **Open** | Period is open for transactions | All transaction types |
| **Closed** | Period is closed for regular transactions | Only adjustment journals (if allowed) |
| **Permanently Closed** | Period is locked | None - cannot be reopened |

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Period Status Lifecycle**

```
Never Opened
    ↓
  Open (Open First Period task)
    ↓
  Closed (Close Period task)
    ↓
  Permanently Closed (Permanently Close Period task)
```

**Transitions:**
- Never Opened → Open: Open First Period or Open Next Period
- Open → Closed: Close Period
- Closed → Open: Reopen Period (if not permanently closed)
- Closed → Permanently Closed: Permanently Close Period (irreversible)

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Opening Periods**

**Open First Period:**
- Task performed after ledger setup
- Opens the first accounting period
- Required before any transactions can be entered

**Open Next Period:**
- Opens the next sequential period
- Can open multiple periods in advance
- Allows users to enter transactions in future periods

**Example:**
```
Fiscal Year: 2025 (Jan-Dec)
Current Date: January 15, 2025

Period Status:
- Jan-2025: Open (first period opened)
- Feb-2025: Open (opened in advance)
- Mar-2025: Never Opened
- Apr-2025: Never Opened
...
```

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Closing Periods**

**Close Period:**
- Closes period to regular transactions
- Part of month-end close process
- Can be reopened if needed

**Close Process:**
1. Complete all transactions for the period
2. Run subledger Create Accounting
3. Transfer subledger journals to GL
4. Post all journals
5. Run period close reports
6. Reconcile accounts
7. Close the period

**Permanently Close Period:**
- Locks period permanently
- Cannot be reopened
- Typically done after audit completion
- Recommended for prior fiscal years

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Period Close Monitor**

**What Is It?**
- Dashboard for tracking period close activities
- Shows status of close tasks
- Identifies incomplete activities

**Key Features:**
- Task checklist
- Status tracking
- Exception reporting
- Close timeline

**Navigation:** General Accounting > Period Close > Close Monitor

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Adjusting Periods**

**What Are They?**
- Special periods for year-end adjustments
- Separate from regular monthly periods
- Used for closing, auditing, or other adjustments

**Configuration:**
- Defined during calendar setup
- Typically 1-3 adjusting periods
- Named: Adj-1, Adj-2, Adj-3

**Example:**
```
Fiscal Year 2025:
- Jan-2025 through Dec-2025 (regular periods)
- Adj-1 (adjusting period 1)
- Adj-2 (adjusting period 2)

Use Case:
- Dec-2025: Regular month-end entries
- Adj-1: Year-end closing entries
- Adj-2: Audit adjustments
```

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Period Status by Ledger**

**Independent Status:**
- Each ledger has its own period status
- Primary ledger and secondary ledgers managed separately
- Allows different close schedules

**Example:**
```
US Primary Ledger:
- Jan-2025: Closed
- Feb-2025: Open
- Mar-2025: Never Opened

US Reporting Ledger:
- Jan-2025: Open (still processing adjustments)
- Feb-2025: Never Opened
- Mar-2025: Never Opened
```

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Period Status Tasks**

**Task:** Manage Accounting Periods

**Navigation:** Setup and Maintenance > Manage Accounting Periods

**Actions:**
- View period status
- Open first period
- Open next period
- Close period
- Reopen period
- Permanently close period

**Security:**
- Requires appropriate GL job role
- Typically General Accounting Manager or Controller

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Best Practices**

**Period Opening:**
- Open 1-2 periods in advance for flexibility
- Don't open too many periods (security risk)
- Communicate period opening to users

**Period Closing:**
- Follow consistent close calendar
- Complete all close tasks before closing
- Run reconciliation reports
- Document close process

**Permanent Closure:**
- Permanently close prior fiscal years after audit
- Maintain audit trail
- Document closure decisions

**Exception Handling:**
- Define process for posting to closed periods
- Require approval for period reopening
- Log all period status changes

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


## **General Ledger Setup Summary**

### **Implementation Checklist**

**1. Chart of Accounts Setup**
- [ ] Design chart of accounts structure
- [ ] Define segments and segment labels
- [ ] Create value sets and values
- [ ] Build account hierarchies
- [ ] Upload chart of accounts

**2. Ledger Setup**
- [ ] Define accounting calendar
- [ ] Create primary ledger
- [ ] Assign chart of accounts and calendar
- [ ] Set ledger currency
- [ ] Configure ledger options

**3. Data Security**
- [ ] Create data access sets
- [ ] Assign data access to users
- [ ] Configure segment value security (if needed)
- [ ] Test user access

**4. Journal Processing**
- [ ] Define journal sources and categories
- [ ] Configure journal approval rules (if needed)
- [ ] Set up AutoPost criteria (if needed)
- [ ] Configure journal reversal criteria (if needed)

**5. Period Management**
- [ ] Open first period
- [ ] Open additional periods as needed
- [ ] Define period close process
- [ ] Configure Close Monitor

**6. Balances and Reporting**
- [ ] Verify balances cube creation
- [ ] Define Essbase database connections
- [ ] Configure Smart View for users
- [ ] Create financial reports

**7. Integration**
- [ ] Configure subledger accounting
- [ ] Set up intercompany balancing rules
- [ ] Test subledger to GL transfer
- [ ] Verify drill-down functionality

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


## **Key Takeaways**

1. **Chart of Accounts is foundational** - Plan carefully as it cannot be easily changed after go-live

2. **Segment labels provide special functionality** - Use Primary Balancing Segment, Natural Account, and Cost Center appropriately

3. **Journals must balance** - All journal entries must have equal debits and credits

4. **Balances are stored in Essbase cube** - Optimized for fast query and reporting

5. **Period status controls transaction entry** - Open periods allow transactions, closed periods restrict them

6. **Open first period before transactions** - Required step after ledger setup

7. **Use adjusting periods for year-end** - Separate regular activity from closing adjustments

8. **Permanently close prior years** - After audit completion to lock historical data

9. **Security applies at multiple levels** - Data access sets, segment value security, and function security

10. **Test thoroughly before go-live** - Validate chart of accounts, journals, balances, and security
