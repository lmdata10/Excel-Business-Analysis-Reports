# AtliQ Hardware Business Analysis Report
---

# Introduction

In today's data-driven business world, effective sales data analysis is crucial for success. This guide walks through dynamic sales data analysis using Excel, from data extraction and transformation to building interactive pivot tables.

## **Extract, Transform, Load (ETL)** forms the foundation of our analysis workflow.

![ETL](/Assets/1-atliq-ETL.png)

#### Extracting the Data

1. Navigate to **Data > Get Data > From Folder**
2. Upload the folder containing CSV files:
    - `fact_sales_monthly.csv`
    - `dim_product.csv`
    - `dim_market.csv`
    - `dim_customer.csv`

#### Transforming the Data with Power Query
- Create references for each file from the uploaded folder
- Set each reference as a source
- Ensure column headers are correctly recognized (use **"Use First Row as Headers"** if needed)

#### Data Cleaning Tips

Remember, real-world data is often messy. Here's a quick checklist for data cleaning:
- Check Column Distribution and Quality
- Remove duplicates
- Find and replace incorrect values
- Eliminate missing values and errors (like `#NA`)
- Verify unique columns in dimension tables
- Double-check spellings    

> [!TIP]
> ***Pro Tip***: Give proper names to your Power Query steps. It makes your queries more organized and easier to understand!

### Data Modeling: Connecting the Dots

With clean data in hand, it's time for data modelling:
- Go to **PowerPivot > Manage > Diagram View**
- Connect datasets by establishing relationships

We're using the Star schema, a data modeling technique that arranges data into a central fact table surrounded by several dimension tables.

### Creating a Date Dimension Table

To enhance our analysis, let's create a date dimension table in Power Query:

1. Create a new query named `dim_date`.
2. Insert date range: `= {Number.From(#date(2018,9,1)) ..Number.From(#date(2021,8,1)) }`
3. Change type to Date, then Insert Start of Month, and Year

### Setting Up Fiscal Year

AtliQ Hardware follows a fiscal year from September through August. Here's how to set it up:

1. Create a custom column for *FY Month*: `= Date.AddMonths ([month],4)`
2. Create a custom column for *FY*: `= Date.Year ([FY Month])`
3. Remove the *inserted Year* column and the *FY month* custom column.

Update your data model with the new `dim_date` connections.

![datamodel](/Assets/2-atliq-datamodel.png)
## Building the Report

### **Creating Dynamic Measures**

1. Insert a Pivot Table from the Data Model.

2. Create custom measures for dynamic calculations:
    * Net Sales: `=SUM(fact_sales_monthly[net_sales_amount])`
    * NetSales 19: `=CALCULATE([Net Sales],dim_date[FY]="2019")`
    * NetSales 20: `=CALCULATE([Net Sales],dim_date[FY]="2020")`
    * NetSales 21: `=CALCULATE([Net Sales],dim_date[FY]="2021")`
    * 21 vs 20: `=DIVIDE([NetSales 21],[NetSales20],0)`

3. Format measures to display values in millions: `0.0,,"M"`

### Designing Your Report

* Keep it clean and professional.
* Use conditional formatting to highlight key points.
* Add headers and company logo.
* Apply appropriate borders and formatting

	![](/Assets/3-atliq-net_sales_report1.png)
	
	![](/Assets/4-atliq-net_sales_report2.png)


### Market vs Target Analysis

The business owner requested a market vs target report. Here's how to incorporate it:

1. Add the new target data and update your data model.
    ![](/Assets/5-atliq-datamodel_updated.png)

2. Create new measures:
    * target 21: `=SUM(ns_targets_2021[ns_target])`
    * 2021 - Target: `=[NetSales 21]-[target 21]`

3. Format both to display in millions.

**Market Performance**

![](/Assets/6-atliq-market_performance.png)

---
### Key Business Insights

To round off our analysis, let's answer some crucial business questions:

1. **Top 10 Products:** Based on percentage increase in net sales from 2020 to 2021

	![](/Assets/7-atliq-insights1.png)
    
2. **Division Report:** Net sales data for 2020 and 2021 with growth percentage

    ![](/Assets/8-atliq-insights1.png)

3. **Quantity Analysis:** Top 5 and bottom 5 products by quantity sold

	![](/Assets/9-atliq-insights3.png)
    
