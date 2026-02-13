# Trade Settlement Exception & Break Management System  
**Automated Post-Trade Reconciliation for Asset Managers (SQL & Python)**

---

## Overview

Settlement failures represent a persistent and material cost to asset managers operating in Fund Administration. Despite mature front-office trading platforms, post-trade settlement reconciliation remains heavily manual, spreadsheet-driven, and reactive—resulting in avoidable penalties, interest duplication, and elevated operational risk.

This project implements a **Trade Settlement Exception & Break Management System** using **SQL and Python** to automate reconciliation, identify settlement breaks earlier in the lifecycle, and quantify financial exposure with full audit traceability.

The solution is explicitly modelled on real operating environments at **Old Mutual**, **Sanlam**, and **Futuregrowth Asset Managers**, which I actively service in my professional role as a **Senior Fund Administrator at SS&C **.


---

## Professional Context

I am a **Senior Fund Administrator at SS&C Technologies**, supporting institutional asset managers across the full post-trade lifecycle, including:

- Trade settlement and reconciliation  
- Custodian confirmations  
- Cash and interest movements  
- Break investigation and resolution  
- Operational and client reporting  

This project reflects **real production workflows, data structures, and control requirements** encountered daily in South African asset-management operations.

---

## Business Problem

Across large asset managers:

- Trade, custodian, and cash data resides in siloed systems  
- Reconciliation is performed end-of-day using Excel  
- Settlement breaks are identified after settlement date  
- Penalty exposure is not systematically quantified  
- Manual logs are difficult to audit and trend  

These issues lead to:
- Higher settlement fail rates  
- Increased penalties and interest claims  
- Excessive operational effort  
- Control and audit risk  

---

## Project Objectives

- Centralise trade, confirmation, and cash settlement data  
- Automate daily post-trade reconciliation  
- Identify and categorise settlement breaks earlier  
- Quantify potential penalty and interest exposure  
- Improve STP rates, efficiency, and audit readiness  

---

## Solution Architecture

### 1. SQL Data Layer
A structured relational database storing:
- Trades  
- Custodian confirmations  
- Cash settlement movements  
- Reconciliation status history  

Designed for **high-volume reconciliation, performance, and auditability**.

### 2. Python Reconciliation Engine
A scheduled Python process that:
- Extracts data from SQL  
- Performs deterministic matching  
- Flags settlement breaks  
- Produces operational and management reports  

---

## Data Model (Core Tables)

### Trades
- Trade ID  
- ISIN  
- Trade Date  
- Settlement Date  
- Quantity  
- Price  
- Counterparty  

### Custodian Confirmations
- Confirmation ID  
- Trade Reference  
- Confirmed Quantity  
- Confirmed Amount  
- Settlement Date  

### Cash Movements
- Cash Reference  
- Amount  
- Value Date  
- Currency  

---

## Settlement Break Categories

- Amount mismatches  
- Quantity mismatches  
- ISIN/security discrepancies  
- Settlement date differences  
- Missing confirmations  
- Missing or duplicated cash movements  

---

## Key SQL Skills Demonstrated

- Multi-table joins on high-volume datasets  
- Window functions for latest trade state  
- Indexing strategies for reconciliation performance  
- Aggregation and exception logic  

---

## Key Python Skills Demonstrated

- Pandas-based reconciliation logic  
- Exception classification and prioritisation  
- Automated CSV / Excel reporting  
- Batch scheduling for daily operations  

---

## Operational & Financial Impact

| Metric | Manual Process | Automated System | Improvement |
|------|---------------|------------------|-------------|
| Daily reconciliation effort | ~3 hours | ~15 minutes | >90% |
| Break detection | Post-settlement | Intraday / T+1 | 24–48h faster |
| Settlement fail rate (sample) | ~2.1% | ~1.5% (proj.) | –29% |
| Annual penalty exposure | ~ZAR 2.1m | ~ZAR 1.5m | –ZAR 600k |

*Figures illustrative; results depend on portfolio size and volumes.*

---

## Repository Structure
trade-settlement-exception-management/
├── sql/
│ ├── schema.sql
│ ├── sample_data.sql
│ └── reconciliation_queries.sql
│
├── python/
│ ├── reconciliation_engine.py
│ ├── exception_report.py
│ ├── config.py
│ └── utils.py
│
├── data/
├── diagrams/
│ └── ERD.png
│
├── reports/
│ └── sample_exception_report.xlsx
│
├── docs/
│ └── architecture.md
│
└── README.md



---

## Project Scope

### In Scope
- Domestic equities, bonds, and money-market instruments  
- Trade execution feeds, custodian confirmations, cash movements  
- Automated reconciliation and exception classification  
- Penalty and interest exposure estimation  
- Audit-ready reconciliation logs  

### Out of Scope (Initial Phase)
- Trade execution or order management  
- Regulatory reporting submissions  
- Client-facing portals  
- Real-time market data feeds  

---

## Implementation Roadmap

**Phase 1 – Proof of Value (4 weeks)**  
- Deploy on a single fund or portfolio  
- Run in parallel with manual process  
- Deliver daily exception reports and impact analysis  

**Phase 2 – Production Pilot (6 weeks)**  
- Integrate with live feeds  
- Automate report distribution  
- Calibrate penalty logic  

**Phase 3 – Enterprise Rollout**  
- Scale across domestic portfolios  
- Knowledge transfer to internal teams  
- Extend to derivatives and corporate actions  

---

## Why This Matters

Settlement efficiency is no longer a back-office concern—it is a **competitive differentiator**. This system enables:

- Lower operational cost  
- Stronger controls and audit readiness  
- Improved client transparency  
- Faster, data-driven decision-making  

---

## About the Author

**Simiso A Manatha**  
Senior Fund Administrator – SS&C Technologies  

I service the trade operations of South Africa’s leading asset managers, including **Old Mutual**, **Sanlam**, and **Futuregrowth Asset Management**. I combine deep hands-on operational expertise with strong technical capability in SQL, Python, and analytics to deliver practical, high-impact improvements in production environments.

**LinkedIn:** [https://www.linkedin.com/in/simiso-manatha-08766260/)]  
**GitHub:** [C:\Users\SMANATHA\Documents\GitHub\trade-settlement-exception-management]

---

## Disclaimer

All data used in this repository is **synthetic or anonymised**. No client-confidential or proprietary information is included.
