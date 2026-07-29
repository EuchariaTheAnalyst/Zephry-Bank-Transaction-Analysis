# Zephyr Bank Transaction Analytics Dashboard

An end-to-end Power BI analytics project designed to monitor banking transactions, identify fraud patterns, evaluate operational performance, and uncover revenue leakage using transactional data.

---

# Table of Contents

1. [Introduction](Introduction)
2. [Project Description](Project-Description)
3. [Business Problem](Business-Problem)
4. [Project Objectives](Project-Objectives)
5. [Business Questions](Business-Questions)
6. [About the Dataset](About-the-Dataset)
7. [Dataset Structure](Dataset-Structure)
8. [Data Preparation and Transformation](Data-Preparation-and-Transformation)
   - [Importing the Dataset into Power BI](Importing-the-Dataset-into-Power-BI)
   - [Data Cleaning](Data-Cleaning)
   - [Data Validation](Data-Validation)
   - [Data Modelling](Data-Modelling)
9. [Data Analysis in Power BI](Data-Analysis-in-Power-BI)
10. [Insights from the Analysis](Insights-from-the-Analysis)
11. [Business Recommendations](Business-Recommendations)
12. [Conclusion](Conclusion)

---

# Introduction

Banks process thousands of financial transactions every day across different channels, customer segments, merchant categories, and geographical locations. As transaction volumes continue to increase, manually monitoring operational performance, fraudulent activities, transaction failures, and fee collection becomes increasingly difficult.

Business Intelligence tools such as Power BI enable financial institutions to transform raw transactional data into meaningful insights that support strategic and operational decision-making.

This project presents an interactive **Transaction Analytics Dashboard** developed for **Zephyr Bank**. The dashboard provides management with a centralized view of transaction performance, fraud exposure, customer behaviour, regional performance, operational efficiency, and revenue leakage.

Using Power BI, DAX, and a well-structured star schema data model, the solution transforms transactional data into actionable insights that can help executives improve customer experience, reduce operational losses, strengthen fraud monitoring, and optimize fee collection.

---

# Project Description

The objective of this project was to design an interactive Power BI dashboard capable of providing meaningful insights into the bank's transactional activities.

The dashboard focuses on three major business areas:

- Executive Performance Monitoring
- Fraud & Risk Monitoring
- Operational Performance Analysis

The solution allows stakeholders to monitor transaction volumes, transaction values, customer behaviour, fraud exposure, fee revenue, transaction failures, and operational inefficiencies from a single reporting platform.

The dashboard was developed using a dimensional data model consisting of one fact table and three dimension tables, allowing efficient filtering, aggregation, and reporting across multiple business dimensions.

---

# Business Problem

Financial institutions depend heavily on transaction data to understand customer behaviour, monitor operational performance, and protect revenue. However, without an effective reporting solution, several challenges may arise:

- Executives cannot easily monitor transaction performance across different regions and customer segments.
- Fraud investigations become reactive rather than proactive.
- Operational issues leading to transaction failures remain unidentified.
- Revenue leakage resulting from incorrect fee calculations is difficult to detect.
- High-risk customers cannot easily be prioritized for investigation.
- Decision-makers lack a centralized view of key banking performance indicators.

These challenges can result in financial losses, increased fraud exposure, poor customer satisfaction, regulatory concerns, and inefficient resource allocation.

To address these issues, this project delivers an interactive Power BI dashboard that enables business users to monitor key performance indicators, identify operational bottlenecks, and support data-driven decision-making.

---

# Project Objectives

The primary objectives of this project were to:

- Develop an interactive Power BI dashboard for monitoring banking transactions.
- Analyze transaction performance across multiple business dimensions.
- Monitor transaction success and failure rates.
- Identify fraudulent transactions and customers requiring investigation.
- Evaluate revenue generated through transaction fees.
- Detect revenue leakage caused by incorrect fee charging.
- Compare transaction performance across customer segments and geographical regions.
- Provide business stakeholders with actionable insights for operational improvement.
- Support evidence-based decision-making through interactive visualizations.

---

# Business Questions

The dashboard was designed to answer several key business questions, including:

### Executive Performance

