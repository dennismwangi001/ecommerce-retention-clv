# [Project Title]

**Industry:** [e.g., Retail / E-commerce]  
**Tools:** SQL · Python · Power BI [adjust per project]

## Business Problem
[1-2 paragraphs: what real business challenge does this address, and why 
does it matter to the business? Not "predict X" - frame it as a decision 
someone in the company needs to make.]

## Business Questions
- [Question 1]
- [Question 2]
- [Question 3]

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
2. Exploratory analysis - [brief summary]
3. Statistical/analytical approach - [brief summary]
4. Dashboard/visualization - [brief summary]

## Key Insights
- [Insight 1 - tied to a number/finding, not vague]
- [Insight 2]
- [Insight 3]

## Business Recommendations
- [Recommendation 1 - tied directly to an insight above]
- [Recommendation 2]

## Repo Structure
- data/        raw (not committed) and processed data
- sql/         SQL scripts for data extraction/analysis
- notebooks/   Python/R analysis notebooks
- dashboard/   Power BI/Tableau files or exported visuals
- docs/        supporting docs, data dictionary, methodology notes

## How to Reproduce
[Brief steps someone would follow to rerun this analysis]
