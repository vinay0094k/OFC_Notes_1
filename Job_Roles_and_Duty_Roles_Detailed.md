# Job Roles and Duty Roles for Financial Modules

## **What Are Job Roles and Duty Roles?**

Job roles and duty roles are the foundation of Oracle Fusion Financials security. They control what users can do in the system by granting access to specific functions, pages, and processes.

**Job Roles** = Collections of duties that represent a complete job function (e.g., Accounts Payable Manager)

**Duty Roles** = Building blocks that provide access to specific tasks and functions (e.g., Invoice Processing, Payment Creation)

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


## **Role Hierarchy**

```
User
  ↓
Job Role (e.g., Accounts Payable Manager)
  ↓
Duty Roles (e.g., Invoice Processing Duty, Payment Creation Duty)
  ↓
Privileges (Function Security)
  ↓
Access to Pages, Processes, Reports
```

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


## **Types of Roles**

### **1. Job Roles**
Represent complete job functions with all necessary duties.

**Characteristics:**
- Assigned directly to users
- Contain multiple duty roles
- Represent real-world job positions
- Predefined by Oracle or custom-created

**Examples:**
- Accounts Payable Manager
- General Accounting Manager
- Accounts Receivable Specialist
- Asset Accountant

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **2. Duty Roles**
Provide access to specific tasks and functions.

**Types of Duty Roles:**

**Functional Duty Roles:**
- Grant access to transactional functions
- Examples: Payables Invoice Processing, Journal Management

**Transaction Analysis Duty Roles (OTBI):**
- Grant access to reporting subject areas
- Role codes start with FBI_
- Examples: Payables Invoice Transaction Analysis Duty

**Self-Service Reporting Duty Roles:**
- Grant access to specific subject areas for reporting
- Building blocks for custom reporting roles
- Examples: Payables Self Service Reporting Duty

**Financials Duty Roles:**
- Grant access to Financials-specific functions
- Role codes start with ORA_
- Examples: Payables Balance Analysis

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **3. Abstract Roles**
Provide common functionality across applications.

**Examples:**
- Enterprise Resource Planning Self Service User
- Employee
- Contingent Worker
- Line Manager

**Purpose:**
- Grant access to common self-service functions
- Expense reports, time cards, approvals
- Shared across multiple Oracle Cloud applications

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **4. Implementation Roles**
Special roles for setup and configuration.

| Role | Purpose | When to Use |
|------|---------|-------------|
| **Application Implementation Manager** | Manage implementation projects | During implementation to assign tasks |
| **Application Implementation Consultant** | Access all setup tasks | During implementation for configuration |
| **IT Security Manager** | Manage roles, users, security | For security administration |
| **Financial Integration Specialist** | Manage financial integrations | For integration setup and management |
| **Financial Application Administrator** | Ongoing setup management | Post-implementation for setup changes |

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


## **Predefined Job Roles by Module**

### **General Ledger**

| Job Role | Description | Key Responsibilities |
|----------|-------------|---------------------|
| **General Accounting Manager** | Comprehensive GL access | Create journals, post, close periods, manage ledgers, all GL functions |
| **General Accountant** | Standard GL functions | Create journals, view accounting, run reports, period activities |
| **Financial Analyst** | Read-only analysis | View journals, balances, run reports, analyze financial data |

**Inherited Duty Roles (General Accounting Manager):**
- Journal Management
- Period Close Management
- Ledger Management
- General Ledger Self Service Reporting Duty
- General Ledger Transaction Analysis Duty
- BI Consumer Role

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Accounts Payable**

| Job Role | Description | Key Responsibilities |
|----------|-------------|---------------------|
| **Accounts Payable Manager** | Full AP management | Create/approve invoices, process payments, manage suppliers, all AP functions |
| **Accounts Payable Supervisor** | AP supervision | Review invoices, approve payments, manage AP team activities |
| **Accounts Payable Specialist** | AP transaction processing | Create invoices, enter expenses, process receipts, basic AP tasks |