- How many transactions were processed during the reporting period?
- What is the total transaction value?
- How much fee revenue was generated?
- What percentage of transactions failed?

### Customer Analysis

- Which customer segments generate the highest transaction values?
- Which customers process the largest transactions?
- Which customers require fraud investigation?
- How does customer behaviour vary across different regions?

### Fraud Analysis

- What percentage of transactions were flagged as fraudulent?
- What is the total financial exposure resulting from fraudulent transactions?
- Which merchant categories experience the highest fraud exposure?
- Does KYC verification status correlate with fraud risk?

### Operations Analysis

- Which transaction types generate the highest revenue leakage?
- What are the leading causes of failed transactions?
- Which transaction channels perform best?
- Are customers being overcharged or undercharged transaction fees?
- Which operational improvements could reduce financial losses?

The answers to these questions enable management to improve operational efficiency, strengthen fraud prevention strategies, optimize fee structures, and enhance customer experience.

---

# About the Dataset

The dataset used in this project represents transactional data generated by **Zephyr Bank**. It was designed to simulate real-world banking operations by capturing customer transactions across multiple channels, merchant categories, transaction types, and geographical regions.

The dataset follows a dimensional modelling approach consisting of one fact table and three dimension tables. This structure enables efficient reporting, simplifies DAX calculations, and improves dashboard performance.

The analysis focuses on understanding transaction performance, fraud occurrence, operational efficiency, customer behaviour, and revenue generation.

The dataset contains **1,500 transaction records** involving **20 customers** across 15 transaction type/channel combinations and 18 merchant categories, covering the period **1 January – 31 May 2026**.

---

# Dataset Structure

The project consists of four related tables.

| Table | Description |
|--------|-------------|
| **Fact_Transactions** | Stores every banking transaction and serves as the central fact table for analysis. |
| **Dim_Customer** | Contains customer demographic information and segmentation details. |
| **Dim_Transaction_Type** | Stores the different transaction categories processed by the bank. |
| **Dim_Merchant_Category** | Contains merchant classifications used for transaction analysis. |

The relationship between these tables forms a **Star Schema**, which is considered a best practice for analytical reporting because it improves model performance, simplifies calculations, and enables efficient filtering across multiple dimensions.

---

# Dataset Description

## Fact_Transactions

This is the primary table used throughout the analysis. Each record represents a unique banking transaction.

The table includes important business attributes such as:

- Transaction ID
- Customer ID
- Merchant Category ID
- Transaction Type ID
- Transaction Date
- Transaction Amount (`amount_gbp`)
- Transaction Fee (`fee_charged_gbp`)
- Transaction Status (Completed / Declined / Pending / Reversed)
- Fraud Flag (`is_flagged_fraud`)
- FX Rate Used
- Device Type
- Failed Reason

This table forms the basis for nearly all calculations and visualizations within the dashboard.

---

## Dim_Customer

The Customer dimension contains descriptive information about each customer.

Customer attributes include:

- Customer ID and Name
- Age Band
- Region
- Customer Segment (Premium, Standard, Starter, Business)
- KYC Verified Status
- Account Open Date

This table enables segmentation of transactions based on customer characteristics and supports customer-level performance analysis.

---

## Dim_Transaction_Type

This table categorizes the different types of banking transactions processed by the institution, including their channel and standard pricing.

- Purchase (Mobile App / Web Browser)
- Transfer – Outbound
- Transfer – International
- ATM Withdrawal (domestic and international)
- Direct Debit
- Standing Order
- Salary Credit
- Crypto Purchase
- Loan Repayment

Using a separate dimension table reduces redundancy and allows transaction performance to be analyzed by transaction category, channel, and standard fee.

---

## Dim_Merchant_Category

The Merchant Category dimension classifies where transactions occurred, along with a sector grouping and an assigned risk classification.

- Groceries, Fuel, Clothing & Fashion (Retail)
- Dining & Restaurants, Entertainment, Gambling (Leisure)
- Utilities, Travel & Transport, Education (Services)
- Crypto Exchange, Salary/Income, Loan & Credit (Financial)

Merchant categorization enables the bank to understand customer spending behaviour while identifying industries associated with higher fraud exposure or operational risk.

---

# Data Preparation and Transformation

