# Sales analysis for Adventureworks-Dashboard

### Dashboard Link : https://mcmasteru365-my.sharepoint.com/:u:/g/personal/obisakii_mcmaster_ca/ESd4JfTWDEREjf07PUxv5BYBs9Gg1VF5HkTlP8kSk2T-3Q?e=snTRCZ

## Problem Statement

This dashboard helps Adventureworks understand their sales pattern between May 1, 2011 and June 30, 2014 . To provide insights to address business challenges relating to:
Customer segmentation
Customer retention
Cross selling and upselling
Customer lifetime value estimation

### Steps followed 

- Step 1 : Loaded data into Power BI Desktop, dataset is a csv file.
- Step 2 : Open power query editor & in view tab under Data preview section, check "column distribution", "column quality" & "column profile" options.
- Step 3 : Also since by default, profile will be opened only for 1000 rows so you need to select "column profiling based on entire dataset".
- Step 4 : It was observed that in none of the columns errors & empty values were present except column named "Arrival Delay".
- Step 5 : In the report view, under the view tab, theme was selected.
- Step 6 : Total sales, total customers, average frequency and average recency were calculated at 109.85M, 19,000, 6.35 and 5,80 respectively represented by card visuals 
- Step 7 : Percentage of customers without any purchase in the last 12 months was calculated at 3.52% 
- Step 8 : Line charts were introduced to illustrate Recency by customers and  monetary value by recency.
- Step 9 : Column charts, donut and pie charts were also used to determine customer segmentations; decline or increase in monetary value frequency and recency 
- Step 10 :  Customer Segmentation
                    •	19K total customers
                    •	53.28% (10.19K customers)low spenders, 35.1%(6.73K) at risk, 9.26% (1.77K)loyal, 1.77%(340 customers) high value
                    •	669 customers without purchase in the last 12 months
                    •	Average recency: 5.80
                    •	Average monetary value: 5.75K
                    •	Average frequency: 6.35

- Step 11 : Product Performance
            •	Top products frequently bought together: 
                 * Mountain Bottle Cage & Water Bottle - 30 oz.
                 * Road Bottle Cage & Water Bottle - 30 oz.
                 * AWC Logo Cap & Long-Sleeve Logo Jersey L
 
            •	High frequency boughtproducts: Mountain Bottle Cage, Water Bottle - 30 oz., Road Bottle Cage, AWC Logo Cap, Sport-100 Helmet Blue, 
                                             Sport-100 Helmet Black, HL Mountain Tire and Mountain Tire Tube.
 
            •	Total sales by product categories: Accessories (35.19%), Bike (33.53%), Clothing (31.28%)
            •	Total sales: Accessories ($92.76M), Bike ($88.39M), Clothing ($82.44M)
