# Microsoft Dynamics GP – Receivables (A/R) Notes

## Receivables Overview
- Core A/R module = **Sales → Receivables**
- Covers:
  - Customers
  - Invoices
  - Cash receipts
  - Aging
  - Statements

---

## Setup (Important Early Config)

### Aging Setup
- Define aging buckets (e.g., 0–30, 31–60, etc.)
- Two methods:
  - **Due Date Aging (common)** → based on payment terms
  - **Document Date Aging** → based on invoice date

### Key Settings
- Password protection:
  - Credit limit overrides
  - Write-offs
  - Finance charge removal
- Enable:
  - Reprint statements
  - Credit limit warnings (red indicator)
- Default values:
  - Checkbook (cash receipts)
  - Price level
  - Tax schedule

### Document Numbering
- Can customize numbering formats
- Defaults are usually fine

### User-Defined Fields
- Add custom fields like:
  - Customer type
  - Region

---

## Classes 
- Used to:
  - Speed up customer setup
  - Standardize defaults

- Example:
  - Default A/R account
  - Default checkbook
  - Default terms

- When assigning a class → values auto-fill

---

## Customer Setup (Cards)

### Key Fields
- **Customer ID**
- **Statement Name** (what appears on statements)
- **Addresses:**
  - Bill-to
  - Ship-to (multiple allowed)

### Additional Setup
- Salesperson + territory (for commissions)
- Payment terms
- Credit limit
- Finance charge %

### Tax Behavior
- Based on:
  - Shipping method
  - Customer location

- Example:
  - Pickup → tax based on your location
  - Delivery → tax based on customer location

### Accounts (GL Defaults)
- A/R account
- Revenue accounts
- Default checkbook

### Email Setup
- Enables:
  - Sending invoices via email
  - Word template documents

---

## National Accounts (Parent/Child Customers)
- Group customers under one parent
- Benefits:
  - Combined reporting
  - Apply payments across multiple customers

---

## A/R Transactions

### Sales Invoice Entry
Path: `Sales → Transactions → Transaction Entry`

Steps:
1. Select type:
   - Invoice
   - Debit memo
   - Credit memo
2. Enter:
   - Customer ID
   - Document date
   - Amounts (sales, discounts, freight, tax)
3. Review distributions
4. Save to batch or post

### Key Notes
- Document date affects aging
- Sales tax auto-calculates based on setup
- Distributions pull from:
  - Customer setup → fallback to company setup

---

## Batches (Posting Control)
- Group multiple transactions
- Benefits:
  - Control totals
  - Bulk posting

### Controls
- Number of transactions
- Batch total amount

---

## Posting
- Post from:
  - Transaction window
  - Batch window

- Posting generates:
  - Receivables Posting Journal
  - GL impact

---

## Cash Receipts (Payments)

### Entry
Path: `Sales → Transactions → Cash Receipts`

Steps:
1. Select customer
2. Enter payment amount
3. Choose payment type (cash/check)
4. Select checkbook
5. Open **Apply window**

### Applying Payments
- Match payment to invoices
- Can:
  - Fully apply
  - Partially apply
  - Write off small balances

### Write-Offs
- Limited by customer settings
- Done during apply process

### Key Tip
- **Apply Date affects aging reports**

---

## Apply Sales Documents
- Used to:
  - Apply credit memos to invoices
- Helpful for:
  - Cleaning up A/R balances

---

## Inquiry (Lookup & Drilldown)

### Use Cases
- View:
  - Customer activity
  - Specific invoices
  - Transaction history

### Features
- Drill-down to source transactions
- Filter by:
  - Date
  - Status
  - Amount

### Summary Views
- Snapshot of:
  - Balances
  - Payment history
  - Average days to pay

---

## Routines (Monthly / Period-End Tasks)

### Aging 
- Must run manually
- Updates aging buckets

### Finance Charges
- Applies % to overdue balances
- Creates new transactions

### Statements
- Generate customer statements
- Options:
  - Include credit limits
  - Include finance charges

### Write-Off Process
- Automatically clears small balances

### Paid Transaction Removal
- Moves fully paid items:
  - Open → History
- Improves system performance

---

## Reports (A/R Focus)

### Aging Reports
- Current aging (real-time)
- Historical aging (as of past date)

### Transaction Reports
- Customer transaction history
- Invoice listings

### Posting Journals
- Detailed GL impact
- Can reprint anytime

### Commissions
- Based on salesperson assigned to invoices

---

## SmartList (Power Tool)
- Best tool for:
  - Exporting A/R data
  - Custom reports

- Key Lists:
  - Receivables transactions
  - Customers

---

## Utilities (Use Carefully)

### Reconcile
- Fixes data inconsistencies

### Remove History
- Deletes old data (admin use only)

---

## Key Workflow (Daily A/R)

1. Enter invoices
2. Post batches
3. Receive payments
4. Apply payments
5. Run aging
6. Review reports / SmartList

---

## Mental Model

- Customers = who owes money
- Invoices = what they owe
- Cash receipts = payments
- Aging = how late they are
- Reports = what management sees
