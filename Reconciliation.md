# Microsoft Dynamics GP – General Ledger & Bank Reconciliation Notes

## Overview
- Module: **Financial**
- Covers:
  - General Ledger (GL)
  - Journal Entries
  - Checkbooks (Bank Accounts)
  - Bank Reconciliation

---

## Setup (GL Fundamentals)

### Key Settings
- **Retained Earnings Account**
  - Used during year-end close
- **Divisional Close**
  - Can close to multiple retained earnings accounts by segment
- **Allow Posting to History**
  - Enables posting to closed years (recommended ON)
- **Maintain History**
  - Keep all historical transactions

### Reporting Ledgers
- Can enable multiple books:
  - Example: Local GAAP vs IFRS

### Account Categories
- Used for:
  - Financial statements
- Examples:
  - Cash
  - Expense
  - Revenue

### Segments (Chart of Accounts)
- Example structure:
  - Department | Account | Division
- Segments define account structure

---

## GL Accounts (Cards)

### Key Fields
- Account Number (multi-segment)
- Description (natural account name)
- Category (required)
- Posting Type:
  - **Balance Sheet**
  - **P&L (Income Statement)**

### Important Rules
- P&L accounts → close to retained earnings
- Balance sheet → roll forward

### Typical Balance
- Debit → cursor defaults to debit
- Credit → cursor defaults to credit

---

## Checkbooks (Bank Accounts)

### Concept
- Checkbook = **Bank Account in GP**

### Key Setup
- **Cash Account**
  - Should be **1:1 with bank account**
- Bank account number
- Default checkbook ID
- Optional:
  - Max check amount
  - Password protection

### EFT Setup
- Used for:
  - Electronic payments
- Requires:
  - Bank info
  - File format from bank

---

## Unit Accounts (Non-$ Tracking)
- Track **quantities, not dollars**
- Example:
  - Number of employees
  - Units sold

### Use Case
- Combine with financial data:
  - Example: salary ÷ employees = avg salary

---

## Allocation Accounts

### Fixed Allocation
- Splits amounts automatically by %
- Example:
  - Rent split across departments

### Variable Allocation
- Splits based on:
  - Unit accounts (e.g., employee count)

---

## Journal Entries (Core GL)

### Entry Path
`Financial → Transactions → General`

### Steps
1. Enter reference (description)
2. Enter accounts
3. Enter debit/credit
4. Save (adds to batch)

### Key Concepts
- Debits = Credits (must balance)
- Saving = not posted yet

---

## Batches
- Used for:
  - Grouping entries
  - Bulk posting

### Workflow
1. Create batch
2. Add entries
3. Close transaction window
4. Post batch

---

## Reversing Entries
- Used for:
  - Accruals

### Example
- Post today
- Reverse next period automatically

---

## Excel Copy/Paste (VERY IMPORTANT)
- Paste journal entries directly from Excel

### Format:
- Description | Account | Debit | Credit

### Benefits:
- Faster than manual entry
- Replaces templates/macros

---

## Bank Transactions (Cash Handling)

### Important Rule
- **NEVER hit cash via journal entry**
- Always use:
  - Bank transaction entry

### Types
- Cash disbursement (payments)
- Receipts (money in)

---

## Bank Deposits
- Combine multiple receipts into one deposit
- Matches:
  - Bank statement line

- Can be automated in settings

---

## Bank Transfers
- Move money between checkbooks

---

## Bank Reconciliation (CRITICAL)

### Purpose
- Match:
  - GP checkbook
  - Bank statement
  - GL cash account

### Steps
1. Enter ending balance
2. Mark cleared transactions
3. Add adjustments (fees, etc.)
4. Reconcile

### Goal
- Difference = **0**

### Reports
- Cleared transactions
- Outstanding transactions

---

## Inquiry (Finding Data)

### GL Inquiry
- Account summary
- Drill down to transactions

### Journal Entry Inquiry
- Search by JE number

### Checkbook Register
- View:
  - All bank activity
  - Filter by date/status

---

## Reports

### Trial Balance
- Summary → account totals
- Detail → every transaction

### Cross-Reference
- Reprint:
  - Journal entries
  - Batches

### Checkbook Reports
- Bank activity
- Reconciliation reports

---

## SmartList (Power Tool)
- Financial lists:
  - Accounts
  - Transactions
  - Bank activity

- Can:
  - Filter
  - Export to Excel
  - Customize views

---

## Reconcile to GL Tool (VERY IMPORTANT)

### Purpose
- Compare:
  - Subledger (A/R, A/P)
  - General Ledger

### Output
- Matched transactions
- Unmatched transactions

### Use Case
- Month-end tie-out

---

## Year-End Close (High Level)
- Closes P&L → retained earnings
- Balance sheet rolls forward

---

## Utilities (Fix Issues)

### Reconcile
- Fixes data mismatches

### Remove History
- Deletes old data
- Improves performance

---

## Key Workflow (Daily GL)

1. Enter journal entries
2. Save to batch
3. Post batch
4. Review reports
5. Reconcile cash regularly

---

## Mental Model

- Accounts = structure
- Journal entries = activity
- Checkbooks = cash
- Reconciliation = accuracy
- Reports = validation
