# Ledgers and Legal Entities

## **What Are Ledgers and Legal Entities?**

Ledgers and Legal Entities are fundamental components of Oracle Fusion Financials enterprise structure. They define how you organize, record, and report financial information.

**Ledger** = The accounting book where financial transactions are recorded and maintained

**Legal Entity** = A recognized party with legal rights and responsibilities, required to account for itself

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


## **Enterprise Structure Overview**

```
Enterprise
    ↓
Legal Entities (Legal Structure)
    ↓
Ledgers (Accounting Structure)
    ↓
Business Units (Operational Structure)
    ↓
Transactions
```

Every enterprise has three fundamental structures:
1. **Legal Structure** - Legal entities for compliance and reporting
2. **Accounting Structure** - Ledgers for financial recording
3. **Operational Structure** - Business units for transaction processing

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


## **Legal Entities**

### **What Is a Legal Entity?**

A legal entity is a recognized party with rights and responsibilities given by legislation. It has the right to own property and the responsibility to account for itself.

**Key Characteristics:**
- Legally registered organization
- Can enter into contracts
- Can own assets and incur liabilities
- Required to file statutory reports
- Subject to taxation

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Legal Entity Components**

| Component | Description | Example |
|-----------|-------------|---------|
| **Legal Entity Name** | Official registered name | ABC Corporation USA |
| **Registration Number** | Government registration ID | 12-3456789 |
| **Country** | Country of registration | United States |
| **Address** | Legal address | 123 Main St, New York, NY 10001 |
| **Reporting Unit Registration Number** | Lowest level component requiring registration | Branch-specific registration |

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Legal Entity Examples**

**Single Country Organization:**
```
ABC Corporation
└── ABC Corporation USA (Legal Entity)
    - Registration: 12-3456789
    - Country: United States
    - Primary Balancing Segment Value: 1000
```

**Multi-Country Organization:**
```
Global Corp
├── Global Corp USA (Legal Entity)
│   - Registration: 12-3456789
│   - Country: United States
│   - Primary Balancing Segment Value: 1000
├── Global Corp UK (Legal Entity)
│   - Registration: GB123456789
│   - Country: United Kingdom
│   - Primary Balancing Segment Value: 2000
└── Global Corp Canada (Legal Entity)
    - Registration: CA987654321
    - Country: Canada
    - Primary Balancing Segment Value: 3000
```

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Legal Entity to Primary Balancing Segment Mapping**

**Key Concept:**
Legal entities are typically mapped to primary balancing segment values in the chart of accounts.

**Why?**
- Ensures journals balance by legal entity
- Enables legal entity reporting
- Supports statutory compliance
- Facilitates data security by legal entity

**Example:**
```
Chart of Accounts: Company-Department-Account-Cost Center-Product
Primary Balancing Segment: Company

Legal Entity Mapping:
- ABC Corporation USA → Company 1000
- ABC Corporation UK → Company 2000
- ABC Corporation Canada → Company 3000

Result:
All transactions for ABC Corporation USA use Company 1000
All journals must balance for Company 1000
Reports can be run by legal entity (Company value)
```

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


## **Ledgers**

### **What Is a Ledger?**

A ledger is the accounting book that maintains financial records. It's where all transactions are recorded, balanced, and reported.

**Key Characteristics:**
- Required component for financial recording
- Characterized by chart of accounts, calendar, and currency
- Contains journals, balances, and accounting periods
- Foundation for financial reporting

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Ledger Components**

| Component | Description | Can Be Changed? |
|-----------|-------------|-----------------|
| **Chart of Accounts** | Account structure for recording transactions | No (after setup) |
| **Accounting Calendar** | Fiscal periods and year structure | No (after setup) |
| **Currency** | Ledger currency for recording | No (after setup) |
| **Subledger Accounting Method** | Rules for creating accounting entries | Yes |
| **Ledger Options** | Configuration settings | Yes (some) |

