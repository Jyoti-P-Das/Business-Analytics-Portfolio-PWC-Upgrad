# 🏦 Bank Marketing Campaign — Statistics, EDA & Customer Analytics

**Program:** Professional Certificate in Business Analytics & Consulting — upGrad × PwC Academy  
**Domain:** Financial Services · Customer Analytics  
**Tools:** Microsoft Excel · Statistical Analysis

---

## 🎯 Project Objective

Conduct a comprehensive statistical exploratory data analysis on a Portuguese bank's direct marketing campaign records to identify which customer profiles, campaign parameters, and behavioural signals most strongly predict term deposit subscription. Deliver a customer scoring framework and campaign optimisation strategy grounded in statistical evidence — not guesswork.

This project applied inferential statistics and EDA at scale (250,000+ records), mirroring the kind of customer analytics work done by data analysts in financial services and consulting. It also demonstrates the groundwork for predictive modelling: the derived variables and segmentation logic here would directly feed a classification model (logistic regression or decision tree) in a production data science context.

---

## 💼 Business Problem

The bank's marketing team ran phone-based campaigns to sell term deposit products. With an 11.7% baseline conversion rate and high per-contact costs, precision mattered. The team needed to:
- Move from broad outreach to statistically informed targeting
- Understand which variables are genuine conversion drivers vs noise
- Reduce wasted contacts on low-probability customers while maximising yield from high-probability segments
- Build a framework for scoring future campaign contact lists

---

## 📂 Dataset

**Source:** UCI Machine Learning Repository — Bank Marketing Dataset (publicly available benchmark dataset; one of the most widely studied datasets in customer analytics and classification research)  
**Records:** ~253,680 customer contact records from a 2017 campaign  
**Class Balance:** 11.7% converted (Yes) · 88.3% did not (No) — imbalanced classification problem

**Variable Groups:**

| Category | Variables |
|---|---|
| **Customer Demographics** | Age, Job Type, Marital Status, Education Level |
| **Financial Profile** | Account Balance, Housing Loan (Y/N), Personal Loan (Y/N), Credit Default (Y/N) |
| **Campaign Details** | Contact Method (cellular/telephone), Call Duration, Contacts This Campaign, Last Contact Day & Month |
| **Historical Campaign Data** | Days Since Last Contact, Number of Prior Contacts, Previous Campaign Outcome |
| **Target** | Term Deposit Subscribed — Yes / No |

> UCI Bank Marketing Dataset is freely available at: [archive.ics.uci.edu](https://archive.ics.uci.edu/dataset/222/bank+marketing)
---

## 🔍 Analysis Performed

### 1. Data Cleaning
- Identified and handled 'unknown' category entries across job, education, and contact fields
- Removed structural nulls; standardised categorical encodings
- Post-cleaning dataset: ~229,781 records

### 2. Univariate Analysis
- Distribution plots for all continuous variables (age, balance, duration, contacts)
- Frequency tables for all categorical variables
- Summary statistics: mean, median, mode, standard deviation, skewness, kurtosis
- Baseline conversion rate established: 11.7% — context for all downstream comparisons

### 3. Segmented Univariate Analysis
- Conversion rate computed for every category of every variable
- High-converting job types: retired (25.2%), student (22.8%), management (14.5%)
- Education: tertiary-educated customers convert at nearly 2× the rate of primary-educated
- Balance bands: higher balance accounts show progressively better conversion

### 4. Bivariate Analysis
- Cross-tabulations: every variable vs target (subscribed: yes/no)
- Call duration vs conversion — longest calls convert at 3× the baseline rate; duration is the strongest single predictor
- Contact method: cellular (14.1%) vs telephone (5.2%) — major operational insight
- Seasonality: March (47.2%), September (47.1%) are optimal; December (10.5%) is the worst
- Campaign fatigue: conversion drops sharply after 2 unsuccessful contacts

### 5. Statistical Interpretation
- Distributions interpreted against **Normal Distribution** and **Binomial Distribution** frameworks
- **Central Limit Theorem** applied to interpret sample-level conversion estimates as population-level inferences
- Confidence intervals constructed for key segment-level conversion rates
- **Hypothesis Testing logic** applied: tested whether conversion rate differences between segments are statistically meaningful vs. due to sampling variation

### 6. Derived Metrics
- **Customer Value Score** = f(balance, education level, existing loan burden)
- **Campaign Fatigue Index** = (current contacts + prior contacts) / days since last contact
- **Contact Quality Score** = duration weighting + channel bonus − contact frequency penalty

These derived metrics underpin the 3-tier scoring model and directly mirror the feature engineering step in a supervised classification workflow.

---

## 📈 Key Findings

| Variable | Insight |
|---|---|
| Call Duration | >10 minutes → 3× conversion rate; single strongest predictor |
| Contact Method | Cellular: 14.1% vs Telephone: 5.2% — highly significant |
| Month | March/September peak; December worst — 4× difference |
| Prior Success | Previous campaign success → 64% conversion on re-contact |
| Campaign Contacts | 2+ failed contacts = sharp drop; contact fatigue is real |
| Age | 35–60 optimal window; under-25 and over-70 underperform |
| Job | Retired and students highest; blue-collar lowest |

---

## 💡 Business Recommendations

**Customer Targeting Profile:**
- Age 35–60, tertiary education, management or retired professional
- Account balance > 500 EUR, no existing housing or personal loans
- No prior campaign default history

**Campaign Execution:**
- Eliminate landline calls — switch entirely to cellular
- Cap at 2 contacts per customer per campaign; stop after 2 failures
- Concentrate budget in March–April and September windows
- Agent training to target 10–15 minute call engagement

**Customer Scoring — 3-Tier Model:**

| Tier | Profile | Expected Conversion | Recommended Resource |
|---|---|---|---|
| **Hot** | Value Score > 7, prior success | 35–40% | 50% of agent capacity |
| **Warm** | Value Score 3–7, no prior contact | 12–18% | 40% of agent capacity |
| **Cold** | Value Score < 3, prior failures | 5–8% | 10% (test messaging only) |

**Projected outcome:** 78% improvement in campaign ROI + 21% more conversions with 29% fewer contacts
---

## 📁 Files in This Folder

```
05-bank-marketing-eda/
├── README.md
├── analysis/
│   └── bank-marketing.xlsx    ← Full EDA workbook (3 analysis sheets)
```

---
## 🎓 Skills Demonstrated

`Exploratory Data Analysis` · `Statistical Analysis` · `Inferential Statistics` · `Normal Distribution` · `CLT` · `Confidence Intervals` · `Hypothesis Testing` · `Univariate & Bivariate Analysis` · `Correlation` · `Derived Metrics` · `Feature Engineering` · `Customer Segmentation` · `Campaign Optimisation` · `ROI Analysis` · `Financial Services Analytics` · `Excel Advanced Analytics`

---

**Modules:** Exploratory Data Analysis + Inferential Statistics + Hypothesis Testing  