**Inherited Duty Roles (Accounts Payable Manager):**
- Payables Invoice Processing
- Payables Payment Processing
- Payables Balance Analysis
- Payables Invoice Transaction Analysis Duty (OBI)
- Payables Payment Transaction Analysis Duty (OBI)
- Payables Self Service Reporting Duty
- BI Consumer Role

**Key Privileges:**
- Create Invoices
- Approve Invoices
- Force Approve Invoices
- Create Payments
- Manage Suppliers
- Run Import Journals Program

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Accounts Receivable**

| Job Role | Description | Key Responsibilities |
|----------|-------------|---------------------|
| **Accounts Receivable Manager** | Full AR management | Create/approve invoices, process receipts, manage customers, all AR functions |
| **Accounts Receivable Specialist** | AR transaction processing | Create customer invoices, apply receipts, process adjustments |

**Inherited Duty Roles (Accounts Receivable Manager):**
- Receivables Invoice Processing
- Receivables Receipt Processing
- Receivables Customer Management
- Receivables Customer Transaction Analysis Duty (OBI)
- Receivables Transaction Analysis Duty (OBI)
- Receivables Receipts Transaction Analysis Duty (OBI)
- Receivables Self Service Reporting Duty
- BI Consumer Role

**Key Functions:**
- Create customer invoices
- Apply receipts
- Process credit memos
- Manage adjustments
- Customer account management
- Collections activities

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Fixed Assets**

| Job Role | Description | Key Responsibilities |
|----------|-------------|---------------------|
| **Asset Accounting Manager** | Full FA management | Manage all asset activities, depreciation, transfers, retirements |
| **Asset Accountant** | Asset transaction processing | Add assets, process depreciation, manage asset records |

**Inherited Duty Roles (Asset Accountant):**
- Fixed Asset Management
- Fixed Asset Transaction Analysis Duty (OBI)
- Fixed Asset Self Service Reporting Duty
- BI Consumer Role

**Key Functions:**
- Add fixed assets
- Change asset details
- Retire assets
- Process depreciation
- Asset transfers
- Run asset reports

**Data Privileges (Asset Book Level):**
- Add Fixed Asset Data
- Change Fixed Asset Data
- Retire Fixed Asset Data
- Track Fixed Asset Data
- Submit Fixed Assets Reports

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Cash Management**

| Job Role | Description | Key Responsibilities |
|----------|-------------|---------------------|
| **Cash Manager** | Cash management | Manage bank accounts, reconciliations, cash forecasting |

**Inherited Duty Roles:**
- Cash Management Operations
- Cash Management Self Service Reporting Duty
- BI Consumer Role

**Key Functions:**
- Manage bank accounts
- Bank reconciliations
- Cash positioning
- Cash forecasting
- Bank statement processing

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Expense Management**

| Job Role | Description | Key Responsibilities |
|----------|-------------|---------------------|
| **Expense Manager** | Expense management | Manage expense policies, approve expenses, expense reporting |

**Inherited Duty Roles:**
- Expense Management
- Expense Self Service Reporting Duty
- BI Consumer Role

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Tax**

| Job Role | Description | Key Responsibilities |
|----------|-------------|---------------------|
| **Tax Manager** | Tax management | Manage tax configuration, tax reporting, compliance |
| **Tax Administrator** | Tax administration | Configure tax rules, manage tax setup |
| **Tax Accountant** | Tax accounting | Process tax transactions, tax reconciliation |
| **Tax Specialist** | Tax processing | Handle tax-related transactions |

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Intercompany**

| Job Role | Description | Key Responsibilities |
|----------|-------------|---------------------|
| **Intercompany Accountant** | Intercompany transactions | Manage intercompany transactions, reconciliations |

**Inherited Duty Roles:**
- Intercompany Transaction Management
- BI Consumer Role

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Budget Management**

| Job Role | Description | Key Responsibilities |
|----------|-------------|---------------------|
| **Budget Manager** | Budget management | Create budgets, manage budget cycles, budget reporting |

**Inherited Duty Roles:**
- Budget Management
- Budgetary Control Self Service Reporting Duty
- BI Consumer Role

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Cross-Module Roles**

