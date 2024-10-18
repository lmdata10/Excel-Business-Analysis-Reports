# Basics
- Excel building blocks include sheets, cells, rows, columns, the ribbon menu, and the formula bar.
- An Excel workbook is saved with the extension `*.xlsx`.
- The most commonly used operations in Excel are **filtering**, **sorting**, and **conditional formatting**.
- For writing a formula in a cell, start with the `=` sign.
- Use the **Format Painter** tool to copy and paste formats.
- Formulas covered: `SUM()`, `AVERAGE()`, `IF()`, `SUMIF()`.
- Locking referenced cells in a formula **helps prevent dynamic changes** when the formula is copied or moved to another cell.
- To lock a column or row reference, put a **`$`** in front of it. You can also use the **F4 key** to do the same.
- You have the **flexibility to lock** either rows, columns, or both.
- **Named Ranges** allow calculations using descriptive names rather than cell references.
- Formulas will be automatically applied to **new rows**.
- Additional features such as **slicers**, **automatic totals**, and **filters** are available in Excel Tables.
- **Table headers remain visible** when scrolling down, which is useful for large tables.
- The **Recommended Charts** feature in Excel suggests the most appropriate charts based on the selected data.
- Converting data into tables allows the automatic addition of new data to charts.
- The **UNIQUE** function extracts unique values from a range or array.
- **Merge & Centre** option combines multiple cells into one cell and centers the content horizontally within the merged cell.
- **Format Painter** quickly copies and applies cell formatting to other cells or ranges in your spreadsheet.
- **Format Cells** dialog box helps you customize cell appearance and behavior in your spreadsheet.
- **Wrap text** lets you display the cell contents over multiple lines instead of one.
- Excel provides several **security features** to help protect your spreadsheet from unauthorized access or modification.

# Cleaning & Combining Data
- **Data cleaning** is an important step in the data analysis process because it ensures that the data is accurate and reliable.
- The `TRIM()` function eliminates extra spaces in the text, including those at the start and end.
- **Conditional Formatting** helps to identify and highlight duplicate data in a range of cells.
- The **Text to Columns** feature helps to split a single cell containing text into multiple cells based on a specified delimiter, such as a comma, semicolon, or space.
- The **VLOOKUP** function is used to look up a value in a table by searching for a corresponding value in the leftmost column of another table.
- Syntax of the `VLOOKUP` function: `VLOOKUP(lookup_value, table_array, col_index_num, [range_lookup])`
- Simple Definition: `=VLOOKUP (value to look for, range to look in, column number of the value to return, approximate or exact match [TRUE/FALSE])`
- Some **limitations** of VLOOKUP:
  - It searches only the first column of a reference table for a matching value.
  - Adding a new column to the reference table can cause errors by shifting column indexes and changing the referenced columns.
- `INDEX()` and `MATCH()` are two powerful Excel functions that are often used together to search for and retrieve data from a table or range.
- Syntax of the `INDEX()` function: `=INDEX(array, row_num, [column_num])`
- Syntax of the `MATCH()` function: `=MATCH(lookup_value, lookup_array, [match_type])`.
- Writing **INDEX MATCH** Formula: `=INDEX(Return Range, MATCH(Lookup Value, Lookup Range, 0))`

# Business Maths & Statistics
- Business Knowledge + Business Math & Statistics = KPIs (Key Performance Indicators)
- Formulas covered: `IF()`, `SUM()`, `SUMIF()`, `COUNT()`, `COUNTIF()`, `AVERAGE()`.
- **Null values** can be handled in different ways based on the business situation:
  - Delete that data
  - Replace with the mean or median value
- Revenue - Budget = **Profit/Loss**
- **Budget** is the baseline for calculating the Profit/Loss percentage.
- **Market Value**: Total revenue of all the movies.
- **Market Share**: The revenue contribution of a particular industry to the overall market value.
- **Target**: Estimated revenue for a particular time period.
- Use conditional formatting to highlight values that are above or below a certain threshold.
- **Mean** - Synonym for Average.
- **Median** - Middle value of a dataset when it is ordered in ascending order.
- If the dataset has an even number of values, the median is the average of the two middle values.
- **Mode** - Most frequently occurring data value.
- **Variance** is a measure of how spread out a distribution is. It is calculated as the average of the squared differences from the mean.
  - The smaller the variance, the less spread out the data is. Conversely, the larger the variance, the more spread out the data is.