**CAUTION:** Chart of accounts, calendar, and currency cannot be changed after ledger setup is complete.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Types of Ledgers**

**1. Primary Ledger**
- Main accounting ledger
- Required for all implementations
- Records all transactions
- Source for financial reporting
- One per legal entity or group of legal entities

**2. Secondary Ledger**
- Additional accounting representation
- Uses different accounting rules
- Can have different chart of accounts or calendar
- Optional
- Examples: GAAP vs IFRS, Management reporting

**3. Reporting Currency**
- Currency conversion of primary ledger
- Same chart of accounts and calendar as primary
- Different currency
- Optional
- Example: USD primary ledger with EUR reporting currency

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Primary Ledger Details**

**Creation:**
- Created during rapid implementation
- One primary ledger per unique country in legal entities
- Automatically assigned chart of accounts, calendar, and currency

**Naming Convention:**
```
Ledger Name: InFusion Ledger
Legal Entities:
  - InFusion USA (Country: United States)
  - InFusion Canada (Country: Canada)

Result:
  - InFusion Ledger US (Primary Ledger for USA)
  - InFusion Ledger CA (Primary Ledger for Canada)

Country code automatically appended to ledger name
```

**Characteristics:**
- Standard accrual subledger accounting method assigned
- GL balances cube created automatically
- Data access set created automatically
- Period status managed independently

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Ledger Example**

```
Primary Ledger: US Primary Ledger

Components:
  Chart of Accounts: US COA (Company-Dept-Account-Cost Center-Product)
  Calendar: US Calendar (Jan-Dec, 2 adjusting periods)
  Currency: USD
  Subledger Accounting Method: Standard Accrual

Legal Entities Assigned:
  - ABC Corporation USA (Company 1000)
  - XYZ Corporation USA (Company 1100)

Business Units Using This Ledger:
  - US East BU
  - US West BU
  - US Central BU

Balances Cube: US_COA_US_Calendar_Cube
Data Access Set: US Primary Ledger (implicit)
```

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


## **Relationship Between Ledgers and Legal Entities**

### **Key Relationships**

**1. Legal Entity → Primary Balancing Segment Value**
```
Legal Entity: ABC Corporation USA
Mapped To: Company 1000 (Primary Balancing Segment)
```

**2. Legal Entity → Ledger**
```
Legal Entity: ABC Corporation USA
Assigned To: US Primary Ledger
```

**3. Ledger → Chart of Accounts**
```
Ledger: US Primary Ledger
Uses: US COA
Primary Balancing Segment: Company
```

**4. Complete Flow**
```
Legal Entity (ABC Corporation USA)
    ↓
Primary Balancing Segment Value (Company 1000)
    ↓
Ledger (US Primary Ledger)
    ↓
Chart of Accounts (US COA)
    ↓
Transactions recorded with Company 1000
```

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Balancing by Legal Entity**

**Concept:**
All journals must balance for each primary balancing segment value (legal entity).

**Example:**
```
Journal Entry:
Line 1: Company 1000 - Cash - Debit $10,000
Line 2: Company 1000 - Revenue - Credit $10,000

Status: Balanced ✓ (Company 1000 balances)

Journal Entry:
Line 1: Company 1000 - Cash - Debit $10,000
Line 2: Company 2000 - Revenue - Credit $10,000

Status: Out of Balance ✗ (Different companies)
Action: Intercompany balancing creates additional lines
```

**Intercompany Balancing:**
When journal is out of balance by legal entity, system automatically creates intercompany receivable and payable lines to balance.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


## **Business Units**

### **What Are Business Units?**

Business units perform business functions and can process transactions on behalf of many legal entities.

**Key Characteristics:**
- Operational structure
- Process transactions (AP, AR, Procurement, etc.)
- Can serve multiple legal entities
- Have manager, objectives, autonomy
- Responsibility for profit and loss

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Business Unit Components**

