
# E-commerce Sales & Revenue Analytics Report

**Project:** E-commerce Sales & Revenue Analytics  
**Dataset:** Online Retail  
**Analysis Period:** 1 December 2010 – 9 December 2011  
**Report Type:** Business Analytics and Insights

---

## 1. Executive Overview

This report evaluates historical e-commerce transactions to understand sales trends, product performance, geographic distribution, and customer purchasing behaviour. The analysis combines data-quality checks, transaction filtering, duplicate handling, key performance indicators, and visual exploration.

The primary analysis dataset contains **524,878 records**, representing **19,960 distinct invoices** and **10,642,110.80 in gross recorded sales**.

The findings indicate strong dependence on the United Kingdom market, a substantial contribution from frequent identifiable customers, and sensitivity in product rankings caused by an unusually large single-invoice transaction.

## 2. Business Objectives

The project aims to:

1. Measure overall sales performance using business KPIs.
2. Identify monthly sales patterns and changes in order volume.
3. Evaluate leading products and product concentration.
4. Compare sales across countries.
5. Understand customer purchase frequency and sales contribution.
6. Translate findings into practical business recommendations.

## 3. Dataset Overview

The Online Retail dataset contains **541,909 transaction-line records** and eight original columns:

- `InvoiceNo`: invoice identifier.
- `StockCode`: product or service code.
- `Description`: product or service description.
- `Quantity`: number of units in a transaction line.
- `InvoiceDate`: date and time of the transaction.
- `UnitPrice`: recorded unit price.
- `CustomerID`: customer identifier, where available.
- `Country`: customer country recorded in the dataset.

The observed transaction dates range from 1 December 2010 to 9 December 2011.

## 4. Data Quality Assessment

### 4.1 Missing Values and Duplicates

The original dataset contains:

- **135,080 missing CustomerID values** (24.93%).
- **1,454 missing Description values** (0.27%).
- **5,268 fully duplicated rows**.

Missing customer identifiers limit customer-level analysis. Such records were retained in the transaction-level sales analysis when they met the sales eligibility criteria.

### 4.2 Transaction Anomalies

The initial checks identified:

- 9,288 rows associated with cancellation invoices.
- 10,624 rows with negative quantities.
- 2,515 rows with zero unit prices.
- 2 rows with negative unit prices.

The cancellation rows overlap with negative-quantity rows. Therefore, these anomaly counts should not be added together to estimate the number of unique excluded records.

Two negative-price records were identified as adjustments described as “Adjust bad debt,” rather than ordinary merchandise sales.

### 4.3 Preparation Rules

The primary sales view excludes:

1. Invoice rows whose invoice number begins with `C`.
2. Rows with non-positive quantities.
3. Rows with non-positive unit prices.

Later exact duplicates are removed using the original eight columns. Missing CustomerID values are retained for transaction-level analysis but excluded from customer-level metrics.

After eligibility filtering, the dataset contains 530,104 rows. After exact-duplicate removal, the primary analysis dataset contains **524,878 rows**.

## 5. Methodology and KPI Definitions

### 5.1 Recorded Line Sales

Line sales are calculated as:

**Line Sales = Quantity × Unit Price**

### 5.2 Gross Recorded Sales

Gross recorded sales are the sum of eligible line sales after the specified filtering and duplicate-removal steps.

This measure is not equivalent to net revenue, profit, or cash received. It does not account for operating expenses, cost of goods, taxes, or other financial adjustments.

### 5.3 Average Order Value

**Average Order Value (AOV) = Gross Recorded Sales ÷ Distinct Eligible Invoices**

### 5.4 Repeat-Customer Rate

The repeat-customer rate is the proportion of identifiable customers who placed more than one distinct eligible invoice during the observed period.

### 5.5 Customer Segments

Identifiable customers are grouped by eligible invoice frequency:

- **One-time:** 1 invoice.
- **Repeat:** 2–5 invoices.
- **Frequent:** 6 or more invoices.