Before developing the dashboard, the datasets were reviewed to ensure they were suitable for analysis.

The preparation process involved importing the datasets into Power BI, validating data quality, establishing relationships between tables, and confirming that all fields were assigned the correct data types.

Although the datasets were relatively clean, several validation checks were performed to improve model reliability and analytical accuracy.

---

## Importing the Dataset into Power BI

The datasets were imported into Power BI Desktop using the **Text/CSV** connector.

The following steps were performed:

- Opened Power BI Desktop.
- Selected **Get Data** from the Home ribbon.
- Chose **Text/CSV** as the data source.
- Imported each dataset individually.
- Reviewed each table within the Power Query Editor.
- Loaded the validated datasets into the Power BI data model.

Once imported, relationships were established between the fact table and the dimension tables using their respective keys.

---

## Data Cleaning

The following data quality checks were performed before beginning the analysis:

- Verified that each transaction contained a unique Transaction ID.
- Checked for duplicate records.
- Confirmed that numerical fields such as Transaction Amount and Transaction Fee were correctly formatted as decimal values.
- Ensured that Transaction Date was stored as a Date data type.
- Verified that Customer IDs, Merchant Category IDs, and Transaction Type IDs matched their corresponding dimension tables.
- Reviewed missing values across all columns.

One important observation was the presence of blank values in the **Failed Reason** and **Device Type** columns.

Rather than treating these as missing data, they were interpreted as valid, conditional fields: Failed Reason only applies to transactions with an unsuccessful outcome, and Device Type reflects the originating channel of a transaction, so blanks occur naturally where these attributes do not apply.

No significant duplicate records or relationship inconsistencies were identified during the validation process.

---

## Data Validation

To improve confidence in the analysis, several validation checks were completed after loading the data into Power BI.

These checks included:

- Confirming that transaction totals matched the source data.
- Validating the number of customers imported.
- Ensuring every transaction type was correctly linked to the fact table.
- Confirming that merchant categories displayed correctly across visualizations.
- Verifying that all KPI calculations produced expected values.

Performing these validation checks reduced the likelihood of inaccurate reporting caused by broken relationships or incorrect data types.

---

## Data Modelling

A **Star Schema** was implemented to organize the data model.

The Fact_Transactions table serves as the central table, while the Customer, Transaction Type, and Merchant Category tables provide descriptive information used for slicing and filtering the data.

This modelling approach offers several advantages:

- Faster report performance.
- Reduced data redundancy.
- Simpler DAX calculations.
- Improved scalability for future enhancements.
- Easier maintenance and troubleshooting.

The relationships were configured as **one-to-many** relationships with the dimension tables acting as lookup tables and the transaction table serving as the central fact table.

This model supports interactive filtering across customer segments, transaction types, merchant categories, and regions without duplicating transactional data.

<img width="740" height="379" alt="Image" src="https://github.com/user-attachments/assets/ea6551c1-508c-4624-820e-03ffd8e4437c" />
---

# Data Analysis in Power BI

After preparing the data model, Power BI was used to develop measures that transformed raw transactional data into meaningful business metrics. These measures provide stakeholders with quantitative insights into transaction performance, fraud exposure, operational efficiency, and revenue generation.

Data Analysis Expressions (DAX) were used extensively throughout the project to calculate KPIs, percentages, averages, and performance indicators that could not be obtained directly from the raw dataset.

---

## DAX Measures Created

### Total Transactions

```DAX
Total Transactions =
COUNTROWS(fact_transactions)
```

**Purpose**

Counts the total number of transactions processed during the reporting period.

**Business Value**

Provides management with a quick overview of transaction activity and serves as the foundation for several other performance metrics.

---

### Total Transaction Value

```DAX
Total Transaction Value =
SUM(fact_transactions[amount_gbp])
```

**Purpose**

Calculates the total monetary value of all processed transactions.

**Business Value**

Measures the overall volume of funds processed by the bank and helps executives monitor business growth over time.

---

### Expected Fee

```DAX
Expected Fee =
SUMX(
    fact_transactions,
    RELATED(dim_transaction_type[typical_fee_gbp])
)
```

**Purpose**