| Component | Description |
|-----------|-------------|
| **Business Unit Name** | Unique identifier |
| **Default Legal Entity** | Primary legal entity for the BU |
| **Assigned Ledger** | Ledger based on default legal entity |
| **Enabled Functions** | AP, AR, Procurement, Projects, etc. |

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Business Unit to Ledger Assignment**

**Rule:**
Business unit is assigned to the primary ledger of its default legal entity.

**Example:**
```
Legal Entity: ABC Corporation USA
Assigned To: US Primary Ledger

Business Unit: US East BU
Default Legal Entity: ABC Corporation USA
Result: US East BU assigned to US Primary Ledger

Business Unit: US West BU
Default Legal Entity: ABC Corporation USA
Result: US West BU assigned to US Primary Ledger
```

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Business Unit Processing**

**Transaction Flow:**
```
1. User creates AP invoice in US East BU
2. Invoice references legal entity (Company 1000)
3. Create Accounting generates subledger journal
4. Journal posted to US Primary Ledger
5. Balances updated for Company 1000
```

**Key Point:**
A business unit can process transactions on behalf of many legal entities, but all transactions post to the ledger assigned to the business unit.


## **Setup Process**

### **Rapid Implementation Workbook**

**Task:** Create Chart of Accounts, Ledger, Legal Entities, and Business Units in Spreadsheet

**Navigation:** Setup and Maintenance > Define Financials Configuration for Rapid Implementation

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Workbook Sheets**

**1. Chart of Accounts, Calendar, and Ledger**
- Define ledger name
- Specify currency (if single ledger)
- Define calendar (period frequency, adjusting periods, fiscal year start)
- Define chart of accounts segments

**2. Companies and Legal Entities**
- Enter company hierarchy (primary balancing segment)
- Enter legal entity details:
  - Legal entity name
  - Country
  - Address
  - Registration number
  - Reporting unit registration number

**3. Business Units**
- Enter business unit names
- Specify default legal entity for each BU

**4. Natural Accounts**
- Enter account values and hierarchies
- Specify account types

**5. Additional Segment Sheets**
- Auto-generated for each segment
- Enter segment values and hierarchies

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Setup Steps**

**Step 1: Download Workbook**
- From Manage Chart of Accounts Configurations task
- Or from implementation project

**Step 2: Complete Chart of Accounts, Calendar, and Ledger Sheet**
```
Ledger Name: InFusion Ledger
Currency: (Leave blank if entering legal entities)
Period Frequency: Month
Adjusting Periods: 2
Fiscal Year Start Date: 01-JAN-2025

Chart of Accounts Segments:
1. Company (Primary Balancing Segment)
2. Department
3. Account (Natural Account)
4. Cost Center
5. Product
```

**Step 3: Complete Companies and Legal Entities Sheet**
```
Company Hierarchy:
Parent: 1000 (ABC Corporation)
  Child: 1000 (ABC Corporation USA)
    Legal Entity: ABC Corporation USA
    Country: United States
    Address: 123 Main St, New York, NY 10001
    Registration: 12-3456789

Parent: 2000 (XYZ Corporation)
  Child: 2000 (XYZ Corporation UK)
    Legal Entity: XYZ Corporation UK
    Country: United Kingdom
    Address: 456 High St, London, UK
    Registration: GB123456789
```

**Step 4: Complete Business Units Sheet**
```
Business Unit: US East BU
Default Legal Entity: ABC Corporation USA

Business Unit: US West BU
Default Legal Entity: ABC Corporation USA

Business Unit: UK Operations BU
Default Legal Entity: XYZ Corporation UK
```

**Step 5: Complete Natural Accounts Sheet**
- Enter account values
- Define account types (Asset, Liability, Expense, Revenue, Equity)
- Create account hierarchies

**Step 6: Validate**
- Click "Step 1: Validate"
- Review and fix errors
- Preview sample financial report

