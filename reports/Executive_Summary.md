
# E-commerce Sales & Revenue Analytics
## Executive Summary

### 1. Project Overview

This project analyses historical e-commerce transactions to evaluate sales performance, product contribution, geographic concentration, and customer purchasing behaviour. The objective is to transform transaction-level data into measurable business insights and actionable recommendations.

### 2. Key Performance Indicators

| KPI | Result |
|---|---:|
| Gross Recorded Sales | 10,642,110.80 |
| Eligible Invoices | 19,960 |
| Units Sold | 5,572,420 |
| Average Order Value | 533.17 |
| Identifiable Customers | 4,338 |
| Repeat-Customer Rate | 65.58% |
| UK Sales Share | 84.59% |

*Note: The dataset documentation should be consulted to confirm the currency. These figures represent gross recorded sales, not net revenue or profit.*

### 3. Key Findings

**Sales performance:** November 2011 recorded the highest monthly sales in the observed period, at 1,503,866.78. December 2011 is incomplete, with records ending on 9 December.

**Geographic concentration:** The United Kingdom contributed 84.59% of gross recorded sales, indicating substantial dependence on one market.

**Customer purchasing behaviour:** Among customers with identifiable IDs, 65.58% placed more than one eligible invoice during the observed period. Frequent customers, defined as those with six or more invoices, contributed 66.32% of identifiable-customer sales.

**Product performance:** REGENCY CAKESTAND 3 TIER was the leading merchandise item by recorded sales value, at 174,156.54.

**Data quality:** Approximately 24.93% of original records lacked a CustomerID. An unusually large transaction for PAPER CRAFT, LITTLE BIRDIE contributed 168,469.60 to recorded sales and materially affected product rankings.

### 4. Recommendations

1. Evaluate targeted retention campaigns and measure their incremental impact on repeat purchasing.
2. Assess geographic diversification using profitability, delivery costs, and market potential.
3. Verify the unusually large PAPER CRAFT, LITTLE BIRDIE transaction before using product rankings for inventory decisions.
4. Improve customer identification and data completeness.
5. Separate merchandise from postage and other service-related entries when evaluating product performance.
6. Monitor monthly sales, invoice volume, average order value, customer retention, and geographic sales share.

### 5. Methodology and Limitations

The analysis excludes cancellation invoices, non-positive quantities, and non-positive unit prices from the primary sales dataset. Later exact duplicate records are removed using the original eight columns.

Customer-level metrics use only records with identifiable customer IDs. The dataset covers 1 December 2010 to 9 December 2011, so the first and last calendar months are incomplete. Duplicate removal and unusual transactions require business validation; neither automatically establishes that a record is erroneous.

The analysis does not establish profitability, campaign effectiveness, or causal relationships.

### 6. Conclusion

The analysis identifies strong UK market concentration, a substantial contribution from frequent identifiable customers, and a product-ranking sensitivity associated with an unusually large transaction. These findings provide a practical basis for further investigation and evidence-based commercial decisions.