Calculates the total fee revenue the bank should generate based on its standard pricing structure, applied per transaction type.

**Business Value**

This measure provides the benchmark used to evaluate actual fee collection performance.

---

### Revenue Leakage

```DAX
Revenue Leakage =
SUMX(
    fact_transactions,
    MAX(
        0,
        RELATED(dim_transaction_type[typical_fee_gbp])
            - fact_transactions[fee_charged_gbp]
    )
)
```

**Purpose**

Measures the amount of fee revenue lost due to undercharging on individual transactions, floored at zero per row so undercharged transactions are never offset by overcharged ones elsewhere in the same total.

**Business Value**

Revenue leakage directly affects profitability. Identifying leakage — and which transaction types it concentrates in — enables management to review pricing application and recover lost revenue with a targeted fix.

---

### Overcharging

```DAX
Overcharging =
SUMX(
    fact_transactions,
    MAX(
        0,
        fact_transactions[fee_charged_gbp]
            - RELATED(dim_transaction_type[typical_fee_gbp])
    )
)
```

**Purpose**

Calculates the total amount customers were charged above the standard fee for their transaction type.

**Business Value**

Monitoring overcharging helps improve customer satisfaction, maintain regulatory compliance, and reduce potential disputes.

---

### Fraud Cases

```DAX
Fraud Cases =
CALCULATE(
    COUNTROWS(fact_transactions),
    fact_transactions[is_flagged_fraud] = TRUE
)
```

**Purpose**

Counts all transactions flagged as fraudulent.

**Business Value**

Supports fraud monitoring by quantifying suspicious transaction activity.

---

### Fraud Exposure

```DAX
Fraud Exposure =
CALCULATE(
    [Total Transaction Value],
    fact_transactions[is_flagged_fraud] = TRUE
)
```

**Purpose**

Measures the total monetary value associated with fraudulent transactions.

**Business Value**

Unlike fraud count alone, fraud exposure highlights the financial impact of fraudulent activity and assists with risk prioritization.

---

### Fraud Rate

```DAX
Fraud Rate =
DIVIDE(
    [Fraud Cases],
    [Total Transactions],
    0
)
```

**Purpose**

Calculates the percentage of all transactions identified as fraudulent.

**Business Value**

Allows management to monitor fraud trends and evaluate the effectiveness of fraud prevention controls.

---

### Success Rate

```DAX
Success Rate =
DIVIDE(
    CALCULATE(
        COUNTROWS(fact_transactions),
        fact_transactions[transaction_status] = "Completed"
    ),
    [Total Transactions],
    0
)
```

**Purpose**

Calculates the percentage of successfully completed transactions.

**Business Value**

A higher success rate indicates reliable transaction processing and a better customer experience.

---

### Failure Rate

```DAX
Failure Rate =
DIVIDE(
    CALCULATE(
        COUNTROWS(fact_transactions),
        fact_transactions[transaction_status] IN {"Declined", "Reversed"}
    ),
    [Total Transactions],
    0
)
```

**Purpose**

Measures the proportion of transactions that Declined or Reversed rather than completing successfully.

**Business Value**

This KPI highlights operational areas worth investigating and supports service improvement initiatives.

---

### Average Transaction Value

```DAX
Average Transaction Value =
AVERAGE(fact_transactions[amount_gbp])
```

**Purpose**

Calculates the average value of transactions processed by the bank.

**Business Value**

Helps understand customer spending behaviour and identify unusual transaction patterns.

---

# Dashboard Development

The dashboard was designed to provide different levels of insight for executives, fraud analysts, and operations teams. Rather than presenting all metrics on a single page, the report was divided into three dedicated dashboards, each focusing on a specific business function.

This structure improves usability by allowing stakeholders to quickly access the information most relevant to their responsibilities while maintaining consistent filtering and navigation across the report.

Each dashboard combines KPI cards with supporting visualizations to provide both high-level summaries and detailed analytical views.

## Executive Overview

<img width="682" height="383" alt="Image" src="https://github.com/user-attachments/assets/6b1a1aac-9ce1-4b37-9205-6917a3658b50" />

---

The Executive Overview page provides a high-level summary of the bank's transaction performance.

The primary objective of this page is to answer the question:

