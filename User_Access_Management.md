# User Access Management

## **What Is It?**

User access management is the process of creating user accounts, assigning job roles, granting data access, and managing user privileges throughout their lifecycle in Oracle Fusion Financials. It controls WHO can access the system and WHAT they can do.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


## **Key Components**

### **1. User Account Creation**
The foundation of access management - creating user identities in the system.

### **2. Role Assignment**
Assigning job roles and duty roles that grant functional privileges.

### **3. Data Access Assignment**
Granting access to specific data contexts (ledgers, business units, asset books).

### **4. Access Review and Maintenance**
Ongoing monitoring, updates, and removal of access.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


## **User Provisioning Process**

### **Step 1: Create User Account**

User accounts are created through:
- **HCM Processes**: New hire, transfer, promotion automatically trigger user creation
- **Manual Creation**: IT Security Manager creates user manually
- **Identity Management**: Oracle Identity Management (OIM) manages user identities

Key User Attributes:
- Username
- Email address
- Employee assignment (if applicable)
- Effective start and end dates
- Primary job and department

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Step 2: Assign Job Roles**

Use **Security Console** to assign roles:

Navigation: Tools > Security Console

Actions:
- Search for user
- Add job roles
- Set effective dates
- Review role hierarchy

Role Assignment Rules:
- Assign multiple roles based on responsibilities
- Don't create one role with all accesses
- Use predefined roles when possible
- Create custom roles only when necessary

Example:
```
User: John Smith
Job Roles:
  - Accounts Payable Specialist
  - Expense Report Approver
  - Enterprise Resource Planning Self Service User (Abstract Role)
```

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Step 3: Assign Data Access**

Use **Manage Data Access for Users** task:

Navigation: Setup and Maintenance > Search: "Manage Data Access for Users"

Data Access Types by Module:

| Module | Security Context | What It Controls |
|--------|------------------|------------------|
| General Ledger | Data Access Set | Which ledgers user can access |
| Payables | Business Unit | Which business units for AP transactions |
| Receivables | Business Unit | Which business units for AR transactions |
| Assets | Asset Book | Which asset books user can access |
| Subledger Accounting | Ledger | Which ledgers for subledger accounting |

Access Levels:
- **Read-Write**: Create, update, and view transactions
- **Read-Only**: View and report only, cannot modify

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Step 4: Assign Segment Value Security (Optional)**

If chart of accounts segments are secured:

Use **Manage Segment Value Security Rules** spreadsheet:

1. Create segment value security role
2. Define policies for account value access
3. Assign policies to the role
4. Assign role to users with rule assignments

Rule Assignment Attributes:
- User Name
- Policy Name
- Business Function (GL, AP, AR, FA)
- Security Context (Data Access Set, Business Unit, Asset Book)
- Security Context Value (specific ledger, BU, or book)
- Access Level (Read-Write or Read-Only)

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


## **Security Role Provisioning**

### **Automatic Provisioning**

Roles are automatically provisioned based on:
- Employee assignment
- Job changes (promotion, transfer)
- Department changes
- Termination (automatic de-provisioning)

HCM processes trigger identity management and access provisioning automatically.

### **Manual Provisioning**

IT Security Manager manually assigns roles through:
- Security Console
- Delegated Administration (for specific business areas)

Example: Sales line manager approves access to sales roles instead of IT Security Manager.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


## **Data Access Assignment Details**

### **General Ledger - Data Access Sets**

Task: **Manage Data Access Set Data Access for Users**

What You Assign:
- Specific ledgers or ledger sets
- Access level (Read-Only or Read-Write)
- Primary balancing segment values (optional)

Example:
```
User: Sarah Johnson
Role: General Accounting Manager
Data Access Set: US Operations
  - US Primary Ledger (Read-Write)
  - US Reporting Ledger (Read-Only)
```

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Payables and Receivables - Business Units**

Task: **Manage Data Access for Users**

What You Assign:
- Business units for transaction processing
- Access level per business unit

Example:
```
User: Mike Chen
Role: Accounts Payable Specialist
Business Units:
  - US East BU (Read-Write)
  - US West BU (Read-Write)
  - Canada BU (Read-Only)
```

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **Assets - Asset Books**

Task: **Manage Data Access for Users**

What You Assign:
- Asset books
- Data privileges per book

Data Privileges:
- Add Fixed Asset Data
- Change Fixed Asset Data
- Retire Fixed Asset Data
- Track Fixed Asset Data
- Submit Fixed Assets Reports

Example:
```
User: Lisa Wong
Role: Asset Accountant
Asset Books:
  - Corporate Asset Book (All privileges)
  - Leased Assets Book (Track and Report only)
```

Default Asset Book:
- Set using **Default Book** profile option
- Automatically populated in transactions
- Can be overridden by user

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


## **Access Review and Maintenance**

### **Regular Access Reviews**

Frequency: Quarterly or as per company policy

Review Activities:
- Verify users still need assigned roles
- Remove access for terminated employees
- Update roles for job changes
- Identify and remediate SOD conflicts
- Review unused accounts

Tools:
- User and Role Audit Report
- Security Console
- Access certification workflows

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


### **User Lifecycle Management**

