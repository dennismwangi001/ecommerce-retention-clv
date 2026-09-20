# [Project Title]

**Industry:** [e.g., Retail / E-commerce]  
**Tools:** SQL · Python · Power BI [adjust per project]

## Business Problem
An e-commerce business wants to understand which customers are likely to churn, which are most valuable long-term, and how to prioritize retention spend — since acquiring new customers costs significantly more than retaining existing ones, but not all customers are worth retaining equally.

## Business Questions
- 1. What does the customer purchase/order pattern look like — frequency, recency, order value?
- 2. Which customers show signs of churning (long gap since last purchase)?
- 3. What is each customer's Customer Lifetime Value (CLV), and how concentrated is value among top customers?
- 4. Can we forecast expected future value/order volume for the customer base? (this is where your econometrics/forecasting differentiator shows up)
- 5. Which customer segments (by recency/frequency/value) should retention efforts prioritize?

## Data Source
UCI Online Retail II dataset — real transaction-level data from a UK-based 
online retailer, December 2009 to December 2011 (~1.07M rows). 
Source: https://archive.ics.uci.edu/dataset/502/online+retail+ii 
(CC BY 4.0, Chen 2012).

## Methodology
1. Data cleaning and preparation -
- 243,007 rows (~22.8%) had a missing Customer ID and were excluded from 
  customer-level analysis (CLV, churn, retention), since purchases cannot 
  be attributed to a specific customer without one. This is a genuine 
  limitation of the raw dataset, not an analytical choice to discard data.
- 19,494 rows are formally coded cancellations (Invoice numbers starting 
  with "C"); a further ~3,456 rows show negative quantities not coded as 
  formal cancellations, suggesting inconsistent recording of returns in 
  the source system.
- Returns/negative quantities were retained (not dropped) and netted 
  against purchases, so a customer's calculated spend correctly reflects 
  actual revenue after returns rather than gross sales alone.
- After cleaning: 824,364 rows across 5,942 unique customers form the 
  base for RFM segmentation and CLV analysis.
  - 100 customers (1.68%) had zero or negative net Monetary value (returns 
  exceeding purchases in total value) and were excluded specifically from 
  CLV ranking, since "lifetime value" is conceptually a positive-value 
  measure. These customers remain in the general RFM/behavioral analysis, 
  since the return-heavy pattern itself is a legitimate finding.
2. Exploratory analysis - [brief summary]
3. Statistical/analytical approach - [brief summary]
4. Dashboard/visualization - [brief summary]

## Key Insights
### Q2: Churn Risk & Q5: Retention Prioritization
- Customer base breakdown: Champions (1,722, 29%), Loyal Customers 
  (1,174, 20%), Needs Attention (864, 15%), Lost (1,133, 19%), Recent 
  but Low Value (621, 10%), At Risk - Was Valuable (328, 5.5%).
- 328 customers show a high-value-but-declining pattern (frequent past 
  purchases, no recent activity) — the highest-priority segment for 
  targeted retention spend, since they've already proven their value.
  
  **Sample of the RFM segmentation output** (full table: `data/processed/rfm_segments.csv`):

| Customer ID | Recency | Frequency | Monetary | RFM Score | Segment |
|---|---|---|---|---|---|
| 12347 | 2 | 8 | 5,633.32 | 11 | Champions |
| 12351 | 375 | 1 | 300.93 | 4 | Lost |
| 12352 | 36 | 13 | 1,889.21 | 10 | Champions |
| 12353 | 204 | 2 | 406.76 | 5 | Needs Attention |

## Business Recommendations
### Q2 & Q5
- Prioritize retention campaigns (personalized offers, re-engagement 
  emails) specifically on the "At Risk (Was Valuable)" segment rather 
  than broad-based retention spend — this offers the highest expected 
  return given their proven historical value.
- The "Lost" segment (19%) may warrant a lower-cost, automated win-back 
  attempt, but shouldn't receive the same resource intensity as active 
  retention efforts.

## Repo Structure
- data/        raw (not committed) and processed data
- sql/         SQL scripts for data extraction/analysis
- notebooks/   Python/R analysis notebooks
- dashboard/   Power BI/Tableau files or exported visuals
- docs/        supporting docs, data dictionary, methodology notes

## How to Reproduce
[Brief steps someone would follow to rerun this analysis]