**Step 7: Generate Files**
- Step 2: Generate Chart of Accounts File (ChartOfAccounts.xml)
- Step 3: Generate Ledger, LE, and BU File (FinancialsCommonEntities.xml)

**Step 8: Upload Files**
- Upload Chart of Accounts file first
- Upload Ledger, Legal Entities, and Business Units file second
- Verify successful completion

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **What Gets Created**

**After Upload:**

**Ledgers:**
- InFusion Ledger US (Primary Ledger)
- InFusion Ledger UK (Primary Ledger)

**Legal Entities:**
- ABC Corporation USA (assigned to InFusion Ledger US)
- XYZ Corporation UK (assigned to InFusion Ledger UK)

**Business Units:**
- US East BU (assigned to InFusion Ledger US)
- US West BU (assigned to InFusion Ledger US)
- UK Operations BU (assigned to InFusion Ledger UK)

**Chart of Accounts:**
- US COA (shared by all ledgers)

**Balances Cubes:**
- One cube per unique COA and calendar combination

**Data Access Sets:**
- Implicit data access set for each ledger

**Document Sequences:**
- For Payables invoices, Payments, Receivables invoices, etc.
- For subledger journals and GL journals

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


## **Complete Example: Multi-Country Setup**

### **Scenario**

**Organization:** Global Manufacturing Corp
**Countries:** United States, Canada, United Kingdom
**Requirements:** Separate legal entities per country, shared chart of accounts

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Setup Configuration**

**Chart of Accounts:**
```
Name: Global COA
Segments:
1. Company (Primary Balancing Segment) - 4 digits
2. Department - 2 digits
3. Account (Natural Account) - 5 digits
4. Cost Center - 3 digits
5. Product - 4 digits
```

**Legal Entities:**
```
1. Global Manufacturing USA
   - Country: United States
   - Registration: 12-3456789
   - Company Value: 1000

2. Global Manufacturing Canada
   - Country: Canada
   - Registration: CA987654321
   - Company Value: 2000

3. Global Manufacturing UK
   - Country: United Kingdom
   - Registration: GB123456789
   - Company Value: 3000
```

**Ledgers Created:**
```
1. Global Manufacturing Ledger US
   - Chart of Accounts: Global COA
   - Calendar: Global Calendar (Jan-Dec)
   - Currency: USD
   - Legal Entity: Global Manufacturing USA (Company 1000)

2. Global Manufacturing Ledger CA
   - Chart of Accounts: Global COA
   - Calendar: Global Calendar (Jan-Dec)
   - Currency: CAD
   - Legal Entity: Global Manufacturing Canada (Company 2000)

3. Global Manufacturing Ledger UK
   - Chart of Accounts: Global COA
   - Calendar: Global Calendar (Jan-Dec)
   - Currency: GBP
   - Legal Entity: Global Manufacturing UK (Company 3000)
```

**Business Units:**
```
1. US Manufacturing BU
   - Default Legal Entity: Global Manufacturing USA
   - Assigned Ledger: Global Manufacturing Ledger US
   - Functions: AP, AR, Procurement

2. US Sales BU
   - Default Legal Entity: Global Manufacturing USA
   - Assigned Ledger: Global Manufacturing Ledger US
   - Functions: AR, Order Management

3. Canada Operations BU
   - Default Legal Entity: Global Manufacturing Canada
   - Assigned Ledger: Global Manufacturing Ledger CA
   - Functions: AP, AR, Procurement

4. UK Operations BU
   - Default Legal Entity: Global Manufacturing UK
   - Assigned Ledger: Global Manufacturing Ledger UK
   - Functions: AP, AR, Procurement
```

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Transaction Example**

**Scenario:** US Manufacturing BU purchases inventory

```
Transaction:
- Business Unit: US Manufacturing BU
- Legal Entity: Global Manufacturing USA
- Ledger: Global Manufacturing Ledger US

Journal Entry:
Line 1: 1000-10-15000-100-0001 (Inventory) - Debit $50,000
Line 2: 1000-10-21000-100-0001 (AP) - Credit $50,000

Company 1000 = Global Manufacturing USA
All lines balance for Company 1000 ✓
Posted to Global Manufacturing Ledger US
```

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