> **"How is the bank performing overall?"**

Key Performance Indicators displayed include:

- Total Transactions
- Transaction Value
- Total Revenue
- Failure Rate

Supporting visualizations include:

- Monthly transaction value trend
- Transaction status distribution
- Transaction value by customer segment
- Transaction activity by region

This page enables executives to quickly identify performance trends and areas requiring further investigation.

## Risk & Fraud Analysis

<img width="681" height="383" alt="Image" src="https://github.com/user-attachments/assets/75fd096d-2938-440e-bf8e-d6cec2725dc9" />

---

The Risk & Fraud Analysis page was designed to support fraud analysts, compliance officers, internal auditors, and risk managers by providing a comprehensive view of fraudulent activities within the bank.

The primary objective of this dashboard is to answer the question:

> **"Where is the bank most exposed to fraud, and which customers require immediate attention?"**

### Key Performance Indicators

- Fraud Cases
- Fraud Exposure
- Fraud Rate
- High-Risk Customers

### Supporting Visualizations

- Fraud Investigation Priority table
- Spending by Merchant Category
- Fraud by KYC Status
- Fraud by Risk Level

Together, these visuals provide a complete picture of the bank's fraud landscape and allow users to drill down into suspicious customer activities.

---

## Operation Analysis

<img width="683" height="382" alt="Image" src="https://github.com/user-attachments/assets/19bcba71-cac4-4b49-b569-dcc7a957cfbe" />

---

The Operation Analysis focuses on measuring operational efficiency and identifying financial opportunity resulting from transaction failures and fee application inconsistencies.

The primary objective of this dashboard is to answer the question:

> **"How efficiently are banking transactions being processed, and where is fee revenue opportunity concentrated?"**

### Key Performance Indicators

- Expected Fee
- Fee Leakage
- Overcharging
- Success Rate

### Supporting Visualizations

- Revenue Leakage by Transaction Type
- Where Overcharging Occurred
- Transaction Failure Reason
- Success Rate by Channel

These visualizations help operational teams identify inefficiencies, improve fee collection processes, and reduce transaction failures.

---

# Insights from the Data Analysis

## Executive Overview Insights

### Transaction Performance
 
The dashboard shows that the bank processed **1,500 transactions** during the reporting period, representing a total transaction value of **£1.9 million**, at an average of **£1,265** per transaction. This indicates a healthy level of customer activity across the reporting period and provides a strong foundation for further operational analysis.
 
---

### Customer Segment Performance
 
Premium customers accounted for **£1,200,687.85 (63.3%)** of the total transaction value, making them the bank's most valuable customer segment by a wide margin. Standard customers followed at £273,888.96 (14.4%), Starter at £253,480.94 (13.4%), and Business at £169,210.00 (8.9%).
 
This concentration highlights the importance of targeted retention strategies and enhanced fraud monitoring for the Premium segment — a disproportionate share of the bank's transaction value, and of its fraud exposure, sits with this group of customers.
 
---

### Monthly Transaction Trend

Transaction values fluctuated across the reporting period, ranging from a low of **£263,965.85 in April** to a high of **£465,168.28 in January**, settling at £391,739.09 in May. April's dip stands out as the softest month in the five-month window and is worth monitoring going forward — with only five months of data available, it is not yet possible to say whether this reflects a recurring seasonal pattern or a one-off dip in activity.

---

### Regional Performance

**London accounted for £1,168,846.18 (61.6%) of total transaction value** despite representing 25% of transaction volume — the clearest sign in the data that transaction value is concentrated in a small number of high-value relationships based in London. South East followed at £559,003.80 (29.5% of value, 15% of volume). Together, London and South East account for 91.1% of total transaction value from just 40% of transaction volume, while the remaining eight regions combined contribute less than 9% of value.

This concentration means regional resourcing — for both business development and fraud monitoring — should weight London and the South East disproportionately relative to their share of the customer base.

---

## Risk & Fraud Insights

### Fraud Activity

**300 of 1,500 transactions (20.0%) were flagged as fraudulent**, representing **£1,186,290.87 — 62.5% of total transaction value.** The gap between ### Transaction Performance

