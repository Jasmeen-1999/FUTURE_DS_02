# Customer Retention & Churn Analysis

## Data Science & Analytics – Task 2 (2026) | Future Interns

A customer retention and churn analysis project using the Telco Customer Churn dataset. The objective was to understand why customers leave, identify high-risk customer segments, analyze customer lifetime patterns, and translate findings into practical retention recommendations.

## Business Problem

Customer churn directly affects recurring revenue and long-term growth in subscription businesses. This project analyzes customer and service characteristics to answer:

- How large is the current churn problem?
- Which customer segments have the highest churn?
- How does churn change with customer tenure?
- Which contract and payment methods are associated with higher churn?
- Which services and customer characteristics are linked to higher churn?
- Which customer segment represents the greatest retention risk?
- What actions could help reduce churn?

## Dataset

**Telco Customer Churn Dataset** from Kaggle.

The dataset contains **7,043 customers** and 21 customer, subscription, service, billing, and churn-related fields.

Key fields include customer demographics, tenure, contract type, payment method, internet service, monthly charges, total charges, and churn status.

## Tools Used

- **Python** – data cleaning, exploratory analysis, segmentation and churn calculations
- **Pandas** – data manipulation and analysis
- **NumPy** – numerical operations
- **Matplotlib / Seaborn** – exploratory visualization
- **Power BI** – dashboard and business storytelling
- **DAX** – calculated measures and dashboard KPIs
- **Jupyter Notebook** – analysis workflow

## Data Preparation

The analysis included:

- Loading and inspecting the dataset
- Checking data types and missing values
- Handling whitespace-only values in `TotalCharges`
- Checking duplicate records and duplicate customer IDs
- Creating tenure groups
- Creating monthly-charge groups
- Creating customer segment combinations
- Calculating churn and retention percentages
- Preparing summary tables for dashboard analysis

No duplicate customer IDs were identified in the dataset.

## Key Metrics

| Metric | Result |
|---|---:|
| Total Customers | 7,043 |
| Churned Customers | 1,869 |
| Retained Customers | 5,174 |
| Overall Churn Rate | **26.54%** |
| Retention Rate | **73.46%** |
| Average Tenure | **32.37 months** |

## Key Insights

### 1. Early-tenure customers are the highest-risk group

| Tenure Group | Churn Rate |
|---|---:|
| 0–6 months | **52.94%** |
| 7–12 months | **35.89%** |
| 13–24 months | **28.71%** |
| 25–48 months | **20.39%** |
| 49–72 months | **9.51%** |

The first few months of the customer lifecycle are a critical retention window.

### 2. Month-to-month contracts have substantially higher churn

| Contract | Churn Rate |
|---|---:|
| Month-to-month | **42.71%** |
| One year | 11.27% |
| Two year | 2.83% |

Customers on longer-term contracts show much lower churn.

### 3. Electronic check customers show the highest churn

| Payment Method | Churn Rate |
|---|---:|
| Electronic check | **45.29%** |
| Mailed check | 19.11% |
| Bank transfer (automatic) | 16.71% |
| Credit card (automatic) | 15.24% |

There were **1,071 churned customers using electronic check**, representing **57.30% of all churned customers**.

### 4. Fiber optic customers show elevated churn

| Internet Service | Churn Rate |
|---|---:|
| Fiber optic | **41.89%** |
| DSL | 18.96% |
| No internet service | 7.40% |

This segment warrants further investigation around pricing, service quality, technical support, and customer experience.

### 5. Higher monthly charges are associated with higher churn

Customers in higher monthly-charge segments show greater churn than customers paying below $30 per month, suggesting that pricing or perceived value may be relevant to retention.

### 6. Customer characteristics also matter

The analysis found higher churn among:

- Senior customers compared with non-senior customers
- Customers without partners compared with customers with partners
- Customers without dependents compared with customers with dependents

These characteristics can contribute to broader customer-risk segmentation.

## Highest-Risk Customer Segment

The dashboard identifies:

> **0–6 months | Month-to-month | Electronic check | Fiber optic**

### Churn Rate: **75.45%**

This segment combines several individually high-risk characteristics and represents a priority group for retention efforts.

## Business Recommendations

### 1. Strengthen first-6-month onboarding

Because churn reaches **52.94% among customers with 0–6 months of tenure**, introduce stronger onboarding, proactive support, product education, and early engagement campaigns.

### 2. Encourage longer-term contracts

Month-to-month customers have a **42.71% churn rate**, compared with **2.83% for two-year contracts**. Consider targeted discounts, loyalty benefits, or plan incentives for customers willing to move to longer-term contracts.

### 3. Investigate electronic-check customers

Electronic-check users have a **45.29% churn rate** and account for **57.30% of all churned customers**. Investigate whether payment experience, billing friction, or customer characteristics associated with this payment method contribute to churn.

### 4. Investigate the fiber-optic segment

Fiber optic customers have a **41.89% churn rate**. Further investigation should examine pricing, service quality, technical support, and customer expectations.

### 5. Build an early-warning retention program

Use tenure, contract type, payment method, internet service, monthly charges, and customer characteristics to identify customers at elevated churn risk and trigger targeted retention actions.

## Dashboard

The Power BI dashboard contains two pages.

### Page 1 – Customer Churn Analysis Dashboard

Includes:

- Total customers
- Churned customers
- Churn rate
- Retention rate
- Average tenure
- Churn by tenure
- Churn by contract
- Churn by payment method
- Churn by internet service
- Churn by monthly charges

### Page 2 – Highest-Risk Customer Segment

Includes:

- Early-customer churn by contract and payment method
- Highest-risk customer segment
- Senior citizen status
- Partner status
- Dependents status

## Cohort Analysis Note

The task description mentions cohort analysis as an optional analytical direction. The selected Telco dataset does not contain a customer signup date/month field, so traditional signup-month cohort analysis was not appropriate.

Instead, **tenure-based customer lifetime segmentation** was used to analyze how churn changes throughout the customer lifecycle.

## Project Structure

```text
customer-churn-retention-analysis/
│
├── README.md
├── requirements.txt
|
├── data/
│   ├── cleaned/
│   │   └── telco_churn_analysis_ready.csv
│   │
│   └── raw/
│       └── WA-Fn-UseC_-Telco-Customer-Churn.csv
|
├── notebooks/
│   └── Customer_Churn_Analysis.ipynb
|
├── dashboard/
│   └── Customer_Churn_Analysis_Dashboard.pbix
|
└── images/
    ├── dashboard_page1.PNG
    └── dashboard_page2.PNG
```

## How to Run the Analysis

1. Clone or download the repository.
2. Install dependencies:

```bash
pip install -r requirements.txt
```

3. Open the Jupyter notebook in `notebooks/`.
4. Run the analysis cells.
5. Open the Power BI `.pbix` file to explore the completed dashboard.

## Future Improvements

- Build signup-month cohorts if timestamped acquisition data becomes available
- Develop a predictive churn model
- Add customer lifetime value analysis
- Create an automated churn-risk scoring system
- Test retention strategies through controlled experiments
- Connect the dashboard to regularly refreshed business data

## Author

**Jasmeen Kaur**

Data Science & Analytics | Python | SQL | Power BI | Machine Learning

---

*Completed as part of Data Science & Analytics – Task 2 (2026) by Future Interns.*
