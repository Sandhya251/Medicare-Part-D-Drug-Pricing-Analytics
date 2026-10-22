# Medicare Part D Drug Spending Analytics

## Project Overview

This project analyzes **CMS Medicare Part D prescription drug spending data from 2020 to 2024** to understand spending trends, identify high-spending drugs, evaluate manufacturer concentration, and compare likely brand and generic drug patterns.

Using Python, SQL, and Power BI, I transformed raw data into actionable insights and built an interactive dashboard to help identify major spending drivers and areas requiring further investigation.

## Business Problem

Prescription drug spending is influenced by multiple factors, including drug utilization, pricing, competition, and manufacturer activity. However, analyzing thousands of drugs and manufacturers makes it difficult to identify the most important contributors.

The goal of this project was to answer the following business questions:

- How has Medicare Part D drug spending changed from 2020 to 2024?
- Which drugs contribute the most to total spending?
- How concentrated is spending across drugs and manufacturers?
- How do likely brand and generic drugs differ in spending patterns?
- Which drugs show meaningful growth or decline over time?
- Which products and manufacturers should be prioritized for deeper analysis?

## Tools and Technologies

- **Python:** Pandas, NumPy, exploratory data analysis, data cleaning, and validation
- **SQL:** CTEs, aggregations, `CASE` statements, window functions, `LAG`, `RANK`, and `ROW_NUMBER`
- **Power BI:** Interactive dashboards, DAX measures, KPIs, and data visualization
- **Jupyter Notebook:** Data exploration and analysis

## Dataset

- **Source:** CMS Medicare Part D data
- **Period:** 2020–2024
- **Raw dataset:** 14,500+ records and 46 columns
- **Coverage:** 3,500+ drugs and 960+ manufacturers

The dataset includes drug names, manufacturer information, spending, claims, beneficiary counts, and dosage units.

*Note: Beneficiary values may be suppressed in the source data to protect privacy. Suppressed values were treated as unavailable rather than assumed to be zero.*

## Project Workflow

### 1. Data Cleaning and Validation — Python

- Inspected the dataset structure, data types, missing values, and duplicate records.
- Standardized manufacturer names and examined inconsistencies.
- Separated drug-level aggregate records from manufacturer-level detail records to avoid double-counting.
- Validated spending consistency and checked unusual values and year-over-year changes.
- Investigated suppressed beneficiary counts and other data limitations.
- Restructured the data into a drug-year panel for time-series analysis.

### 2. Exploratory Data Analysis — Python

Explored the data to identify:

- Overall spending trends from 2020 to 2024.
- Highest-spending drugs and manufacturers.
- Claims and beneficiary patterns.
- Drug-level spending growth and decline.
- Spending concentration and portfolio composition.
- Differences between likely brand and likely generic drugs.

Unusual growth rates were investigated rather than automatically removed, since some changes could reflect genuine product launches or market developments.

### 3. SQL Analysis

Used SQL to perform deeper analytical queries, including:

- Year-over-year spending growth.
- Drug and manufacturer rankings.
- Cumulative spending contribution.
- Top-drug and top-manufacturer concentration.
- Manufacturer-level performance and product dependence.
- Drug lifecycle classification and trend comparisons.

Window functions such as `LAG` were used to compare current-year values with previous-year values.

### 4. Power BI Dashboard

Developed a four-page interactive dashboard:

**Page 1 — Executive Summary**
- Total spending and claims
- Active drugs
- Spending trends over time
- Highest-spending drugs
- Brand and generic spending composition

**Page 2 — Drug Lifecycle and Reliability**
- Growing, declining, and stable drug patterns
- Spending concentration
- Reliable growth and decline indicators
- Utilization-related metrics

**Page 3 — Manufacturer Performance**
- Manufacturer spending and rankings
- Manufacturer concentration
- High-growth manufacturers
- Manufacturer dependence on individual products

**Page 4 — Brand vs. Generic and Price-Change Analysis**
- Brand and generic spending shares
- Year-over-year trends
- Average spending-per-unit trends
- Reliable price-change indicators