The dashboard shows that the bank processed **1,500 transactions** during the reporting period, representing a total transaction value of **£1.9 million**, at an average of **£1,265** per transaction. This indicates a healthy level of customer activity across the reporting period and provides a strong foundation for further operational analysis.

---

### Customer Segment Performance

Premium customers accounted for **£1,200,687.85 (63.3%)** of the total transaction value, making them the bank's most valuable customer segment by a wide mthe 20% transaction-count share and the 62.5% value share is the most important read in this section: fraud is concentrated in high-value transactions rather than spread evenly across the book, meaning value-weighted monitoring will catch materially more exposure than a flat per-transaction rule.

---

### Customer Risk Analysis

Four customers appear on the Fraud Investigation Priority table, which is filtered to High-risk merchant categories (Gambling and Crypto Exchange). Within this filtered view, ranking by **exposure** and ranking by **fraud count** point to two different customers — and the underlying transaction pattern behind each is different enough to warrant two separate actions rather than one.

| Customer | High-Risk Fraud Count | Exposure | Max Single Transaction | Status Pattern |
|---|---|---|---|---|
| Rajan Mehta | 8 | £120,000.00 | £17,272.73 | 8 of 8 Reversed |
| Daniel Okafor | 9 | £3,968.18 | £504.55 | 9 of 9 Declined |
| Charlotte Lewis | 8 | £2,373.88 | £344.30 | Mixed |
| Mohammed Al-Hassan | 8 | £611.36 | £86.36 | Mixed |

**Rajan Mehta carries the highest exposure by a wide margin** — £120,000 across 8 Gambling transactions, each in the £12,700–£17,300 range, and every one of them **Reversed** rather than Declined. A Reversed status means funds moved and were then pulled back, which is a materially different — and more serious — pattern than a transaction that never cleared in the first place. This is the strongest case for immediate account action: high value per transaction, consistent monthly recurrence (one flagged transaction roughly every month from January through May), and a status pattern indicating money actually moved.

**Daniel Okafor carries the highest fraud count** — 9 Gambling transactions, all **Declined**, each in a tight £382–£505 range, also recurring monthly across the same five-month window. No individual transaction is large, and none of them cleared, but the consistency and repetition — the same category, a narrow and stable amount band, monthly cadence, every attempt declined — reads as a sustained pattern of repeated attempts rather than isolated incidents. This is a different kind of risk signal than Rajan Mehta's case: not "money has moved," but "this account is persistently attempting a specific type of transaction that keeps getting blocked," which is worth understanding before it either stops or succeeds.

**Recommendation**: treat these as two separate actions rather than one ranked list.
- **Freeze Rajan Mehta's account** and initiate a full KYC re-audit — the Reversed status and transaction size represent the highest immediate financial exposure.
- **Investigate, rather than freeze, Daniel Okafor's account** — the repeated, low-value, all-Declined pattern doesn't carry the same immediate financial exposure as Rajan Mehta's case, but the consistency of the attempts is exactly the kind of behavioural signal worth understanding before deciding on further action. Freezing on count alone, without knowing why nine similar attempts were made and blocked, risks either an unnecessary customer disruption or missing what the pattern is actually telling Risk.

Charlotte Lewis and Mohammed Al-Hassan show smaller exposure and count than either of the above, with a mixed status pattern, and can be handled through standard monitoring rather than priority action at this time.

---

### KYC Status and Fraud

Among KYC-verified customers, **25.0% of transactions were fraud-flagged**, compared with 0.0% among unverified customers in this sample. This indicates that KYC verification alone does not eliminate fraud risk — a meaningful share of fraud activity originates from customers who have already passed verification, supporting the case for behavioural monitoring to run alongside KYC checks rather than in place of them.

---

### Merchant Category Analysis

Fraud does not occur uniformly across merchant categories, and the pattern does not fully align with the bank's existing risk classification. **Fuel (31.3%), Online Retail (31.0%), and Loan & Credit (30.1%) — all classified Low or Medium risk — show fraud rates at or above Gambling (30.1%), the highest-rated High-risk category.** Crypto Exchange, the other High-risk category, shows a fraud rate of just 9.6% — statistically in line with several Low-risk categories such as Groceries and Salary/Income.