| Event | Action Required |
|-------|-----------------|
| New Hire | Create user, assign roles, grant data access |
| Promotion | Update roles, expand data access |
| Transfer | Change department, update business unit access |
| Leave of Absence | Suspend account (set end date) |
| Termination | Remove all roles, end-date account |
| Contractor End | Remove access, deactivate account |

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


## **Complete User Setup Example**

### **Scenario: New Accounts Payable Clerk**

**User Details:**
- Name: Alex Martinez
- Department: Finance - Accounts Payable
- Location: US East Office
- Start Date: January 1, 2025

**Step-by-Step Setup:**

**1. Create User Account**
- Username: AMARTINEZ
- Email: alex.martinez@company.com
- Employee: Yes
- Effective Date: 01-JAN-2025

**2. Assign Job Roles (Security Console)**
- Accounts Payable Specialist
- Enterprise Resource Planning Self Service User
- Employee (Abstract Role)

**3. Assign Data Access (Manage Data Access for Users)**

Business Units:
- US East BU (Read-Write)
- US Central BU (Read-Write)

Ledgers (via Data Access Set):
- US Primary Ledger (Read-Write)

**4. Assign Segment Value Security (if applicable)**

Policy: AP Clerk Company Access
- Companies: 100, 200 (Read-Write)
- Business Function: Payables
- Security Context: Business Unit
- Security Context Value: US East BU, US Central BU

**Result:**
Alex can:
- Create and approve invoices in US East and Central BUs
- Process payments for companies 100 and 200
- View accounting in US Primary Ledger
- Submit expense reports
- Access self-service functions

Alex cannot:
- Access other business units
- Create journals in General Ledger
- Access other company values
- Modify setup data

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


## **Key Roles for User Management**

| Role | Purpose | Key Tasks |
|------|---------|-----------|
| IT Security Manager | Manage all users and roles | Create users, assign roles, security console access |
| Application Implementation Consultant | Setup during implementation | Access all setup tasks |
| Financial Application Administrator | Ongoing setup management | Manage financial setup data |
| Line Manager | Approve team access | Delegated approval for team roles |

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


## **Best Practices**

### **1. Role Assignment**
- Use predefined roles whenever possible
- Assign multiple specific roles instead of one super-role
- Document custom roles and their purpose
- Review role assignments regularly

### **2. Data Access**
- Follow least privilege principle
- Grant only necessary data access
- Use Read-Only access for inquiry users
- Document data access decisions

### **3. Segregation of Duties**
- Separate creation and approval functions
- Separate processing and reconciliation
- Monitor SOD conflicts
- Document approved exceptions

### **4. Access Governance**
- Implement regular access reviews
- Automate provisioning where possible
- Use effective dates for temporary access
- Maintain audit trail of changes

### **5. Documentation**
- Document role assignment rationale
- Maintain user access matrix
- Record data access grants
- Keep termination checklists

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


## **Common Scenarios**

### **Scenario 1: Multi-Module User**

User needs access to both AP and AR:

```
User: Jane Doe
Roles:
  - Accounts Payable Specialist
  - Accounts Receivable Specialist
  
Data Access:
  - AP Business Units: US East, US West
  - AR Business Units: US East, US West
  - Ledger: US Primary Ledger
```

### **Scenario 2: Read-Only Auditor**

User needs view-only access across all modules:

```
User: Audit Team Member
Roles:
  - Financial Analyst (Read-Only)
  
Data Access:
  - All Ledgers (Read-Only)
  - All Business Units (Read-Only)
  - All Asset Books (Track and Report only)
```

### **Scenario 3: Regional Manager**

User needs full access to specific region:

```
User: EMEA Finance Manager
Roles:
  - General Accounting Manager
  - Accounts Payable Manager
  - Accounts Receivable Manager
  
Data Access:
  - EMEA Ledger (Read-Write)
  - EMEA Business Units (Read-Write)
  - EMEA Asset Book (All privileges)
  
Segment Value Security:
  - Companies: 300-399 (EMEA region)
```

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


## **Troubleshooting Access Issues**

### **User Can't See Expected Data**

Check:
1. Job role assigned?
2. Data access granted for security context?
3. Segment value security rules assigned?
4. Effective dates valid?
5. Profile options set correctly?

### **User Can't Perform Action**

Check:
1. Role has required duty roles?
2. Access level is Read-Write (not Read-Only)?
3. No SOD restrictions blocking action?
4. Business unit/ledger accessible?

### **User Sees "No Access" Error**

Check:
1. Data access set assigned?
2. Business unit access granted?
3. Segment value security blocking access?
4. Security context matches transaction?

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


## **Key Takeaways**

1. **User access management is a three-layer process**: User creation → Role assignment → Data access assignment

2. **Use Security Console** for role assignments and **Manage Data Access for Users** for data access

3. **Different modules use different security contexts**: GL uses Data Access Sets, AP/AR use Business Units, FA uses Asset Books

4. **Assign multiple specific roles** instead of creating one role with all privileges

5. **Regular access reviews** are essential for maintaining security and compliance

6. **Effective dates** control when access is active - use them for temporary access

7. **Document everything** - role assignments, data access grants, and exceptions

8. **Automate where possible** - leverage HCM integration for provisioning
