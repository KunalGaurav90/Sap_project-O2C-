# 📦 Order-to-Cash (O2C) — SAP SD Complete Sales Cycle
### KIIT University | SAP Project Work | Topic ii

---

## 🔍 Overview

This repository contains the complete **Order-to-Cash (O2C)** simulation project for the KIIT SAP Project Work assignment. The O2C cycle is an end-to-end business process in **SAP SD (Sales & Distribution)** that covers every step from a customer inquiry to cash receipt.

**Fictitious Company:** TechNova Solutions Pvt. Ltd.  
**Module:** SAP SD — Sales & Distribution  
**SAP Functional Areas:** SD + FI + MM Integration  

---

## 📁 Repository Contents

| File | Description |
|------|-------------|
| `O2C_Complete_Simulation.py` | ✅ Full Python simulation — runs in Google Colab |
| `O2C_Project_Report.docx` | 📄 Complete project report with customisation steps |
| `O2C_Project_Documentation.pdf` | 📋 Professional PDF documentation |
| `README.md` | 📖 This file |

---

## 🔄 O2C Process Flow

```
Customer Inquiry (VA11)
        ↓
Quotation (VA21)
        ↓
Sales Order (VA01)  ←── Credit Check + Availability Check
        ↓
Outbound Delivery (VL01N)
        ↓
Post Goods Issue — PGI (VL02N)  ←── Stock ↓ | COGS ↑
        ↓
Billing / Invoice (VF01)  ←── AR ↑ | Revenue ↑
        ↓
Payment Posting (F-28)  ←── Cash ↑ | AR ↓ = ZERO
        ✅ O2C Complete
```

---

## 💻 How to Run in Google Colab

### Option A — Upload & Execute
1. Open [Google Colab](https://colab.research.google.com)
2. Upload `O2C_Complete_Simulation.py` via the Files panel (📁 icon on the left)
3. In a code cell, run:
```python
!pip install tabulate
exec(open('O2C_Complete_Simulation.py').read())
```

### Option B — Copy & Paste
1. Open `O2C_Complete_Simulation.py`
2. Copy the entire content
3. Paste into a Colab code cell
4. Add `!pip install tabulate` as the first line
5. Run the cell

---

## 🗂️ What the Simulation Does

| Section | Feature | SAP Equivalent |
|---------|---------|---------------|
| 1 | Master Data Setup | Customer Master, Material Master |
| 2 | `create_inquiry()` | VA11 — Create Inquiry |
| 3 | `create_quotation()` | VA21 — Create Quotation |
| 4 | `create_sales_order()` | VA01 + Credit Check + Availability Check |
| 5 | `create_delivery()` | VL01N — Outbound Delivery |
| 6 | `post_goods_issue()` | VL02N — PGI (Movement Type 601) |
| 7 | `create_billing()` | VF01 — Invoice + Auto FI Posting |
| 8 | `post_payment()` | F-28 — Payment + AR Clearing |
| 9 | Document Flow Summary | VA03 / VF03 / FB03 |
| 10 | Financial Summary | Revenue, COGS, Profit, AR |
| 11 | Inventory Status | MB52 — Warehouse Stocks |

---

## 📊 Sample Output

```
══════════════════════════════════════════════════════════════
  SECTION 9: O2C DOCUMENT FLOW SUMMARY
══════════════════════════════════════════════════════════════

╒════════╤═══════════════════╤══════════════╤══════════╤═══════════════════════╕
│   Step │ Document Type     │ Doc Number   │ T-Code   │ Status                │
╞════════╪═══════════════════╪══════════════╪══════════╪═══════════════════════╡
│      1 │ Inquiry           │ INQ-10001    │ VA11     │ Completed             │
│      2 │ Quotation         │ QT-20001     │ VA21     │ Completed             │
│      3 │ Sales Order       │ SO-30001     │ VA01     │ Open                  │
│      4 │ Outbound Delivery │ DEL-40001    │ VL01N    │ Goods Issue Completed │
│      5 │ Material Document │ MAT-50001    │ VL02N    │ Posted                │
│      6 │ Billing Document  │ BILL-60001   │ VF01     │ Posted                │
│      7 │ FI AR Entry       │ FI-70001     │ FB03     │ Posted                │
│      8 │ Payment Doc       │ FI-70002     │ F-28     │ Cleared               │
╘════════╧═══════════════════╧══════════════╧══════════╧═══════════════════════╛
```

---

## 🏢 Organisational Setup

| SAP Element | Value | Description |
|-------------|-------|-------------|
| Company Code | TN01 | TechNova India |
| Sales Org | TN10 | TechNova Sales Org |
| Distribution Channel | 10 | Direct Sales |
| Division | 00 | Cross-Division |
| Plant | TN01 | Main Distribution Plant |
| Shipping Point | TN01 | Central Shipping Point |

---

## 💰 Financial Summary

| Description | Amount (INR) |
|-------------|-------------|
| Gross Revenue (10 units × ₹75,000) | ₹7,50,000 |
| Discount (5%) | -₹37,500 |
| Net Revenue | ₹7,12,500 |
| GST Output Tax (18%) | ₹1,28,250 |
| **Total Invoice Value** | **₹8,40,750** |
| Amount Received | ₹8,40,750 |
| Outstanding AR | ₹0 ✅ |

---

## 🛠️ Key SAP Transaction Codes

| T-Code | Description | Phase |
|--------|-------------|-------|
| VA11 | Create Inquiry | Pre-Sales |
| VA21 | Create Quotation | Pre-Sales |
| VA01 | Create Sales Order | Sales |
| VL01N | Create Outbound Delivery | Logistics |
| VL02N | Post Goods Issue (PGI) | Logistics |
| VF01 | Create Billing Document | Billing |
| FBL5N | Customer Line Items | Accounts Receivable |
| F-28 | Post Incoming Payment | Payment |

---

## 📚 References

- SAP Help Portal: [help.sap.com](https://help.sap.com)
- KIIT SAP Project Work Guidance Document
- SAP SD Certification Guide — C_TSCM62
- SAP Community: [community.sap.com](https://community.sap.com)

---

*KIIT University | SAP Project Work | Order-to-Cash (O2C) | SAP SD*