## Key Findings

### 1. Prescription Drug Spending Increased

Total spending increased from approximately **$194.1 billion in 2020 to $288.7 billion in 2024**, representing growth of approximately **48.7%** over the period.

### 2. Spending Was Concentrated Among a Small Group of Drugs

The top 10 drugs accounted for approximately **28.5% of 2024 spending**.

Drugs such as Eliquis, Ozempic, Jardiance, and Xarelto were among the major spending contributors.

**Business implication:** These drugs are strong candidates for deeper investigation into price changes, utilization, competition, and treatment patterns.

### 3. Likely Brand Drugs Accounted for a Larger Share of Spending

The estimated share of spending associated with likely brand drugs increased from approximately **76.8% in 2020 to 84.0% in 2024**.

The likely generic share declined over the same period.

**Business implication:** Further analysis could investigate whether the changing mix reflects utilization, product launches, pricing, or changes in generic competition.

### 4. Manufacturer Concentration Was an Important Area to Monitor

A relatively small group of manufacturers contributed a substantial share of spending.

**Business implication:** Monitoring major manufacturers and their high-spending products can help identify potential exposure to changes in pricing, product availability, or market position.

### 5. Reliable Growth Required Careful Validation

Percentage changes can be misleading when a drug has very few claims. Low-volume observations were therefore treated carefully when identifying reliable growth or decline.

**Business implication:** Growth indicators should be investigated alongside utilization, product launches, and competitive developments rather than interpreted in isolation.

## Business Recommendations

Based on the analysis, the following areas would be valuable for further investigation:

1. **Prioritize high-spending drugs:** Focus on products that account for a substantial share of total spending.
2. **Separate price and utilization effects:** Determine whether spending growth is associated with higher unit costs, greater utilization, or both.
3. **Monitor manufacturer exposure:** Examine major manufacturers and their dependence on individual products.
4. **Investigate brand-generic trends:** Study generic entry, competition, and changes in drug utilization.
5. **Review unusual growth and decline:** Validate significant changes before drawing business conclusions.

The dashboard is intended as a **decision-support and prioritization tool**. It identifies where further investigation may be most valuable but does not independently establish the causes of every spending change.

## Limitations

- **Brand/generic classification:** The dataset did not provide a definitive classification for every drug. Manufacturer-count rules were used as an analytical proxy, with ambiguous cases kept separate. This should not be interpreted as official CMS classification.
- **Suppressed values:** Some beneficiary counts were unavailable because of source-data suppression. These values were not treated as zero.
- **Spending versus revenue:** The analysis concerns reported prescription drug spending associated with Medicare Part D claims, not the recognized revenue of individual manufacturers.
- **Gross versus net spending:** The analysis does not establish final net costs after manufacturer rebates.
- **Patient-level analysis:** The dataset does not provide a unique patient identifier for deduplicating beneficiaries across drugs.
- **Causal interpretation:** The analysis identifies trends and associations but does not establish that a specific factor caused a change in spending.
- **Drug categories:** Therapeutic-category analysis would require additional drug-class mapping data.

## Future Improvements

- Incorporate an authoritative drug classification and therapeutic-category crosswalk.
- Add generic-entry dates and relevant patent information where available.
- Decompose spending changes into price and utilization effects.
- Extend the analysis with additional years of CMS data.
- Incorporate rebate or net-spending information if a suitable source becomes available.
- Add deeper manufacturer and competitor comparisons.



## Conclusion

This project demonstrates an end-to-end data analytics workflow, from data cleaning and validation to SQL analysis and Power BI visualization.

The analysis highlights increasing prescription drug spending, concentration among high-spending drugs and manufacturers, and changing likely brand-generic spending patterns. Most importantly, it shows how analytics can help a business identify the areas that deserve attention first and guide the next stage of investigation.

---

**Skills demonstrated:** Data Cleaning · Exploratory Data Analysis · SQL Analytics · Window Functions · Time-Series Analysis · Market Concentration · Power BI · Business Insight Generation