These are descriptive segments created for this analysis, not official business classifications.

## 6. Overall Sales Performance

The primary dataset reports:

| KPI | Result |
|---|---:|
| Gross recorded sales | 10,642,110.80 |
| Distinct eligible invoices | 19,960 |
| Units sold | 5,572,420 |
| Average order value | 533.17 |
| Primary analysis records | 524,878 |

### Interpretation

The dataset provides a substantial transaction history for evaluating sales patterns. However, the results describe the recorded transactions and should not be interpreted as a complete profitability assessment.

## 7. Monthly Sales Trends

Monthly recorded sales increased substantially toward the end of the observed period.

- November 2011 recorded the highest full-month sales, at **1,503,866.78**, across **2,769 invoices**.
- October 2011 recorded sales of **1,151,263.73**.
- September 2011 recorded sales of **1,056,435.19**.
- December 2011 recorded **637,790.33**, but the data ends on 9 December.

### Interpretation

The rise in recorded sales from September through November warrants further investigation. Possible explanations include seasonal demand, promotions, changes in order size, or other commercial factors. The available data alone does not establish the cause.

December 2011 should not be compared directly with complete months because it covers only part of the month.

**Visual reference:** See the monthly revenue trend and monthly order-volume charts in the notebook.

## 8. Product Performance

### 8.1 Leading Merchandise Items

After excluding the identified service-related stock codes (`DOT`, `POST`, and `M`), the leading merchandise items by recorded sales value include:

| Product | Recorded Sales |
|---|---:|
| REGENCY CAKESTAND 3 TIER | 174,156.54 |
| PAPER CRAFT, LITTLE BIRDIE | 168,469.60 |
| WHITE HANGING HEART T-LIGHT HOLDER | 104,284.24 |
| PARTY BUNTING | 99,445.23 |
| JUMBO BAG RED RETROSPOT | 94,159.81 |

The merchandise ranking is more suitable for product comparisons than a ranking that includes postage and other service entries.

### 8.2 Unusual Single-Invoice Transaction

The product `PAPER CRAFT, LITTLE BIRDIE` has a recorded quantity of **80,995 units** on invoice `581483`, dated 9 December 2011. The line value is **168,469.60**, and the invoice contains only one eligible line in the inspected data.

This transaction contributes approximately **1.58%** of total gross recorded sales and materially affects the merchandise ranking.

### Interpretation

The transaction should be verified against the original invoice or business records before being used to make inventory or demand-planning decisions. It remains in the primary analysis because an unusual value alone is not sufficient evidence that the transaction is invalid.

The sensitivity analysis shows that excluding this invoice changes the merchandise ranking. This demonstrates why outlier review is important when evaluating leading products.

## 9. Geographic Sales Performance

The United Kingdom dominates recorded sales.

| Country | Recorded Sales | Share of Total |
|---|---:|---:|
| United Kingdom | 9,001,744.09 | 84.59% |
| Netherlands | 285,446.34 | 2.68% |
| EIRE | 283,140.52 | 2.66% |
| Germany | 228,678.40 | 2.15% |
| France | 209,625.37 | 1.97% |

### Interpretation

The UK concentration indicates substantial geographic dependence. Other countries contribute smaller shares of recorded sales, but their commercial potential cannot be assessed from sales value alone.

Before expanding into other markets, the business should evaluate profit margins, shipping costs, delivery performance, customer acquisition costs, and local demand.

**Visual reference:** See the country sales comparison chart in the notebook.

## 10. Customer Purchasing Behaviour

### 10.1 Customer Identification

The analysis identifies **4,338 customers** with available customer identifiers in the primary dataset.

Sales linked to these identifiable customers total **8,887,208.89**, equivalent to **83.51%** of gross recorded sales.

The remaining sales are not included in customer-level segment analysis because their customer identifiers are unavailable.

### 10.2 Repeat Purchasing

Of the 4,338 identifiable customers, **2,845 placed more than one eligible invoice**, resulting in a repeat-customer rate of **65.58%**.

