
# E-commerce Sales & Revenue Analytics

A data analytics project that transforms historical e-commerce transactions into business KPIs, visualizations, customer insights, and actionable recommendations.

## Project Overview

This project analyses the Online Retail dataset to understand sales trends, product performance, geographic distribution, and customer purchasing behaviour. It demonstrates a complete analytical workflow, from data quality assessment and preprocessing to exploratory analysis, dashboard-style visualizations, and business reporting.

## Objectives

- Evaluate sales performance using key business metrics.
- Analyse monthly sales and order trends.
- Identify leading merchandise items and unusual transactions.
- Compare sales performance across countries.
- Segment identifiable customers by purchase frequency.
- Develop evidence-based business recommendations.

## Dataset

**Source:** UCI Machine Learning Repository — Online Retail

- [Dataset page](https://archive.ics.uci.edu/dataset/352/online+retail)
- [Dataset DOI](https://doi.org/10.24432/C5BW33)
- **License:** CC BY 4.0
- **Observed period:** 1 December 2010 – 9 December 2011

The original dataset contains 541,909 records and eight columns, including invoice number, product code, description, quantity, invoice date, unit price, customer ID, and country.

### Dataset Setup

Download the Excel dataset from the UCI repository and place it at:

`data/Online Retail.xlsx`

The raw dataset is excluded from Git to avoid committing a large source file. The notebook expects the dataset at this relative path.

## Technology Stack

- **Python** — analysis and data processing
- **Pandas** — data cleaning, transformation, and aggregation
- **NumPy** — numerical operations
- **Matplotlib** — data visualization
- **Seaborn** — statistical visualization
- **Jupyter Notebook** — interactive analysis

## Repository Structure

```text
Analytics-Report-Insights/
├── data/
│   └── Online Retail.xlsx        # Download separately; Git-ignored
├── notebooks/
│   └── ecommerce_sales_analysis.ipynb
├── reports/
│   ├── Executive_Summary.md
│   └── Business_Analytics_Report.md
├── .gitignore
└── README.md
```

## Methodology

1. Load and inspect the source dataset.
2. Assess missing values, duplicates, and transaction anomalies.
3. Exclude cancellation invoices, non-positive quantities, and non-positive unit prices from the primary sales analysis.
4. Remove later exact duplicate rows using the original eight columns.
5. Validate the prepared dataset and calculate business KPIs.
6. Analyse monthly sales, product performance, geography, and customer purchasing behaviour.
7. Investigate unusual product transactions and test their effect on product rankings.
8. Develop a dashboard-style visualization and document recommendations.

## Key Results

| Metric | Result |
|---|---:|
| Primary analysis records | 524,878 |
| Gross recorded sales | 10,642,110.80 |
| Distinct eligible invoices | 19,960 |
| Units sold | 5,572,420 |
| Average order value | 533.17 |
| Identifiable customers | 4,338 |
| Repeat-customer rate | 65.58% |
| UK share of gross recorded sales | 84.59% |

**Interpretation note:** These figures represent gross recorded sales under the project's filtering rules. They are not net revenue or profit. Confirm the dataset's currency before using the values in external financial reporting.

## Key Findings

- **Monthly performance:** November 2011 was the strongest complete month in the observed period, with recorded sales of 1,503,866.78.
- **Geographic concentration:** The United Kingdom contributed 84.59% of gross recorded sales.
- **Customer behaviour:** Frequent identifiable customers (six or more eligible invoices) contributed 66.32% of identifiable-customer sales.
- **Product performance:** REGENCY CAKESTAND 3 TIER was the leading merchandise item by recorded sales value.
- **Transaction validation:** An unusually large single-invoice PAPER CRAFT, LITTLE BIRDIE transaction materially affects product rankings and requires source verification.

## Reports

- [Executive Summary](reports/Executive_Summary.md)
- [Business Analytics Report](reports/Business_Analytics_Report.md)
- [Detailed Notebook Analysis](notebooks/ecommerce_sales_analysis.ipynb)

## How to Run

### 1. Clone the repository

```bash
git clone <YOUR_GITHUB_REPOSITORY_URL>
cd Analytics-Report-Insights
```

Replace the placeholder with the actual repository URL.

### 2. Create and activate a virtual environment

Windows PowerShell:

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
```

### 3. Install dependencies

```bash
python -m pip install pandas numpy matplotlib seaborn openpyxl jupyter
```

### 4. Add the dataset

Download the Online Retail Excel file from the UCI dataset page and save it as `data/Online Retail.xlsx`.

### 5. Launch Jupyter

```bash
jupyter notebook
```

Open `notebooks/ecommerce_sales_analysis.ipynb` and run the cells from top to bottom.

## Important Limitations

- The data is historical and does not describe current market conditions.
- December 2010 and December 2011 are incomplete months.
- Customer-level analysis excludes records without a CustomerID.
- Duplicate removal is based on exact matches across the original eight columns.
- An unusual transaction remains included unless independently verified as invalid.
- Service-code exclusion is a limited classification rule.
- The analysis does not calculate profit or establish causal relationships.

## Author

**Kartikey Sharma**  
B.Tech — Artificial Intelligence and Machine Learning

## Acknowledgements

Dataset: Chen, D. (2015). *Online Retail*. UCI Machine Learning Repository. https://doi.org/10.24432/C5BW33