4. **New Products:** Products with 0% in the "21 vs 20" column (new in 2021)

	![](/Assets/10-atliq-insights4.png)    
    
5. **Top 5 Countries:** By net sales in 2021

    ![](/Assets/11-atliq-insights5.png)

---
## Finance Analysis

Building on the sales analysis foundation, this section explores financial analytics to uncover deeper business insights through P&L reporting.

### P&L Fundamentals

**Profit and Loss (P&L) Statement:** This is the MVP of financial reports. It gives you a snapshot of a company's financial performance over a specific period - could be a month, quarter, or year.

**Key Metrics:** These metrics are essential for evaluating financial health, profitability, and pricing strategies.
	- Net Sales
	- Cost of Goods Sold (COGS)
	- Gross Margin
	- Gross Margin %


#### Adding Financial Data

1. First things first, we need to import our `fact_sales_monthly_with_cost` CSV file. This is where the ETL magic happens!

2. After loading the file, I noticed it's pretty similar to our existing `fact_sales_monthly` data, but with two new columns: `freight_cost` and `manufacturing_cost`.

3. Instead of doing a full-on join (which crossed my mind), I decided to simply add these two columns to our existing `fact_sales_monthly` table. Work smarter, not harder, right?

4. Time for some Power Query acrobatics:
    * Renamed `fact_sales_monthly_with_cost` to `finance ref`
    * Updated the source of `fact_sales_monthly` to `=#"finance ref"`
    * Cleaned up unnecessary steps (source, navigation, and imported CSV) steps!
    * Renamed our updated table to `fact_sales_monthly_with_cost`
    
    ![](/Assets/12-atliq-financial1.png)

5. Organize queries for clarity

    ![](/Assets/13-atliq-financial12.png)

6. Checked our data model, and voilà! `freight_cost` and `manufacturing_cost` are now in the house.
    
    ![](/Assets/14-atliq-financial3.png)


### P&L by Year

1. Jumped into Power Pivot and created a new column for `total_cogs`
	`= fact_sales_monthly[freight_cost] + fact_sales_monthly[manufacturing_cost]`

2. Create new measures:
    * COGS: `=SUM(fact_sales_monthly[total_cogs])`
    * Gross Margin: `=[Net Sales] - [COGS]`
    * Gross Margin %: `=DIVIDE([Gross Margin], [net sales], 0)`

3. Formatted our numbers into millions.

4. For year-over-year comparisons, I went old school with Excel formulas:  
    `21 vs 20 = IFERROR(F10/E10, "")`

> [!TIP]
> Use IFERROR to handle potential errors gracefully.

Some humour to support our Old School Excel Formulas (Skipping DAX) 
    *Me: Spends 1 week working on DAX*
    
    ![](/Assets/15-atliq-dax-meme.jpeg)

6. Apply conditional formatting with three-color scales and data bars

Here's a sneak peek at our P&L by Fiscal Year report:

![](/Assets/16-atliq-P&L.png)

### P&L Months and Quarters

Did you know that fiscal years can be different from calendar years? At AtliQ, the fiscal year starts in September. So, we need to find a solution in Power Pivot:

1. Add new columns:
    * mmm: `FORMAT([date], "MMM")`
    * fy_month_no: `MONTH(DATE(YEAR([date]), MONTH([date])+4, 1))`
    * quarter: `"Q" & ROUNDUP([fy_month_no]/3, 0)`

2. Sort our months by `fy_month_no` to keep everything in fiscal order.

3. Create P&L reports for FY 2019, 2020, and 2021.
    
    ![](/Assets/17-atliq-P&L-fiscal_months.png)

**Check out this beauty - our P&L by Quarters report:**
	
![](/Assets/18-atliq-P&L-fiscal_quarter.png)


### Additional Reports

**P&L for Markets (Countries):** Analyze financial performance across different geographical markets.

![](/Assets/19-atliq-P&L-markets.png)

**Gross Margin % by Quarters (Sub Zones):** Track profitability trends across quarters and sub-zones.

![](/Assets/20-atliq-P&L-subzone.png)

---
## Conclusion

This comprehensive analysis transforms raw data into actionable insights for strategic decision-making. The power of these reports lies not just in the numbers, but in the business stories they reveal. Use these insights to drive strategy and improve overall financial performance.

**Next Steps:** Continue exploring advanced analytics techniques to further enhance your data-driven decision-making capabilities.