| Job Role | Description | Access Scope |
|----------|-------------|--------------|
| **Financial Analyst** | Financial analysis | All Financials modules (read-only) |
| **Financial Application Administrator** | Setup management | All Financials setup tasks |
| **Financial Integration Specialist** | Integration management | All Financials integration tasks |

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


## **Subject Area Access by Job Role**

### **OTBI Subject Areas and Required Roles**

| Subject Area | Job Role | Self-Service Reporting Duty | OTBI Transaction Analysis Duty |
|--------------|----------|----------------------------|-------------------------------|
| **General Ledger - Journals Real Time** | General Accountant | General Ledger Self Service Reporting Duty | General Ledger Transaction Analysis Duty |
| **General Ledger - Balances Real Time** | General Accountant | General Ledger Self Service Reporting Duty | General Ledger Transaction Analysis Duty |
| **Payables Invoices - Transactions Real Time** | Accounts Payable Manager | Payables Self Service Reporting Duty | Payables Invoice Transaction Analysis Duty |
| **Payables Payments - Disbursements Real Time** | Accounts Payable Manager | Payables Self Service Reporting Duty | Payables Payment Transaction Analysis Duty |
| **Receivables - Transactions Real Time** | Accounts Receivable Manager | Receivables Self Service Reporting Duty | Receivables Transaction Analysis Duty |
| **Receivables - Receipts Details Real Time** | Accounts Receivable Manager | Receivables Self Service Reporting Duty | Receivables Receipts Transaction Analysis Duty |
| **Fixed Assets - Asset Transactions Real Time** | Asset Accountant | Fixed Asset Self Service Reporting Duty | Fixed Asset Transaction Analysis Duty |
| **Subledger Accounting - Journals Real Time** | Cash Manager, AP Manager, AR Manager, Asset Accountant | Multiple | Subledger Accounting Transaction Analysis Duty |

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


## **Business Intelligence Roles**

### **BI Consumer Role**
- View reports from BI Catalog
- Run existing reports
- Cannot create new reports
- Inherited by all self-service reporting duties

### **BI Author Role**
- Create new reports from subject areas
- Edit existing reports
- Author analyses and dashboards
- Inherited by job roles that need authoring capability

### **BI Administrator Role**
- Full BI administration
- Manage BI Catalog permissions
- Configure BI settings
- Not inherited by standard Financials roles

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


## **Role Inheritance Example: Accounts Payable Manager**

```
Accounts Payable Manager (Job Role)
├── Payables Invoice Processing (Duty Role)
│   ├── Create Invoice Privilege
│   ├── Update Invoice Privilege
│   └── View Invoice Privilege
├── Payables Payment Processing (Duty Role)
│   ├── Create Payment Privilege
│   ├── Approve Payment Privilege
│   └── View Payment Privilege
├── Payables Balance Analysis (Financials Duty Role)
│   └── Access to Payables reports
├── Payables Invoice Transaction Analysis Duty (OBI Duty Role)
│   └── Access to Payables Invoice subject areas
├── Payables Payment Transaction Analysis Duty (OBI Duty Role)
│   └── Access to Payables Payment subject areas
├── Payables Self Service Reporting Duty
│   └── Access to all Payables subject areas
└── BI Consumer Role
    └── View reports in BI Catalog
```

**Result:** User assigned Accounts Payable Manager role can:
- Create and approve invoices
- Process payments
- View accounting
- Run all Payables reports
- Access Payables subject areas in OTBI
- View reports in BI Catalog


## **Subledger Accounting Security**

### **General Ledger Job Roles**

**Default Data Security:**
For ledgers user has access to:
- Review or create subledger accounting entries for ALL subledgers
- Account transactions, transfer to GL, drill down for ALL subledgers
- Inquiry and reporting for ALL subledgers

**Example:**
```
User: General Accounting Manager
Ledger Access: US Primary Ledger

Can Access Subledger Accounting For:
- Payables journals
- Receivables journals
- Assets journals
- All other subledger journals in US Primary Ledger
```

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Subledger Job Roles**