By transaction count, fraud-flagged activity splits 174 Low-risk, 93 Medium-risk, and 33 High-risk — meaning the majority of flagged fraud activity currently sits in categories the bank classifies as lower risk. This is a useful, actionable signal: as more transaction history accumulates, the risk_flag taxonomy is well positioned to be recalibrated against observed fraud incidence, with Fuel and Online Retail as the clearest early candidates for review.

---

## Operational Insights

### Transaction Failures

**35.0% of transactions were Declined and 25.0% were Reversed**, combining to a 60.0% failure rate; a further 25.0% remain Pending. Of the 300 transactions with a recorded failure reason, **Insufficient Funds accounts for 150 cases (50.0%)**, followed by Card Limit Exceeded and Fraud Suspected at 75 cases each (25.0% each).

The dominance of Insufficient Funds points to a customer-side friction point — one that proactive in-app tools, such as pre-transaction balance visibility, are well placed to address without requiring platform-level changes.

---

### Revenue Leakage

Actual fee revenue collected (£750.17) tracked closely to the Expected Fee benchmark of £750.00 at the aggregate level — but this near-parity is the net effect of two separate patterns that only become visible when leakage and overcharging are measured independently rather than netted against each other.

**Revenue leakage totalled £587, with Transfer – International accounting for £399.61 — 68.1% of the total on its own.** ATM Withdrawal (£112.50, 19.2%) and Crypto Purchase (£75.00, 12.8%) made up the remainder. This concentration means the recovery opportunity is addressable through a focused review of three transaction types rather than a broad pricing overhaul.

---

### Overcharged Transactions

**Overcharging totalled £586.34**, led by Transfer – Outbound (£149.59, 25.5%), Direct Debit (£88.00, 15.0%), Savings Pot Transfer (£87.06, 14.8%), and Standing Order (£75.05, 12.8%) — four products that all carry a standard fee of £0. Because these fields are tracked separately from leakage rather than netted against it, both patterns remain visible: the bank is under-collecting on a small number of cross-border products while over-collecting on a small number of domestic ones.

Addressing overcharging on nominally free products carries a different kind of urgency than leakage — it is an active billing accuracy issue on products explicitly marketed as fee-free, and is the more likely of the two to surface as a customer complaint before it surfaces in a revenue report.

---

### Channel Performance

Success rates were narrow across all four channels — **Mobile App and Web Browser both at 16.7%, ATM Network and Automated both at 12.5%** — a spread of just 4.2 percentage points. This consistency is itself informative: it suggests failure is driven more by account-level factors (balance, limits, fraud holds) than by any single channel underperforming, which should direct Product's next investigation toward account and lending-limit policy rather than channel-specific UX work.

---

# Business Recommendations

## 1. Recover Revenue Leakage on International Products

### Observation

Transfer – International alone accounts for £399.61 of £587 total identified leakage — 68.1% of the total from a single transaction type.

### Recommendation

Review fee application logic on Transfer – International, overseas ATM Withdrawal, and Crypto Purchase to ensure standard pricing is consistently applied.

### Expected Benefit

- Recovers the large majority of identified leakage from a narrow, well-defined fix.
- Improves fee revenue predictability without requiring a broad pricing review.

---

## 2. Correct Overcharging on Fee-Free Products

### Observation

£586.34 was charged as a fee on products carrying a standard £0 fee, led by Transfer – Outbound, Direct Debit, Savings Pot Transfer, and Standing Order.

### Recommendation

Audit fee-charging logic on all nominally free product types and treat this as a billing-accuracy priority alongside the leakage fix above.

### Expected Benefit

- Removes active overcharging on products marketed as free.
- Reduces complaint and regulatory exposure ahead of it becoming a customer-facing issue.

---

## 3. Split Fraud Priority Action by Exposure and by Count

### Observation

Within the High-risk merchant category view, Rajan Mehta carries the highest fraud **exposure** (£120,000 across 8 transactions, all Reversed), while Daniel Okafor carries the highest fraud **count** (9 transactions, all Declined, consistently low-value). These are two distinct risk patterns rather than the same problem at different scales, and treating them identically risks either under-reacting to the exposure case or over-reacting to the count case.

