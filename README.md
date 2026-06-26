# Adventure Works — Customer Segmentation & RFM Analysis

A SQL and Power BI project analysing 19,000 customers from the AdventureWorks dataset (May 2011 – June 2014). The analysis uses **RFM (Recency, Frequency, Monetary)** scoring to segment customers and identify retention and revenue opportunities.

---

## Overview

AdventureWorks is a fictional manufacturing company used as a Microsoft sample database. This project treats it as a real business problem: understanding which customers are loyal, which are at risk of churning, and where cross-selling opportunities exist.

**Business Questions:**
- Which customers are most valuable and most likely to churn?
- What product combinations are most frequently bought together?
- How do customer segments differ in spending behaviour?

---

## Tools Used
- **SQL** (Azure Data Studio) — data extraction, RFM calculation, segmentation logic
- **Power BI** — interactive dashboard and visualisations
- **Excel** — data preparation

---

## Methodology

### RFM Analysis
Customers were scored on three dimensions:

| Dimension | Definition |
|---|---|
| **Recency** | How recently did the customer make a purchase? |
| **Frequency** | How often do they purchase? |
| **Monetary** | How much do they spend on average? |

Each customer received an RFM score used to assign them to one of four segments.

---

## Key Findings

**Customer Overview**
- 19,000 total customers analysed
- Average recency: 5.80 days since last purchase
- Average frequency: 6.35 purchases per customer
- Average monetary value: $5,750 per customer
- 669 customers (3.52%) have been inactive for 12+ months

**Customer Segments**
| Segment | Count | % of Customers |
|---|---|---|
| Low Spenders | 10,190 | 53.28% |
| At-Risk | 6,730 | 35.10% |
| Loyal | 1,770 | 9.26% |
| High-Value | 340 | 1.77% |

**Top Product Combinations (Cross-Sell Opportunities)**
- Mountain Bottle Cage + Water Bottle
- Road Bottle Cage + Water Bottle
- AWC Logo Cap + Long-Sleeve Jersey

**Sales by Category**
| Category | Revenue |
|---|---|
| Accessories | $92.76M |
| Bikes | $88.39M |
| Clothing | $82.44M |

---

## Dashboard Preview
> Add a screenshot of your Power BI dashboard here.

---

## SQL Queries
See the [`AdventureWorks-Queries`](./AdventureWorks-Queries) folder for all SQL scripts used in this analysis.

---

## How to Reproduce
1. Restore the AdventureWorks database in SQL Server or Azure Data Studio
2. Run the SQL scripts in the `AdventureWorks-Queries` folder in sequence
3. Export results to Excel
4. Import into Power BI and connect to the dashboard layout

---

## Data Source
Microsoft AdventureWorks sample database (publicly available via Microsoft)
