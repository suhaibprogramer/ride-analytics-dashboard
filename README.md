# Data Analysis Internship — Task 4: Customer Churn & Retention Analysis

**Author:** Muhammad Suhaib

## Overview

This project analyzes customer churn behavior using the **Telco Customer Churn (IBM/BlastChar)** dataset. The goal is to understand why customers leave, identify the strongest predictors of churn, and turn those findings into practical retention recommendations — delivered through a Python analysis notebook, an interactive Power BI dashboard, and a concise summary report.

## Objective

- Measure the overall customer churn rate
- Identify which customer attributes (contract type, tenure, monthly charges, services subscribed, payment method, etc.) are most associated with churn
- Segment customers by churn risk
- Translate findings into actionable retention strategies

## Dataset

**Telco Customer Churn (IBM / BlastChar)**
A dataset of telecom customers including demographics, account information (tenure, contract type, payment method), subscribed services (internet, streaming, tech support, etc.), monthly and total charges, and whether the customer churned.

## Deliverables

| File | Description |
|---|---|
| `Task4_Customer_Churn_Analysis.ipynb` | Full exploratory data analysis, cleaning, and churn-driver analysis in Python |
| `Task4_Churn_Dashboard.pbix` | Interactive Power BI dashboard with KPIs and churn breakdowns |
| `Task4_Final_Summary.pdf` | 1–2 page executive summary of findings and recommendations |

## Approach

1. **Data Cleaning** — Handled missing values, corrected data types, checked for duplicates and inconsistent categories.
2. **Exploratory Analysis** — Examined churn distribution and how it varies across customer segments (contract type, tenure buckets, payment method, services used).
3. **Driver Identification** — Compared churn rates across segments to isolate the strongest churn drivers.
4. **Dashboard Development** — Built KPI cards, segment breakdowns, and filters in Power BI so the findings can be explored interactively.
5. **Reporting** — Summarized the top findings and translated them into retention recommendations.

## Key Findings

*(To be filled in with your actual results — upload the dataset or notebook and these can be generated from real numbers)*

- Overall churn rate: *[TBD]*
- Top churn drivers: *[TBD — e.g. month-to-month contracts, low tenure, no tech support]*
- Highest-risk customer segment: *[TBD]*

## Recommendations

*(To be filled in based on the findings above)*

- *[TBD — e.g. incentivize longer-term contracts]*
- *[TBD — e.g. proactive outreach to low-tenure customers]*
- *[TBD — e.g. bundle tech support / add-on services to reduce churn]*

## Tech Stack

- Python (pandas, matplotlib/seaborn, scikit-learn)
- Power BI Desktop
- Jupyter Notebook

## Repository Structure

```
task4-churn-analysis/
│
├── data/
│   └── telco_customer_churn.csv
├── notebooks/
│   └── Task4_Customer_Churn_Analysis.ipynb
├── powerbi/
│   └── Task4_Churn_Dashboard.pbix
├── reports/
│   └── Task4_Final_Summary.pdf
├── screenshots/
│   └── dashboard/
└── README.md
```

## How to Reproduce

1. Clone this repository
2. Install dependencies: `pip install pandas matplotlib seaborn scikit-learn jupyter`
3. Run `Task4_Customer_Churn_Analysis.ipynb` to reproduce the analysis
4. Open `Task4_Churn_Dashboard.pbix` in Power BI Desktop to explore the dashboard