- Standard deviation is a measure of the amount of variation or dispersion of a set of values. It is calculated as the square root of the variance.
  - The smaller the standard deviation, the closer the data points are to the mean. Conversely, the larger the standard deviation, the more spread out the data points are.
- **NOTE** The stock market's volatility is the best use case for variance and standard deviation.
- **Correlation** is a statistical measure that shows the degree to which two variables are related.
  - A correlation coefficient can range from -1 to 1: -1 (perfect negative correlation) < 0 (no correlation) < 1 (perfect positive correlation).

# Data Transformation using Power Query
- Power Query simplifies data cleaning and transformation compared to using Excel formulas.
- Power Query uses M-language internally for all the steps performed using the UI controls.
- **NOTE:** It is advisable to give meaningful names to the transformation steps in Power Query.
- In Power Query, you can perform various types of joins between tables based on your specific requirements.
- To quickly check the quality status of columns, use the "view" option.
- **Unique** values are values that appear only once in the data.
- **Distinct** values are values that appear at least once in the data.
- A **Conditional column** allows you to add a column to your table based on a specific condition or set of conditions.
- A **Custom column** allows you to add a new column to your table using a formula that you define. This formula can reference other columns in your table and perform calculations or manipulations on their values.

# Business Reports using Pivot Table & Power Pivot
- As a Data Analyst, Pivot tables are going to be your best friend.
- You can insert a Pivot table either in the same worksheet or in a new worksheet.
- Pivot tables make it easy to summarize data.
- Pivot tables allow you to slice and dice data in any format you want.
- To create a pivot table, follow these steps: Insert › Pivot Table › Select the table range › Create Pivot Table.
- You can use the recommended pivot table for several use cases.
- Pivot tables allow you to sort data based on different values.
- You can make pivot tables more presentable by using formatting and other options.
- Pivot tables are very similar to the matrix visualizations that you will use in BI tools.
- **Power Pivot** is a data modeling tool for Microsoft Excel. It allows users to create relationships between tables and perform advanced calculations with large amounts of data.
- To create measures, we can use the **DAX** (Data Analysis Expression) language.
- **Primary key**: It is a column or combination of columns that uniquely identifies each row in a table.
- **Foreign key**: It is a column or combination of columns that refers to the primary key of another table and establishes a link between the two tables.
- In accounting, **negative** values are represented using **brackets**.
- To highlight interesting data points, use **conditional formatting**.

# Sales & Finance Analysis
- **ETL** stands for **Extract, Transform, Load**. It refers to the process of extracting data from various sources, transforming the data to fit the desired data model or format, and loading the data into a target data store or destination.
- **Power Query** transforms and connects data from different sources, such as databases and spreadsheets, into a format suitable for analysis and reporting.
- **Data cleaning** in Power Query involves the process of identifying and correcting inaccuracies, inconsistencies, and errors in data to ensure that it is accurate and usable for analysis and reporting.
- Giving proper **names** to **Power Query steps** can make your queries more organized and easier to understand.
- **Data modeling** involves the process of connecting different data sets together by establishing the relationships between them.
- The **Star schema** is a data modeling technique that arranges data into a central fact table, surrounded by several dimension tables.
- A **Calendar Year** is a 12-month period starting from January and ending on December 31st.
- A **Fiscal Year** is a 12-month period used by organizations for accounting and financial reporting purposes, which can begin on any date.
- A **Pivot Table** is a powerful tool that allows you to summarize and analyze large amounts of data quickly and easily.
- The `CALCULATE()` function allows you to apply filters to your data and perform calculations based on those filtered results.
- The basic syntax of the `CALCULATE()` function is: `CALCULATE(expression, filter1, filter2, ...)`.
- **Designing** User Empathetic Reports requires giving significant consideration to User Readability and Time to Action.
- **Conditional Formatting** helps to format cells based on specific conditions or criteria. It helps to highlight important data, identify trends, and improve data readability.
- A **P&L (profit and loss)** statement is a financial report that provides an overview of a company's financial performance over a period of time, typically a month, quarter, or year.
- P&L statements include several critical metrics, such as **Net Sales**, **Cost Of Goods Sold (COGS)**, **Gross Margin**, **Gross Margin %**, etc. These metrics evaluate a company's financial performance, profitability, and pricing tactics.
- The `FORMAT()` function is used to format a number or a date/time value into a specific format.
- The syntax for the `FORMAT()` function is: `FORMAT(value, format_text)`.
- The `MONTH()` function is a date and time function used to extract the month number from a date.
- The `ROUNDUP()` function is used to round a number up to a specified number of digits.
- The syntax for the `ROUNDUP()` function is: `ROUNDUP(number, num_digits)`.