**Default Data Security:**
For specific security context (Business Unit, Asset Book) user has access to:
- Review or create subledger accounting entries for THAT subledger only
- Account transactions, transfer to GL, drill down for THAT subledger
- Inquiry and reporting for THAT subledger

**Example:**
```
User: Accounts Payable Supervisor
Business Unit Access: US East BU

Can Access Subledger Accounting For:
- Payables journals from US East BU only
- Cannot access AR, FA, or other subledger journals
- Cannot access Payables journals from other business units
```

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


## **Separation of Duties (SOD)**

### **What Is SOD?**

Separation of Duties prevents conflicts by separating activities like approving, recording, processing, and reconciling to prevent errors and fraud.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Common SOD Conflicts**

| Conflict | Risk | Example |
|----------|------|---------|
| **Create + Approve Invoices** | Unauthorized payments | User creates fake invoice and approves it |
| **Create + Approve Payments** | Fraudulent disbursements | User creates payment to personal account and approves it |
| **Create Journals + Post Journals** | Unauthorized accounting entries | User creates and posts fictitious entries |
| **Create Supplier + Create Invoice** | Fictitious vendor payments | User creates fake supplier and invoices |
| **Process Receipts + Apply Receipts** | Misappropriation of funds | User processes receipt and misapplies it |

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **SOD Example: Accounts Payable Manager**

**Predefined Role Includes:**
- Force Approve Invoices privilege
- Create Payments privilege

**Potential Conflict:**
User can both approve invoices AND create payments = SOD violation

**Resolution Options:**

**Option 1: Accept the Risk**
- Document business justification
- Implement compensating controls
- Regular audit reviews

**Option 2: Remove Privileges**
- Create custom role based on AP Manager
- Remove "Force Approve Invoices" privilege
- Assign to users who should not approve

**Option 3: Separate Roles**
- Assign AP Specialist role (create invoices)
- Assign separate Payment Processor role (create payments)
- Different users for each function

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **SOD Assessment Process**

**Step 1: Gather Stakeholders**
- Business process owners
- IT security administrators
- Internal audit team
- Financial governance team

**Step 2: Identify Relevant Roles**
- Review predefined roles
- Identify roles used in your organization
- Document role assignments

**Step 3: Assess SOD Conflicts**
- Identify potential conflicts
- Evaluate risk level
- Determine if conflicts are acceptable

**Step 4: Implement Controls**
- Modify roles if needed
- Implement compensating controls
- Document decisions

**Step 5: Monitor and Review**
- Regular SOD reviews
- Use Oracle ARCS (if available)
- Audit role assignments

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


## **Custom Job Roles**

### **When to Create Custom Roles**

**Create Custom Roles When:**
- Predefined roles don't match your business needs
- Need to remove privileges for SOD compliance
- Need unique combination of duties
- Organization-specific job functions

**Use Predefined Roles When:**
- They match your requirements
- Standard job functions
- Faster implementation
- Oracle maintains and updates them

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Creating Custom Roles**

**Method 1: Copy Predefined Role**

**Steps:**
1. Sign in with IT Security Manager role
2. Navigate to Security Console
3. Search for predefined role
4. Click "Copy Role"
5. Select "Deep Copy" (includes inherited roles)
6. Modify as needed
7. Save custom role

**Method 2: Create from Scratch**

**Steps:**
1. Navigate to Security Console
2. Click "Create Role"
3. Enter role details
4. Add duty roles
5. Add privileges (if needed)
6. Save role

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Custom Role Example: AP Invoice Processor (No Approval)**

**Requirement:**
User who can create invoices but cannot approve them.

**Solution:**
```
Custom Role: AP Invoice Processor
Based On: Accounts Payable Specialist
Modifications: None needed (Specialist role doesn't include approval)

Inherited Duty Roles:
- Payables Invoice Processing (create invoices)
- Payables Self Service Reporting Duty
- BI Consumer Role

Does NOT Include:
- Force Approve Invoices privilege
- Approve Invoice privilege
```

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Custom Role Example: GL Accountant (No FBDI Import)**

