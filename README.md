# Tally-Automation
Google Sheet to Tally Automation Using AI
Here is a **clean, professional GitHub project story** based on your uploaded workflow (Google Sheets → n8n → Tally automation). You can use it in your **GitHub README** or project description.

---

# Google Sheets to Tally Automation (n8n Workflow)

## Project Story

In many organizations, accounting teams spend hours manually entering vouchers into Tally from spreadsheets or ERP exports. This repetitive work is not only slow but also highly prone to human error.

While working on MIS and automation tasks, I faced the same challenge:
**Financial transactions were maintained in Google Sheets, but every entry had to be manually posted into Tally.**

To solve this problem, I designed an **end-to-end automation pipeline using n8n** that directly converts spreadsheet transactions into Tally vouchers.

This project demonstrates how modern workflow automation tools can integrate with legacy accounting systems like **Tally ERP** without modifying the core software.

---

# What This Automation Does

This workflow automatically:

1. **Reads transaction data from Google Sheets**
2. **Filters only unposted records**
3. **Validates voucher type (Receipt / Payment / Contra)**
4. **Converts JSON data into Tally-compatible XML**
5. **Posts the voucher to Tally using HTTP API**
6. **Parses the Tally response**
7. **Updates the Google Sheet with the posting status**

The result is a **fully automated accounting entry system**.

---

# Workflow Architecture

Google Sheets → n8n → XML Converter → Tally API → Response Parser → Status Update

### Key Workflow Nodes

* **Google Sheets Node**
  Reads financial transaction data.

* **Filter Node**
  Selects only rows that have not yet been posted.

* **Voucher Validation Node**
  Ensures only supported voucher types are processed.

* **Code Node (JSON → XML)**
  Dynamically generates Tally voucher XML.

* **HTTP Request Node**
  Sends voucher data to Tally.

* **Response Parser Node**
  Extracts voucher ID and status from Tally response.

* **Google Sheets Update Node**
  Writes posting status back to the spreadsheet.

---

# Features

✔ Automated voucher creation in Tally
✔ Supports **Receipt, Payment, and Contra vouchers**
✔ Handles **multiple ledger entries**
✔ Supports **bill allocations** (New Ref / Against Ref / On Account)
✔ Automatic **date formatting for Tally (YYYYMMDD)**
✔ Error detection and reporting
✔ Prevents duplicate posting
✔ Updates posting status in Google Sheets

---

# Advanced Logic Implemented

### Bill Allocation Handling

The workflow intelligently handles multiple bill allocations such as:

* New Reference
* Against Reference
* On Account adjustments

### Ledger Amount Balancing

The system automatically balances ledger entries according to voucher type rules.

### Data Validation

The automation validates:

* Voucher type
* Amount structure
* Bill allocation totals
* Date formats

This ensures **Tally receives valid XML every time**.

---

# Technology Stack

* **n8n** – Workflow automation
* **Google Sheets API** – Data source
* **JavaScript (n8n Code Node)** – Data transformation
* **Tally XML Gateway** – Voucher posting
* **HTTP API Integration**

---

# Example Use Cases

This automation can be used for:

* ERP to Tally integration
* Bank receipt automation
* Vendor payment posting
* Bulk accounting entries
* MIS system integrations

---

# Impact

This automation reduces:

* Manual voucher entry
* Data entry errors
* Accounting processing time

A task that previously took **hours of manual work can now be completed automatically in minutes.





