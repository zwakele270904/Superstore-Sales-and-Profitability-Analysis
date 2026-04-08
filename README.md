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
``