**Requirement:**
User who can create journals but cannot import via FBDI.

**Solution:**
```
Custom Role: GL Accountant No FBDI
Based On: General Accountant (deep copy)

Modifications:
1. Find Journal Management duty role
2. Remove: Run Import Journals Program privilege
3. Add: Run Import Journals Program without FBDI Access privilege

4. Find Subledger Accounting Manager duty role
5. Remove: Post Subledger Journal Entry to General Ledger privilege
6. Add: Post Subledger Journal Entry to GL No Journal Import Access for FBDI privilege

Result:
- Can create journals manually
- Can import journals from Create Accounting
- Can import journals from ADFdi spreadsheet
- Cannot import journals via FBDI
```

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Custom Role for OTBI Reporting**

**Requirement:**
Custom role with access to Fixed Asset reports.

**Solution:**
```
Custom Role: FA Report Analyst

Must Include BOTH:
1. Fixed Asset Transaction Analysis Duty (OBI version)
   - Role Code: FBI_*
   - Grants access to FA subject areas

2. Fixed Asset Transaction Analysis (Financials version)
   - Role Code: ORA_*
   - Grants data security policies

3. BI Consumer Role
   - View reports

Result:
- Access to Fixed Asset subject areas
- Data security for FA data
- Can view and run FA reports
- Cannot create new reports (no BI Author Role)
```

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


## **Role Assignment Best Practices**

### **1. Multiple Roles per User**

**DO:**
```
User: Finance Manager
Roles:
- General Accounting Manager
- Accounts Payable Manager
- Accounts Receivable Manager
```

**DON'T:**
```
User: Finance Manager
Roles:
- Super Finance Role (one role with everything)
```

**Why:**
- Easier to manage
- Better security control
- Follows least privilege principle
- Easier to audit

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **2. Use Predefined Roles**

**Advantages:**
- Oracle tested and maintained
- Updated with new features
- Documented in Security Reference guides
- Best practice configurations

**When to Customize:**
- SOD requirements
- Organization-specific needs
- Regulatory compliance
- Unique business processes

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **3. Document Custom Roles**

**Documentation Should Include:**
- Role name and purpose
- Based on which predefined role
- Modifications made
- Business justification
- SOD considerations
- Assigned users
- Review date

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **4. Regular Role Reviews**

**Review Frequency:**
- Quarterly: Active role assignments
- Annually: Role definitions
- After major changes: Role modifications

**Review Activities:**
- Verify users still need assigned roles
- Check for SOD conflicts
- Update role documentation
- Remove unused custom roles

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **5. Least Privilege Principle**

**Grant Only What's Needed:**
- Start with minimum access
- Add privileges as needed
- Remove unnecessary access
- Regular access reviews

**Example:**
```
User: AP Clerk
Need: Create invoices only

Assign: Accounts Payable Specialist
NOT: Accounts Payable Manager

Why: Specialist role has invoice creation without approval privileges
```

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


## **Complete Role Setup Examples**

### **Example 1: AP Department Setup**

**Organization:**
- 1 AP Manager
- 2 AP Supervisors
- 5 AP Clerks

**Role Assignments:**

**AP Manager:**
```
User: Jane Smith
Roles:
- Accounts Payable Manager
- Enterprise Resource Planning Self Service User

Data Access:
- Business Units: All AP business units
- Ledger: US Primary Ledger

Can:
- Create and approve invoices
- Process payments
- Manage suppliers
- Run all AP reports
- Approve team expenses
```

**AP Supervisors:**
```
Users: John Doe, Mary Johnson
Roles:
- Accounts Payable Supervisor
- Enterprise Resource Planning Self Service User

Data Access:
- Business Units: Assigned business units
- Ledger: US Primary Ledger

Can:
- Review invoices
- Approve payments
- Run AP reports
- Cannot create suppliers
```

**AP Clerks:**
```
Users: 5 clerks
Roles:
- Accounts Payable Specialist
- Enterprise Resource Planning Self Service User

Data Access:
- Business Units: Assigned business units
- Ledger: US Primary Ledger (Read-Only)

Can:
- Create invoices
- Enter expenses
- View accounting
- Cannot approve invoices
- Cannot process payments
```

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Example 2: GL Department Setup**

