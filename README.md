# Superstore-Sales-and-Profitability-Analysis
This project presents a Sales and Profitability Analysis Dashboard built using Power BI to uncover key business insights across revenue, profit, customer segments, regions, and discount strategies.The goal is to analyze performance trends and identify actionable strategies to improve profitability and operational efficiency.

## Tools used
- Power BI – Data visualization and dashboard creation
- DAX (Data Analysis Expressions) – Calculated measures and KPIs
- Excel / CSV Dataset – Data source
- Data Modeling – Relationships and transformations

## Data Source
The dataset used for this analysis is "Sample-Superstore.csv" as uploaded in these project files

## Data Cleaning
- Checked for null values and duplicates
Standardized categorical variables (Region, Segment, Shipping Mode)
Ensured correct data types (dates, numeric values)

## EDA
Distribution of Revenue, Profit, and Quantity
Trend analysis across years (2014–2017)
Comparison across:
Regions
Customer Segments
Shipping Modes
Discount levels

## Data Aalysis
```DAX
Total Revenue
Total Revenue = SUM(Sales[Sales])
 Total Profit
Total Profit = SUM(Sales[Profit])
 Total Quantity
Total Quantity = SUM(Sales[Quantity])
 Profit Margin (%)
Profit Margin = 
DIVIDE([Total Profit], [Total Revenue], 0)
 Month-over-Month Growth (MoM %)
MoM Growth = 
VAR CurrentMonth = [Total Revenue]
VAR PreviousMonth = 
    CALCULATE(
        [Total Revenue],
        DATEADD(Sales[Order Date], -1, MONTH)
    )
RETURN 
DIVIDE(CurrentMonth - PreviousMonth, PreviousMonth, 0)
```
## Findings
- Overall Performance
Total Revenue: 2.30M
Total Profit: 286.40K
Total Quantity Sold: 38K
Profit Margin: 12.47%
MoM Growth: 3.79%
- Trends Over Time
Revenue shows a steady increase from 2015 to 2017
Indicates business growth but not necessarily profit efficiency
- Regional Performance
West & East regions generate the highest revenue
South region underperforms in both revenue and profit
-  Customer Segments
Consumer segment dominates (~52.87%)
Corporate and Home Office contribute less but still significant
 -  Shipping Mode Insights
Standard Class generates the highest profit (~160K)
Same Day delivery contributes the least → high cost, low return
-  Discount Impact (Critical Insight)
No Discount → Highest Profit (~330K)
Low Discount → Reduced profit (~100K)
Medium & High Discounts → NEGATIVE profit (losses)