# Cheatsheet
**LOOKUP Functions**
- `VLOOKUP()`: Used to search for a value in the first column of a range and return a value in the same row from another column.
- `HLOOKUP()`: Horizontal lookup for data arranged horizontally.
- `INDEX() & MATCH()`: More flexible and powerful alternative to VLOOKUP, allowing for dynamic row/column lookups.
- `XLOOKUP()`: Combines the functionalities of VLOOKUP, HLOOKUP, and INDEX/MATCH.

**Statistical Functions**
- `AVERAGE()`, `MEDIAN()`, `MODE()`: Basic statistical functions.
- `STDEV.P()`, `STDEV.S()`: Standard deviation for population and sample.
- `COUNT()`, `COUNTA()`, `COUNTBLANK()`: Counting functions for non-empty, empty, and blank cells.
- `COUNTIF()`, `COUNTIFS()`: Count cells that meet one or multiple criteria.

**Text Functions**
- `LEFT()`, `RIGHT()`, `MID()`: Extract substrings from text.
- `LEN()`: Count the number of characters in a string.
- `TRIM()`: Remove extra spaces from text.
- `CONCATENATE() / CONCAT()`: Combine text from multiple cells.
- `TEXT()`: Format numbers as text within a string.
- `FIND()`, `SEARCH()`: Locate the position of a substring within a text.

**Date and Time Functions**
- `TODAY()`, `NOW()`: Current date and time.
- `DATE()`, `TIME()`, `YEAR()`, `MONTH()`, `DAY()`, `HOUR()`, `MINUTE()`, `SECOND()`: Deconstruct and manipulate date/time values.
- `DATEDIF()`: Calculate the difference between two dates.
- `NETWORKDAYS()`, `WORKDAY()`: Calculate the number of working days or determine a future/past workday.

**Logical Functions**
- `IF()`: Basic logical test.
- `IFS()`: Multiple conditions.
- `AND()`, `OR()`, `NOT()`: Combine multiple logical tests.
- `IFERROR()`, `IFNA()`: Error handling functions.

**Mathematical Functions**
- `SUM()`, `SUMIF()`, `SUMIFS()`: Summing functions with or without conditions.
- `PRODUCT()`: Multiply a range of numbers.
- `ROUND()`, `ROUNDUP()`, `ROUNDDOWN()`: Control the precision of numerical results.
- `ABS()`: Return the absolute value.
- `RANDBETWEEN()`: Generate random numbers within a range.

**Data Analysis Functions**
- `PIVOT TABLES`: Summarize large datasets dynamically.
- `SLICER`: Visual filtering in pivot tables and charts.
- `GETPIVOTDATA()`: Extract specific data from pivot tables.
- `SUBTOTAL()`: Calculate subtotals in a range, considering filters.

**Advanced Formulas and Techniques**
- Array Formulas: Perform multiple calculations on one or more of the items in an array (e.g., `{=SUM(A1:A10*B1:B10)}`).
- Conditional Formatting: Automatically format cells based on certain criteria, crucial for highlighting trends and outliers.
- Data Validation: Create drop-down lists and ensure data integrity by setting validation rules.
- Dynamic Named Ranges: Use dynamic ranges in formulas that adjust as your data grows.
- Power Query: Automate data import, cleaning, and transformation.
- Power Pivot: Handle large datasets, create complex relationships, and perform advanced calculations.

**Tips and Tricks**
- Use Tables for Dynamic Ranges: Convert ranges to tables to automatically adjust formulas as data grows.
- Advanced Filtering: Use advanced filters to extract specific data subsets based on complex criteria.
- Audit Formulas: Use tools like Trace Precedents/Dependents and Evaluate Formula to debug complex formulas.
- Data Validation with Dynamic Lists: Create dynamic drop-down lists that update as your data changes.
- Combine Multiple Excel Files: Use Power Query or VBA to consolidate data from multiple workbooks automatically.
- Quick Analysis Tool: Select data and use this tool for instant access to common analysis options like charts, pivot tables, and conditional formatting.

**Dashboarding and Visualization**
- Sparklines: Tiny charts within a cell to provide a quick visual summary of data trends.
- Dynamic Charts: Create charts that automatically update as new data is added.
- Interactive Dashboards: Combine slicers, pivot tables, and charts to create interactive dashboards.
