# AgroInsight: End-to-End Data Analytics Project

**Stockout Detection | Expiry Risk | Farmer Credit Risk**

AgroInsight is an end-to-end Business Intelligence and risk detection system designed to help agro-input businesses identify potential losses, monitor inventory, manage farmer credit, and make better business decisions.

Built using **Databricks, SQL, Power BI, and n8n**, this project demonstrates how raw business data can be transformed into actionable insights and automated email alerts.

## Business Problem

Agro-input businesses face several challenges:

- **Stockouts:** Products run out of stock during important planting seasons, resulting in lost sales.
- **Expiry Risk:** Products approach their expiry dates before they can be sold.
- **Farmer Credit Risk:** Outstanding farmer credit and overdue payments affect cash flow.
- **Limited Visibility:** Managers struggle to identify which products, branches, and customers require immediate attention.

AgroInsight brings these business problems into one decision-support system.

## Project Objectives

- Detect products at risk of stockouts before inventory runs out.
- Identify batches approaching expiry and estimate their financial exposure.
- Monitor farmer credit balances and overdue payments.
- Track branch performance using business KPIs.
- Visualize business risks in a Power BI management dashboard.
- Automate email alerts using n8n.

## Technology Stack

| Technology | Purpose |
|---|---|
| Databricks | Data processing and transformation |
| SQL | Business logic, data modeling, and risk detection |
| Medallion Architecture | Organizing Bronze, Silver, and Gold data layers |
| Power BI | Management reporting and visualization |
| n8n | Automated email notifications |
| GitHub | Version control and project documentation |

## System Architecture

```text
Business Source Data
        |
        v
Databricks Bronze Layer
        |
        v
Databricks Silver Layer
        |
        v
Databricks Gold Layer
        |
        +----------------------+
        |                      |
        v                      v
Power BI Dashboard       Risk Alert Views
                               |
                               v
                         n8n Workflows
                               |
                               v
                       Automated Emails
                               |
                               v
                      Management Action
```

## Key Business Intelligence Features

### 1. Stockout Risk Detection

Identifies products whose available inventory may not cover demand during supplier replenishment lead time.

Example indicators:
- Available stock
- Average daily demand
- Days of inventory cover
- Supplier lead time
- Stockout risk status

### 2. Product Expiry Risk

Identifies inventory batches approaching expiry and estimates the value of stock exposed to potential write-offs.

Example indicators:
- Product and batch
- Expiry date
- Days until expiry
- Remaining quantity
- Estimated exposure at cost

### 3. Farmer Credit Risk

Analyzes outstanding balances and overdue payments to help prioritize credit follow-up.

Example indicators:
- Outstanding credit
- Days overdue
- Overdue balance ratio
- Credit-limit utilization
- Credit risk category

### 4. Branch Performance Monitoring

Tracks business performance across branches using measures such as:
- Revenue
- Lost sales
- Stock write-offs
- Credit collections
- Overdue credit

### 5. Automated Email Alerts

Uses n8n to retrieve risk records and notify the appropriate people when action may be required.

The purpose is to move beyond reporting problems to helping teams respond to them.

## Example Business Scenario

The synthetic case study uses the following illustrative baseline estimates:

| Business Metric | Estimated Value |
|---|---:|
| Revenue across 6 branches over 24 months | KES 410.8M |
| Lost sales associated with stockouts | KES 32.3M |
| Expired-stock write-offs | KES 8.0M |
| Credit overdue by 60+ days | KES 4.4M |
| Total estimated value at stake | KES 44.7M |

**Note:** These figures describe the synthetic project scenario. They are not audited business results or proof of savings achieved by the system.

## Project Workflow

1. Ingest source data into Databricks Bronze.
2. Clean and standardize data in Silver.
3. Build Gold dimensions and fact tables.
4. Develop SQL models for stockout, expiry, and credit risk.
5. Create risk alert views.
6. Build the Power BI management dashboard.
7. Configure n8n email-alert workflows.
8. Validate outputs and test the end-to-end process.

## Repository Structure

```text
AgroInsight-GitHub-Project/
├── README.md
├── LICENSE
├── .gitignore
├── docs/
│   ├── architecture.md
│   ├── business-rules.md
│   ├── power-bi-dashboard.md
│   └── n8n-email-alerts.md
├── sql/
│   ├── 00_setup_notes.sql
│   ├── 01_gold_dimensions.sql
│   ├── 02_gold_facts.sql
│   ├── 03_risk_models.sql
│   └── 04_alert_views.sql
├── power-bi/
│   └── README.md
├── n8n/
│   └── README.md
└── assets/
    └── README.md
```

## Author

**Erick Mwangome**

Business Intelligence | Data Analytics | Analytics Engineering

Building practical, end-to-end Business Intelligence systems that connect data engineering, business logic, reporting, and automated action.