### Recommendation

Freeze Rajan Mehta's account and initiate a full KYC re-audit, given the Reversed status and transaction size. Separately, open an investigation — not a freeze — into Daniel Okafor's account to understand the driver behind nine repeated, consistently-declined Gambling attempts before deciding on further action.

### Expected Benefit

- Matches the response to the actual risk pattern rather than applying a single rule to both cases.
- Addresses the highest financial exposure immediately while avoiding premature action on a lower-value, higher-frequency case that needs understanding before it needs restricting.
- Provides a repeatable template — exposure-driven cases get frozen, count-driven cases get investigated — for future fraud triage.

---

## 4. Recalibrate Merchant Category Risk Classification

### Observation

Fuel, Online Retail, and Loan & Credit — all Low/Medium risk — show fraud rates matching or exceeding Gambling, the highest-rated High-risk category. Crypto Exchange, also High-risk, shows a fraud rate similar to several Low-risk categories.

### Recommendation

Recalibrate the risk_flag taxonomy using observed fraud incidence as more transaction history accumulates, prioritising Fuel and Online Retail for early review.

### Expected Benefit

- Realigns monitoring resource to where fraud is actually occurring.
- Improves the precision of future risk-based transaction screening.

---

## 5. Maintain Behavioural Monitoring Alongside KYC

### Observation

KYC-verified customers still show a 25.0% fraud-flag rate — verification reduces but does not eliminate exposure.

### Recommendation

Continue behavioural fraud monitoring for verified customers rather than treating KYC status as a standalone control.

### Expected Benefit

- Closes the gap between verification and true risk reduction.
- Strengthens the overall fraud control framework without adding friction for legitimate customers.

---

## 6. Reduce Insufficient-Funds Declines

### Observation

Insufficient Funds drives 50.0% of all declines — the single largest failure reason in the dataset.

### Recommendation

Introduce proactive low-balance warnings and spending visibility in-app, ahead of a transaction attempt rather than after decline.

### Expected Benefit

- Addresses the leading cause of transaction failure directly.
- Reduces customer-side friction without requiring platform reliability changes.

---

## 7. Focus Operational Investment on Account Policy, Not Channel UX

### Observation

Channel success rates span only 4.2 percentage points (12.5%–16.7%) — no channel is meaningfully underperforming the others.

### Recommendation

Redirect the next round of Product investigation toward account- and lending-limit policy rather than channel-specific redesign.

### Expected Benefit

- Focuses engineering effort where the data shows the greatest leverage.
- Avoids investment in channel UX improvements unlikely to move the failure rate materially.

---

# Tools and Technologies

| Tool | Purpose |
|--------|---------|
| **Power BI Desktop** | Data modelling, DAX calculations, dashboard development, and visualization |
| **Power Query** | Data import, cleaning, and transformation |
| **DAX (Data Analysis Expressions)** | Creation of KPIs, calculated measures, and analytical metrics |
| **Star Schema Modelling** | Efficient relational data model for reporting |

---

# Conclusion

This project demonstrates how Business Intelligence can be applied to transform raw banking transaction data into actionable business insights.

Using Power BI, a dimensional data model, and DAX calculations, an interactive dashboard was developed to monitor transaction performance, assess fraud exposure, evaluate operational efficiency, and identify revenue opportunity.

The analysis found a transaction book that is fundamentally healthy at the aggregate level — fee collection tracks closely to standard pricing, and transaction value is concentrated in a well-understood Premium customer base — with clear, well-defined opportunities sitting just beneath the headline numbers. Revenue leakage is concentrated in a small number of transaction types. Fraud exposure is concentrated in a small number of customer relationships. Channel performance is consistent enough that the next operational improvement is more likely to come from account-level policy than from channel redesign.

That concentration is the most useful takeaway from this analysis: each of the eight recommendations above is a targeted, measurable action that a single team can own, rather than a broad transformation effort — which means the path from this dashboard to real operational impact is short.

---

## Author

**Eucharia Chibuike N.**

**Data Analyst | Power BI | SQL | Excel | Python**

If you found this project interesting or have suggestions for improvement, feel free to connect or reach out. Feedback and collaboration are always welcome.