**Organization:**
- 1 Controller
- 2 Senior Accountants
- 3 Staff Accountants

**Role Assignments:**

**Controller:**
```
User: Controller
Roles:
- General Accounting Manager
- Accounts Payable Manager
- Accounts Receivable Manager
- Asset Accounting Manager

Data Access:
- All ledgers (Read-Write)
- All business units
- All asset books

Can:
- All GL, AP, AR, FA functions
- Close periods
- Manage ledgers
- Full reporting access
```

**Senior Accountants:**
```
Users: 2 senior accountants
Roles:
- General Accountant
- Custom Role: AP Invoice Reviewer (Read-Only)

Data Access:
- US Primary Ledger (Read-Write)
- AP Business Units (Read-Only)

Can:
- Create and post journals
- View AP invoices
- Run GL and AP reports
- Cannot approve invoices
- Cannot close periods
```

**Staff Accountants:**
```
Users: 3 staff accountants
Roles:
- General Accountant

Data Access:
- US Primary Ledger (Read-Write)
- Segment Value Security: Specific departments only

Can:
- Create journals for assigned departments
- View accounting
- Run reports
- Cannot post journals (requires approval)
- Cannot close periods
```

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Example 3: Multi-Module Finance Analyst**

**Requirement:**
Read-only access across all financial modules for analysis and reporting.

**Role Assignment:**
```
User: Financial Analyst
Roles:
- Financial Analyst
- BI Author Role (for creating custom reports)

Data Access:
- All ledgers (Read-Only)
- All business units (Read-Only)
- All asset books (Track and Report only)

Inherited Duty Roles:
- General Ledger Self Service Reporting Duty
- Payables Self Service Reporting Duty
- Receivables Self Service Reporting Duty
- Fixed Asset Self Service Reporting Duty
- All Transaction Analysis Duty roles
- BI Consumer Role
- BI Author Role

Can:
- View all financial data
- Run all reports
- Create custom OTBI reports
- Analyze trends
- Export data

Cannot:
- Create or modify transactions
- Post journals
- Approve invoices or payments
- Change setup data
```

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


## **Viewing Role Information**

### **Security Console**

**Access:** Navigator > Tools > Security Console

**Functions:**
- Search for roles
- View role hierarchy
- See inherited duty roles
- View privileges
- Export role details
- Copy roles
- Create custom roles

**Steps to View Role Details:**
1. Sign in with IT Security Manager role
2. Navigate to Security Console
3. Search for role name
4. View in tabular or graphical format
5. Expand to see inherited roles
6. Export to spreadsheet for analysis

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Security Reference Guides**

**Location:** Oracle Help Center (docs.oracle.com)

**Content:**
- Complete list of predefined roles
- Role descriptions
- Inherited duty roles
- Privileges included
- Data security policies

**Guides Available:**
- Oracle Fusion Cloud Financials Security Reference for General Ledger
- Oracle Fusion Cloud Financials Security Reference for Payables
- Oracle Fusion Cloud Financials Security Reference for Receivables
- Oracle Fusion Cloud Financials Security Reference for Assets

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


## **Key Takeaways**

1. **Job roles represent complete job functions** - Assign job roles to users, not individual privileges

2. **Duty roles are building blocks** - Job roles inherit multiple duty roles

3. **Use predefined roles when possible** - Oracle maintains and updates them

4. **Assign multiple roles per user** - Don't create one super-role with everything

5. **OTBI reporting requires both duty roles** - OBI version AND Financials version

6. **BI Consumer Role for viewing** - BI Author Role for creating reports

7. **SOD conflicts must be assessed** - Balance security with operational needs

8. **Custom roles for specific needs** - Copy predefined roles and modify

9. **Document custom roles** - Maintain clear documentation

10. **Regular role reviews** - Ensure users have appropriate access

11. **Least privilege principle** - Grant only what's needed

12. **Security Reference guides** - Use Oracle documentation for role details
