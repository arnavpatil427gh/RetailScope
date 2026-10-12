# RetailScope — E-commerce Sales & Customer Intelligence

An end-to-end Data Analytics project exploring e-commerce transactions to uncover sales trends, understand customer behaviour, identify valuable customer segments, and generate actionable business recommendations.

## 📌 Project Overview

RetailScope transforms raw transactional data into business insights using Python, statistical analysis, customer segmentation, predictive modelling, and data visualization.

The project uses the **E-commerce dataset**, which contains transactions from a UK-based online gift retailer between 2021 and 2025.

The goal is to understand what drives revenue, how customers purchase over time, which customers deserve retention efforts, which products are frequently purchased together, and how historical sales can support short-term planning.

## 🎯 Business Objectives

This project aims to answer the following business questions:

- How do sales and revenue change over time?
- Which products and countries contribute most to sales?
- Who are the most valuable customers?
- Which customers may require re-engagement or retention campaigns?
- How do customers behave after their first purchase?
- Which products are frequently purchased together?
- Can historical transaction data help forecast short-term revenue?
- How can customer analytics support targeted marketing and cross-selling?

## 📊 Dataset

**Dataset:** E-Commerce Sales Analytics Dataset

**Period:** 2021 – 2025

**Source:** [E-Commerce Sales Analytics Dataset](https://www.kaggle.com/datasets/datascikhan/e-commerce-sales-and-customer-analytics)

The original dataset contains 25,909 transaction records and eleven columns.

| Column | Description |
|---|---|
| `InvoiceNo` | Invoice identifier; entries beginning with `C` indicate cancellations |
| `StockCode` | Product identifier |
| `Description` | Product description |
| `Quantity` | Quantity purchased or returned |
| `InvoiceDate` | Date and time of the transaction |
| `UnitPrice` | Unit price in pounds sterling |
| `CustomerID` | Customer identifier |
| `Country` | Customer's country |

The dataset contains missing customer identifiers, duplicate records, returns, cancellations, and unusual transaction values. These characteristics make data cleaning and validation important parts of the analysis.

## 🛠️ Tools & Technologies

- **Python** — Data analysis and modelling
- **Pandas & NumPy** — Data manipulation and numerical computation
- **Matplotlib & Seaborn** — Data visualization
- **Scikit-learn** — Customer clustering and evaluation
- **Lifetimes / BG-NBD and Gamma-Gamma models** — Customer lifetime value analysis
- **Statsmodels** — Time-series forecasting
- **Mlxtend** — Market-basket analysis and association rules
- **Jupyter Notebook / Google Colab** — Analysis environment
- **Streamlit** — Interactive dashboard

## 🔍 Project Workflow

### 1. Data Loading and Initial Inspection

- Load the raw transaction dataset.
- Inspect dimensions, column types, missing values, duplicates, and value ranges.
- Identify data quality issues before performing analysis.

### 2. Data Cleaning and Validation

- Remove duplicate transaction records.
- Investigate missing customer and product information.
- Identify returns, cancellations, non-positive prices, and unusual quantities.
- Match eligible cancellations with their original transactions using transaction-level information.
- Document cleaning decisions and assess their effect on the results.

### 3. Feature Engineering

Create additional features and analytical tables to support:

- Invoice-level analysis
- Product-level analysis
- Customer-level analysis
- Monthly and weekly sales trends
- Customer purchasing behaviour

### 4. Exploratory Data Analysis (EDA)

Explore sales performance across time, geography, products, and customers.

Key areas include:

- Monthly revenue trends and seasonality
- Country-level sales distribution
- Product revenue and concentration
- Customer purchase frequency
- Average order value
- Returns and cancellation patterns

### 5. RFM Customer Segmentation

Segment customers using three metrics:

- **Recency:** How recently a customer purchased
- **Frequency:** How often a customer purchased
- **Monetary:** How much a customer spent

Customers are assigned scores and mapped to meaningful segments, including Champions, Potential Loyalists, Needs Attention, and Hibernating customers.

These segments can support loyalty programmes, targeted promotions, and customer reactivation campaigns.

### 6. Customer Segmentation Using K-Means

Apply unsupervised machine learning to identify groups of customers with similar purchasing behaviour.

The workflow includes:

- Transforming skewed RFM features
- Standardizing features
- Evaluating candidate cluster counts
- Comparing clustering quality metrics
- Profiling the resulting customer groups

The resulting clusters provide an alternative perspective to rule-based RFM segmentation.

### 7. Cohort and Retention Analysis

Group customers according to their first purchase month and track their purchasing activity across subsequent months.

This analysis helps investigate:

- Customer retention over time
- Drop-off after the first purchase
- Differences between acquisition cohorts
- Opportunities to improve repeat purchases

Incomplete observation periods are considered when interpreting cohort results.

### 8. Customer Lifetime Value (CLV)

Estimate future customer purchasing behaviour using probabilistic models.

The analysis uses:

- **BG/NBD:** Estimates expected future purchases and the probability that a customer remains active.
- **Gamma-Gamma:** Estimates expected average order value for suitable customers.

The resulting predictions are used to estimate expected customer revenue over a future 90-day period.

These are model-based estimates, not guaranteed future revenue or customer profit.

### 9. Market-Basket Analysis

Use association-rule mining to identify products frequently purchased together.

The workflow includes:

- Preparing invoice-product baskets
- Restricting the analysis to UK transactions
- Selecting frequently occurring products to manage computational requirements
- Generating association rules
- Evaluating support, confidence, and lift

Potential applications include product bundling, cross-selling, and complementary-product recommendations.

### 10. Weekly Revenue Forecasting

Compare forecasting approaches for short-term revenue planning.

Models and baselines include:

- Naive forecasting
- Moving-average forecasting
- Exponential smoothing (ETS)
- ARIMA

Model performance is compared using a hold-out period. The selected approach is intended to provide a practical short-term planning baseline.

### 11. Customer Master Table and Dashboard

Combine customer-level outputs into a consolidated analytical table containing information such as:

- Customer identifiers
- RFM metrics and segments
- K-Means cluster assignments
- Predicted future purchases
- Estimated customer lifetime value
- Customer activity probabilities

The notebook also prepares aggregated outputs for use in an interactive Streamlit dashboard.

### 12. Business Recommendations

Translate analytical findings into potential business actions, such as:

- Rewarding high-value customers
- Re-engaging inactive customers
- Improving second-purchase conversion
- Recommending complementary products
- Supporting inventory and revenue planning

Recommendations should be evaluated against appropriate business metrics before implementation.

## 📈 Expected Business Value

RetailScope demonstrates how transactional data can support several practical business functions:

| Business Area | Potential Application |
|---|---|
| Sales analytics | Understand revenue trends and product performance |
| Customer retention | Identify customers who may need re-engagement |
| Customer value | Prioritize retention efforts using RFM and CLV estimates |
| Marketing | Design targeted campaigns for different customer segments |
| Cross-selling | Identify product combinations for bundling and recommendations |
| Planning | Use short-term revenue forecasts to support operational decisions |

## 🚀 Getting Started

### Prerequisites

Install Python 3.10 or a compatible version for the selected dependencies.

### 1. Clone the repository

```bash
git clone https://github.com/arnavpatil427gh/RetailScope
cd RetailScope
```

### 2. Create a virtual environment

```bash
python -m venv .venv
```

Activate it:

**Windows**

```bash
.venv\Scripts\activate
```

**macOS / Linux**

```bash
source .venv/bin/activate
```

### 3. Install dependencies

Create a `requirements.txt` containing the libraries used by the notebook, then run:

```bash
pip install -r requirements.txt
```

Core dependencies include:

```text
pandas
numpy
matplotlib
seaborn
scikit-learn
statsmodels
mlxtend
lifetimes
streamlit
jupyter
```

Verify package compatibility with the versions used in the notebook before running the complete workflow.

### 4. Download the dataset

Download the Online Retail dataset from the [E-Commerce Sales Analytics Dataset](https://www.kaggle.com/datasets/datascikhan/e-commerce-sales-and-customer-analytics).

Place the CSV or ZIP file in the location expected by the notebook, or update the data-loading path to match your local environment.

### 5. Run the notebook

Launch Jupyter:

```bash
jupyter notebook
```

Open the project notebook and execute the cells in order.

Alternatively, upload the notebook and dataset to Google Colab and run the analysis there.

## 📁 Repository Structure

```text
RetailScope/
│
├── README.md
├── requirements.txt
├── .gitignore
│
├── data/
│   └── README.md
│
├── notebooks/
    └── e_com_analysis.ipynb
```

## ⚠️ Limitations

- **Limited time period:** The dataset covers approximately one year, restricting the ability to estimate long-term trends and annual seasonality reliably.
- **Missing customer identifiers:** Transactions without customer IDs can contribute to suitable sales and product analyses but cannot be assigned reliably to individual customers.
- **Cancellation matching:** Some cancellations may not be matched confidently to original sales. Revenue metrics depend on the cancellation treatment applied.
- **CLV assumptions:** Customer lifetime value estimates depend on model assumptions and the quality of the transaction history. Unavailable predictions must be investigated before aggregate results are reported.
- **Revenue versus profit:** The dataset does not provide product costs, so revenue estimates must not be interpreted as profit.
- **Forecast uncertainty:** Short-term forecasts are based on limited historical data and should be treated as planning estimates rather than guarantees.
- **Market-basket scope:** Product filtering and country restrictions affect which association rules can be discovered.

## 🔮 Future Improvements

- Strengthen cancellation and return reconciliation.
- Add automated data-quality checks and reproducible data pipelines.
- Validate customer lifetime value predictions and document model diagnostics.
- Improve forecasting validation with rolling-origin evaluation.
- Add SQL-based analysis and cross-check selected KPIs against Python.
- Develop and document a complete interactive dashboard.
- Add automated tests for key business metrics.
- Track the effectiveness of customer retention and cross-selling recommendations.

## 👨‍💻 Project Purpose

RetailScope is a portfolio project designed to demonstrate practical Data Analytics skills, including data cleaning, exploratory analysis, business KPI development, customer segmentation, predictive modelling, and communicating data-driven recommendations.

It emphasizes not only producing analytical results, but also documenting assumptions, validating metrics, and understanding the limitations of the underlying data.
