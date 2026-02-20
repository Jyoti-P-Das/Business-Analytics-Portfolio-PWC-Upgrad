# 🏠 Home Loan Sanction & Recovery Dashboard — Power BI

**Program:** Professional Certificate in Business Analytics & Consulting — upGrad × PwC Academy  
**Domain:** Banking & Financial Services  
**Tool:** Microsoft Power BI

---

## 🎯 Project Objective

Design and build an enterprise-grade Power BI dashboard to monitor a bank's home loan portfolio — providing real-time visibility into loan sanctions, disbursements, and recovery performance across branches, products, channels, and time periods. The project required constructing a multi-table star schema data model from scratch and developing DAX measures to power dynamic KPI reporting.

This project was part of the **Power BI module** within the upGrad × PwC Academy program — developed to replicate the kind of financial reporting and BI dashboard work delivered within PwC's financial services and analytics advisory practice.

---

## 💼 Business Problem

The bank's leadership and branch managers needed a centralised, filterable reporting solution to answer:
- How much has been sanctioned, disbursed, and recovered — by branch, channel, product, and time period?
- Which branches and channels are performing above or below portfolio benchmarks?
- Where is delinquency concentrated, and which customer segments represent the highest repayment risk?
- How do disbursement and recovery trends evolve month-on-month?

The business was relying on disconnected Excel reports that couldn't be filtered in real time or aggregated across dimensions. The Power BI dashboard replaced that with a single source of truth for loan portfolio monitoring.

---

## 📂 Dataset

**Source:** Home Loan Dataset (educational dataset used within the upGrad × PwC program for financial BI training — representative of banking loan portfolio data structures)

**Data Model — Star Schema:**

| Table | Type | Key Fields |
|---|---|---|
| **Customer** | Fact/Bridge | Customer Number, Branch Code, Channel Id, Product Id, Month Year, Applied Loan Amount in Lacs |
| **Sanction Data** | Fact | Customer Number, Month Year, Applied Loan Amount in Lacs, Sanction Amt in Lacs, Disb Amt in Lacs |
| **Recovery Data** | Fact | Customer Number, Month Year, Recovery Amount, Delinquency Months |
| **Branch** | Dimension | Branch Code, Branch Name, Branch Latitude, Branch Longitude, Branch Pincode |
| **Product** | Dimension | Product Id, Products |
| **Channel** | Dimension | Channel Id, Channels |
| **Dates** | Dimension | Month Year (calendar table for time intelligence) |

**Model Architecture:**

```
    Branch ──────────────────────────────────┐
    Product ─────────────────────────────────┤
    Channel ─────────────────────────────────┼──── Customer (Central Hub)
    Dates ───────────────────────────────────┤          │
                                             │    ┌─────┴─────┐
                                       Recovery  Sanction
                                         Data      Data
```

All dimension tables connect to `Customer` via one-to-many relationships. `Customer` bridges to fact tables via Customer Number + Month Year composite keys, creating a clean star schema optimised for cross-filter performance.

> Dataset is an upGrad × PwC Academy educational resource. The `.pbix` file in this folder contains the complete data model, all DAX measures, and the finished dashboard.

---

## 🔧 Data Model & DAX Implementation

### Relationships Configured
- One-to-many: Branch → Customer, Product → Customer, Channel → Customer, Dates → Customer
- Customer bridges to Sanction Data and Recovery Data via Customer Number + Month Year
- Cross-filter directions set for optimal slicer performance across all visuals

### DAX Measures Built

```dax
Total Sanction Amount = SUM('Sanction Data'[Sanction Amt in Lacs])

Total Disbursed Amount = SUM('Sanction Data'[Disb Amt in Lacs])

Total Recovery = SUM('Recovery Data'[Recovery Amount])

Recovery Rate % = DIVIDE([Total Recovery], [Total Disbursed Amount], 0)

Disbursal Ratio = DIVIDE([Total Disbursed Amount], [Total Sanction Amount], 0)

Applied Loan > 10 [Calculated Column] = 
    IF('Customer'[Applied Loan Amount in Lacs] > 10, "High Value", "Standard")
```

Time intelligence measures for Month-on-Month variance and cumulative YTD tracking were also implemented using the Dates dimension table.

---

## 📊 Dashboard Features

### KPI Cards
- Total Applied Loan Amount (Lacs)
- Total Sanctioned Amount (Lacs)
- Total Disbursed Amount (Lacs)
- Total Recovery Amount (Lacs)
- Sanction-to-Disbursal Ratio
- Recovery Rate (%)

### Visualisations
- **Branch performance** — bar chart comparing sanctions vs disbursals by branch, with branch-level targets
- **Channel contribution** — breakdown of loan volume across sales channels (direct, broker, digital)
- **Product mix** — loan volume and value by product type
- **Monthly trend line** — sanctions and recovery over time using Dates dimension
- **Delinquency analysis** — customers segmented by Delinquency Months to flag at-risk accounts
- **Geographic map** — branch locations plotted using Branch Latitude / Branch Longitude fields

### Interactive Filters (Slicers)
- Month-Year period slicer
- Branch selector
- Channel selector
- Product selector
- High-value loan filter (Applied Loan > 10 Lacs)

---

## 📈 Insights the Dashboard Surfaces

- Branches in specific regions consistently outperform on recovery rate relative to the portfolio average — identified without manual cross-referencing
- Digital and direct channels show higher sanction-to-disbursal conversion than broker-led originations
- Delinquency concentration visible in specific product and loan-size combinations — enabling early intervention
- Seasonal disbursement patterns evident in the monthly trend view — useful for resource planning and provisioning

---

## 📁 Files in This Folder

```
06-Home-Loan-Dataset-PowerBI/
├── README.md
└── [Home_Loan_Dashboard.pbix]        ← Power BI file — full data model + dashboard
```

> **To view:** Download the `.pbix` file and open with [Power BI Desktop](https://powerbi.microsoft.com/en-us/desktop/) (free). All data is embedded in the file.

---

## 🎓 Skills Demonstrated

`Power BI` · `DAX (Measures, Calculated Columns, Time Intelligence)` · `Star Schema Data Modelling` · `Relationship Management` · `Cross-filter Configuration` · `KPI Dashboard Design` · `Financial Portfolio Analytics` · `Delinquency Monitoring` · `Geographic Visualisation` · `Data Visualisation Best Practices` · `Enterprise BI Reporting`

---

**Module:** Data Visualisation using Power BI  
**Program:** Professional Certificate in Business Analytics & Consulting — upGrad × PwC Academy  

