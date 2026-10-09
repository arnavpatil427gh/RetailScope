# RetailScope — E-commerce Sales & Customer Intelligence

An end-to-end data analytics project exploring online retail transactions, sales trends, product performance, and customer purchasing behavior using Python, Pandas, and RFM segmentation.

## Overview

RetailScope analyzes the UCI Online Retail dataset to uncover business insights from transactional data. The project covers data quality assessment, cleaning, exploratory data analysis (EDA), sales analysis, customer segmentation, and business recommendations.

The goal is to transform raw retail transactions into actionable insights that can support customer retention, product strategy, and market analysis.

## Objectives

- Assess and clean transactional data.
- Analyze sales trends over time.
- Identify top-performing products and countries.
- Segment customers using Recency, Frequency, and Monetary (RFM) analysis.
- Investigate cancellation-related records and their impact on customer metrics.
- Translate analytical findings into business recommendations.

## Dataset

**Source:** [UCI Online Retail Dataset](https://archive.ics.uci.edu/dataset/352/online+retail)

The dataset contains transactions from a UK-based online retailer between December 2010 and December 2011.

Key fields include invoice number, product code, description, quantity, invoice date, unit price, customer ID, and country.

The raw dataset is not included in this repository. Refer to `data/README.md` for download and setup instructions.

## Tools & Technologies

- **Python** — analysis and data processing
- **Pandas** — cleaning, transformation, aggregation, and analysis
- **NumPy** — numerical operations
- **Matplotlib** — data visualization
- **Jupyter Notebook / Google Colab** — interactive analysis
- **RFM Analysis** — customer segmentation

## Project Workflow

1. **Data audit:** inspect dimensions, missing values, duplicates, and transaction anomalies.
2. **Data cleaning:** remove exact duplicates and identify cancellation, return, and invalid-price records.
3. **Exploratory analysis:** investigate sales patterns, product performance, and geographic distribution.
4. **Customer analytics:** calculate recency, purchase frequency, and monetary value.
5. **Customer segmentation:** group customers using rule-based RFM scores.
6. **Cancellation investigation:** match potentially offsetting positive and negative transaction lines using defined criteria.
7. **Business recommendations:** translate the findings into practical next steps.

## Key Findings

The following results come from the current analysis and should be interpreted according to the dataset filters described in the notebook.

- **Positive sales value:** £10.64 million across the broad positive-sales subset.
- **Geographic concentration:** the United Kingdom accounts for approximately 84.59% of positive sales value.
- **Seasonality:** November 2011 is the highest-sales month in the observed period. December 2011 is incomplete because the dataset ends on December 9.
- **Customer segmentation:** the adjusted RFM analysis contains 4,332 identified customers.
- **Customer behavior:** Champions account for approximately 20.94% of the adjusted RFM customer population.
- **Cancellation sensitivity:** the cancellation-adjusted purchase value differs from the baseline, demonstrating why transaction handling matters when measuring customer value.

**Metric definitions matter:** positive sales value is not profit or definitive net revenue. The broad sales subset includes transactions without an identified customer, while RFM requires a customer ID. The cancellation-adjusted results rely on matching assumptions documented in the notebook.

## Visualizations

The notebook includes visualizations covering:

- Monthly positive sales value
- Customer distribution by RFM segment
- Top 10 products by positive sales value
- Top 10 countries by positive sales value
- Top 10 customers by adjusted monetary value

Exported chart images can be added to `reports/figures/` and embedded here as the repository develops.

## Repository Structure

```text
RetailScope/
├── README.md
├── requirements.txt
├── .gitignore
├── data/
│   └── README.md
├── notebooks/
│   └── retailscope_analysis.ipynb
├── reports/
│   ├── business_insights.md
│   └── figures/
├── src/
│   └── README.md
└── sql/
    └── README.md
```

## How to Run

1. Clone this repository:

   ```bash
   git clone https://github.com/arnavpatil427gh/RetailScope.git
   cd RetailScope
   ```

2. Create and activate a virtual environment (recommended).

3. Install dependencies:

   ```bash
   pip install -r requirements.txt
   ```

4. Download the dataset from the official UCI source and follow `data/README.md`.

5. Open `notebooks/retailscope_analysis.ipynb` in Jupyter Notebook or upload it to Google Colab.

6. Update the dataset path in the notebook if needed, then run the cells in order.

## Limitations

- The dataset covers a historical period and should not be treated as a representation of current retail trends.
- Missing customer IDs prevent some transactions from being included in customer-level analysis.
- Cancellation and return matching is rule-based; matched transactions are not guaranteed to represent every real-world cancellation.
- RFM scores and segment definitions are analytical choices, not universal customer classifications.
- Monetary value represents transaction value, not profit or customer lifetime value.

## Future Improvements

- Add SQL queries for business analysis.
- Build an interactive dashboard in Power BI or Tableau.
- Automate data validation and reporting.
- Compare alternative RFM scoring approaches.
- Evaluate customer retention and reactivation strategies.

## Author

Arnav Patil

Aspiring Data Analyst | Python | SQL | Data Visualization

[GitHub Profile](https://github.com/arnavpatil427gh)

---

*This project was developed for learning and portfolio demonstration using a publicly available dataset.*
