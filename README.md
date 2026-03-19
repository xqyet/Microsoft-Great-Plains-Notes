# Microsoft Dynamics GP (Great Plains) – A/R Navigation Notes

## Navigation Basics
- **Modules = Work Areas**
  - Financial → GL, bank rec
  - Sales → A/R (customers, invoices, cash receipts)
  - Purchasing → AP/vendors

- **Sections in each module:**
  - **Cards** → Master data (customers, vendors, accounts)
  - **Transactions** → Enter/process data (invoices, payments)
  - **Inquiry** → Look up ONE record
  - **Reports** → Run reports (trial balance, aging)
  - **Routines** → Month-end processes
  - **Utilities** → Admin/reconcile tools

---

## Customer / Master Data (Cards)
- Cards = Customer records (core of A/R)
- Use **lookup (Ctrl + L)** to find customers quickly
- Can **custom sort** lookup (e.g., ZIP, name, etc.)

---

## A/R Transactions
- Enter invoices, payments, adjustments:
  - `Sales → Transactions`
- Journal-style entry:
  - Debit = receivable
  - Credit = revenue/cash
- **Tip:** Enter a **negative amount** to flip debit/credit automatically

---

## Inquiry (for finding invoice/vendor/etc)
- Use when you know the **exact item** (customer, invoice, JE)
- Shows:
  - Activity
  - Balances
  - Transaction history

- **Drill-down links:**
  - Click links to trace:
    - GL → invoice → original transaction

---

## Reports (A/R)
- Common A/R reports:
  - Aging reports
  - Customer balances
  - Sales transactions

- Steps:
  1. Select report
  2. Set filters (**click Insert to apply**)
  3. Choose output:
     - Screen
     - Printer
     - PDF

- Can **save report setups** for reuse

---

## SmartList (Pulling & Exporting)
- Used to:
  - Pull customer balances
  - Find overdue invoices
  - Export to Excel

- Can create:
  - Custom favorites
  - Filters

- Best tool for:
  - Daily A/R analysis

---

## Reminders / Queues
- Based on SmartList results
- Example:
  - Show alert if overdue invoices > 0
- Clicking reminder → opens report directly

---

## Batches
- Transactions grouped into **batches**
- Can set **recurring batches:**
  - Auto-create entries monthly
  - Dates auto-update

- Used for:
  - Recurring invoices
  - Adjustments

---

## Batch Recovery (ERROR FIX)
- Happens when posting fails (e.g., closed period)
- Fix issue FIRST, then:
  - Click **Continue** → posts correctly

- If not fixed:
  - Returns to original module

---

## Keyboard Shortcuts 
| Shortcut     | Action                          |
|--------------|---------------------------------|
| Ctrl + L     | Lookup                          |
| Ctrl + W     | Close window                    |
| Tab          | Move forward                    |
| Shift + Tab  | Move backward                   |
| Ctrl + C     | Copy                            |
| Ctrl + V     | Paste                           |
| F1           | Help for current window         |

---

## Excel Integration 
- Can **paste journal entries directly from Excel**

- Format:
  - Description | Account | Debit | Credit

- Faster than manual entry

---

## Macros 
- Record repetitive steps
- Example:
  - Auto-fill accounts + amounts

- Assign shortcut key (e.g., F3)

- Using for:
  - Recurring A/R tasks
  - Standard entries

---

## Personal Setup Notes
- Customize:
  - Colors (highlight required fields)
  - Enter key behavior (tabbing)
  - Toolbar layout

- Can set default transaction window (e.g., invoices)

---

## Additional Productivity Notes
- Use **SmartList** instead of manual searching
- Always **drill down** for details
- Use **Excel paste** for bulk entries
- Set up:
  - Reminders for overdue invoices
  - Recurring batches

- Keep hands on keyboard for speed

---

## Summary Model
- Cards = who
- Transactions = what happened
- Inquiry = look up one
- Reports / SmartList = analyze many
