# Automated Financial Compliance & Reconciliation Dashboard

## 📖 Overview

This project automates financial reconciliation and compliance monitoring by combining Python, SQL, and Power BI into a unified solution. It enables finance teams to detect anomalies, track compliance risks, and visualize reconciliation coverage in real-time.

## The pipeline:
- Matches Accounts Payable (AP) invoices with General Ledger (GL) postings.
- Flags unmatched invoices, tax mismatches, and missing approvals.
- Stores results in MySQL and visualizes insights in Power BI dashboards.

## ⚙️ Tech Stack
- Python (Pandas, NumPy, SQLAlchemy) → Reconciliation, compliance checks, and data pipelines.
- MySQL (SQL queries) → Coverage metrics and compliance summaries.
- Power BI → Interactive dashboards for finance and audit teams.

## 🏗 Workflow
### 🔹 Step 1: Reconciliation (Python)
- Exact Match → AP invoice ID = GL reference invoice ID.
- Amount Tolerance Match → Matches within 0.5% tolerance.
- Fuzzy Match → Vendor, date window (±7 days), and small amount difference.
- Produces reconciled_results.csv + MySQL table.

### 🔹 Step 2: Exception Handling

- Identifies unmatched invoices (exceptions).
- Produces exceptions.csv + MySQL table.

### 🔹 Step 3: Compliance Checks

- Tax Mismatch → Compares recorded vs. computed tax.
- Missing Approval → Flags high-value invoices without approval.
- Produces compliance_issues.csv + MySQL table.

###🔹 Step 4: Analytics (SQL Queries)

- Reconciliation Coverage % by month.
- Compliance issues grouped by type.

###🔹 Step 5: Visualization (Power BI)

- Executive Summary → Reconciliation % trends, issue counts.
- Invoice Audit & Risk Insights → Exceptions by type/severity, compliance issue tables.