## **Data Security by Legal Entity**

### **Using Primary Balancing Segment Values**

**Concept:**
Secure access to specific legal entities using primary balancing segment value security.

**Example:**
```
User: US Controller
Data Access Set: US Operations
Type: Primary Balancing Segment Value
Values:
  - Company 1000 (Read-Write)

Result:
- Can create journals for Company 1000 only
- Can view balances for Company 1000 only
- Cannot access Company 2000 or 3000
- Effectively restricted to Global Manufacturing USA legal entity
```

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Data Access Set Example**

```
Data Access Set: US Financial Services
Ledger: US Financial Services Ledger
Type: Primary Balancing Segment Value

Primary Balancing Segment Values:
  - 101 (Banks) - Read and Write
  - 102 (Capital) - Read and Write
  - 131 (Insurance) - Read Only

Legal Entity Mapping:
  - Company 101 = Banks Legal Entity
  - Company 102 = Capital Legal Entity
  - Company 131 = Insurance Legal Entity

User with this data access set can:
- Create journals for Banks and Capital legal entities
- View journals for Insurance legal entity
- Cannot create journals for Insurance legal entity
- Cannot access any other legal entities
```

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


## **Ledger Sets**

### **What Are Ledger Sets?**

Collections of ledgers for batch processing or financial reporting.

**Use Cases:**
- Run processes across multiple ledgers
- Consolidate reporting
- Batch journal posting
- Period close activities

**Example:**
```
Ledger Set: Global Ledgers
Contains:
  - Global Manufacturing Ledger US
  - Global Manufacturing Ledger CA
  - Global Manufacturing Ledger UK

Use:
- Run consolidation reports
- Post journals to all ledgers
- Close periods across all ledgers
```

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


## **Important Considerations**

### **Cannot Be Changed After Setup**

**Ledger:**
- Chart of accounts assignment
- Accounting calendar assignment
- Currency

**Legal Entity:**
- Country
- Primary balancing segment value mapping

**Chart of Accounts:**
- Segment structure
- Segment labels
- Calendar pattern

**Plan Carefully!**

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Best Practices**

**1. Legal Entity Design**
- One legal entity per registered company
- Map to primary balancing segment values
- Document legal entity structure
- Consider statutory reporting requirements

**2. Ledger Design**
- One primary ledger per country (typical)
- Shared chart of accounts when possible
- Consider reporting currency needs
- Plan for secondary ledgers if needed

**3. Business Unit Design**
- Align with operational structure
- One BU per major business function/location
- Assign appropriate default legal entity
- Enable only needed functions

**4. Chart of Accounts**
- Design for all legal entities
- Use primary balancing segment for legal entities
- Plan segment structure carefully
- Cannot change after setup

**5. Testing**
- Test with sample data before go-live
- Verify legal entity balancing
- Test intercompany transactions
- Validate reporting by legal entity

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


## **Key Takeaways**

1. **Legal entities are legally registered organizations** - Required for statutory compliance

2. **Ledgers are accounting books** - Characterized by chart of accounts, calendar, and currency

3. **Legal entities map to primary balancing segment values** - Enables legal entity balancing and reporting

4. **One primary ledger per country** - Automatically created based on legal entity countries

5. **Business units process transactions** - Assigned to ledger based on default legal entity

6. **Journals must balance by legal entity** - Primary balancing segment ensures this

7. **Cannot change fundamental attributes** - Chart of accounts, calendar, currency locked after setup

8. **Data security by legal entity** - Use primary balancing segment value-based data access sets

9. **Rapid implementation workbook** - Single source for creating ledgers, legal entities, and business units

10. **Plan carefully before setup** - Changes are difficult or impossible after go-live