This rate describes purchasing behaviour during the observed period. It does not establish long-term loyalty or predict future retention.

### 10.3 Customer Segment Contribution

| Segment | Customers | Share of Identifiable-Customer Sales |
|---|---:|---:|
| One-time | 1,493 | 6.91% |
| Repeat (2–5 invoices) | 1,973 | 26.77% |
| Frequent (6+ invoices) | 872 | 66.32% |

### Interpretation

Frequent customers account for a substantial share of identifiable-customer sales. This makes customer retention and the experience of high-frequency buyers useful areas for further investigation.

The segment differences are descriptive. They do not prove that a particular marketing action will increase purchasing.

**Visual reference:** See the customer purchase-frequency and customer-segment sales charts in the notebook.

## 11. Key Business Insights

1. **Sales rose toward November 2011.** November was the strongest full month in the observed period, although the underlying cause requires further investigation.
2. **The UK dominates recorded sales.** Its 84.59% share indicates substantial geographic concentration.
3. **Frequent customers are commercially important.** They contribute 66.32% of sales linked to identifiable customers.
4. **Product rankings require validation.** A single unusually large transaction materially changes the ranking of merchandise items.
5. **Customer data coverage is incomplete.** Missing customer identifiers limit the scope of customer-level conclusions.
6. **Merchandise and service entries should be analysed separately.** This produces a more meaningful comparison of physical products.

## 12. Recommendations

### 12.1 Evaluate Customer Retention

Test targeted customer-engagement or repeat-purchase initiatives. Measure repeat-purchase rate, time to second purchase, incremental sales, and campaign cost against an appropriate comparison group.

### 12.2 Assess Geographic Diversification

Investigate markets outside the UK using demand, contribution margin, shipping costs, returns, and delivery performance. Do not use sales share alone to determine expansion priorities.

### 12.3 Verify the Large Product Transaction

Check invoice `581483` against source records and order fulfilment details. Preserve the recorded transaction in the baseline until it is independently verified.

### 12.4 Improve Customer Data Quality

Investigate why customer identifiers are missing and establish data-capture controls where appropriate. Monitor completeness over time.

### 12.5 Separate Product and Service Reporting

Maintain distinct classifications for merchandise, postage, and other service-related entries. Review stock-code mappings and document the classification rules.

### 12.6 Establish a Monthly Performance Review

Monitor gross recorded sales, invoice volume, average order value, geographic share, product contribution, and repeat purchasing. Compare complete calendar months and document changes in methodology.

## 13. Limitations and Assumptions

- The analysis covers a historical period and does not represent current business conditions.
- December 2010 and December 2011 are partial months.
- Gross recorded sales are not equivalent to net revenue or profit.
- Duplicate removal assumes later exact matches across the original eight columns are redundant; this should be validated against business rules.
- Missing customer identifiers limit customer-level analysis.
- The large single-invoice product transaction remains unverified.
- Excluding `DOT`, `POST`, and `M` is a limited service-code classification, not a complete verified product taxonomy.
- Customer segments are based on invoice frequency during the observed period.
- The dataset's currency should be confirmed from its documentation before external financial reporting.
- The analysis does not establish causation or measure campaign effectiveness.

## 14. Conclusion

This project converts transaction-level e-commerce data into business KPIs, visual comparisons, customer segments, product rankings, and actionable recommendations.

The most important findings are the concentration of sales in the UK, the substantial contribution from frequent identifiable customers, and the need to validate unusual transactions before using product rankings for operational decisions.

The results provide a foundation for further business investigation. Decisions involving profitability, marketing investment, and market expansion should be supported by verified source records and additional financial and operational data.

## 15. Dataset Reference

Chen, D. (2015). *Online Retail* [Dataset]. UCI Machine Learning Repository.

- Dataset: https://archive.ics.uci.edu/dataset/352/online+retail
- DOI: https://doi.org/10.24432/C5BW33
- License: CC BY 4.0
