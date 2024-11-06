# PROJECT-1

# Project Title: Sales Performance Analysis for a Retail Store

## Outline
[Project Overview](#project-overview)

[Data Description](#data-description)

[Methodology](#methodology)

[Dashboard Overview](#dashboard-overview)

[Exploratory Data Analysis](#exploratory-data-analysis)

[Insights Generation](#insights-generation)

[Conclusions](#conclusions)

[Recommendations](#recommendations)


## Project Overview
This data analysis project aims to generate insight into the sales performance of a retail store by exploring the sales data to uncover key insights such as regional performance, and monthly sales trend. By analyzing the various parameters in the data received, we seek to  gather enough insights to make reasonable decisions which then enable us to tell compelling stories around our data from the insight gotten and to know the best performance from our data. More so, we are able to figure out what is working, what is not working and what should be focused on.

## Data Description
The dataset includes the following fields:
- **OrderID**: A unique identifier of each order.
- **CustomerID**: A unique identifier for each customer making the purchase.
- **Product**: The specific product purchased in each order.
- **Region**: The geographical area or region where the order was placed or delivered.
- **Order Date**: The date when the order was placed.
- **Quantity**: The number of units of the product ordered in each transaction. 
- **Unit Price**: The price per unit of the product.

 ### Basic Statistics About The Dataset
- **Total Sales Revenue**:$2,101,090
- **Total Quantity Sold**: $68,461
- **Number of Unique Customers**: 500
- **Number of Product**: 6

## Methodology
### Tools Used
#### Microsoft Excel
- For Data Cleaning
- For Analysis 

#### SQL-Structured Query Language
- For Querying of Data
- For Analysis

#### PBI-Power Business Intelligence
- For Visualization

### Data Collection
The dataset for this analysis was provided by LITA Incubator Hub, an initiative that has the vision of empowering ladies across Africa through technology, equipping them with the skills to thrive in the digital age. The data was provided in excel format, making it accessible for analysis.

### Data Manipulation
1 **Data Cleaning**
- Checked for spelling errors, duplicate values, and blank cells.
- Ensured data quality by removing duplicate entries.

2 **Data Importing**
- **Importing Data Into SQL**: The data which was in Excel format was converted to a CSV file. To import the data into SQL, I used SQL Server Management Studio(SSMS). A database was created named CAPSTONE using the following command: ```CREATE DATABASE CAPSTONE PROJECT ``.
The CSV file was then imported by right-clicking on the database created, going to tasks, going to import flat files, browse the file, clicking on next, and then finishing. The file was scanned through before importing. It was then viewed in SQL by using the following command: ```Select * from SalesData```

- **Importing Data Into Power BI**: For Power  BI, the file was imported by selecting the Get Data option and choosing Excel workbook. The file was searched for in my files and taken to the transform workshop before loading.
      
3. **Data Transformation**
- Ensured all data fields were assigned the correct data types, with numerical fields formatted as currencies where appropriate, and date fields set to date format.
- **Created New column**: A new column was added to get the revenue generated for each quantity of product sold per transaction by multiplying the quantity sold by the unit price.

 ## Dashboard Overview
![Sales Perform Analysis](https://github.com/user-attachments/assets/8ff8b134-9f78-4b49-9884-f4aecacc6a8f)

## Exploratory Data Analysis 

### Excel
The pivot table in Excel was used to summarize and analyze the dataset to generate some interesting reports.
- Total Revenue  by Product
- Total Revenue by Region
- Total Quantity Sold by Product
- Total Quantity Sold by Region
- Total Sales by Order Date
  
![Pivot Tables(Excel)](https://github.com/user-attachments/assets/97057a46-9aef-4fc1-b8e4-648aef41f043)

### SQL
Some SQL queries were written to extract key insights from the retail store’s data. The goal was to analyze sales performance, identify trends, and support decision-making through these insights. They are:
- The total sales for each product category.
- The number of sales transactions in each region.
- The highest-selling product by total sales value. 
- Calculate total revenue per product. 
- Calculate monthly sales totals for the current year. 
- Top 5 customers by total purchase amount. 
- Calculate the percentage of total sales contributed by each region. 
- Identify products with no sales in the last quarter.
  
  ```SQL
  select Product, sum(Quantity) as [Total Sales For Each Product] from [dbo].[CAPSTONE] Group by Product

![SQL query1](https://github.com/user-attachments/assets/3a193074-d5e8-493e-9776-800113cf94aa)

```
select Region, count(OrderDate) as [Number of Sales Transaction In Each Region] from [dbo].[CAPSTONE] Group by Region
```
![SQL query 2](https://github.com/user-attachments/assets/3add88e1-02cd-4c74-ad63-a284c12e1895)

  ```SQL
  select top 1 Product, sum(Quantity) as [Highest Selling Product] from [dbo].[CAPSTONE] Group by Product
```
![SQL query3](https://github.com/user-attachments/assets/fad897b1-d211-4820-bbe7-31bedd2b0ed7)

```SQL
select Product, sum(TotalSales) as [Total Revenue For Each Product] from [dbo].[CAPSTONE] Group by Product
```
![SQL query4](https://github.com/user-attachments/assets/9ab0f988-5572-46ec-b704-16eabf091661)

  ```SQL
  select month(OrderDate) as Month, sum(TotalSales) as [Monthly Sales] from [dbo].[CAPSTONE] where year(OrderDate)='2024' 
group by Month(OrderDate) order by Month
```
![SQL query5](https://github.com/user-attachments/assets/b39b2e06-f46c-4df2-868b-2cf7b91b480a)

```SQL
select top 5 TotalSales, customer_id from [dbo].[CAPSTONE] Order by TotalSales desc
```
![SQL query6](https://github.com/user-attachments/assets/2fcbbccb-460e-40f0-ad27-1952d4463293)

  ```SQL
  select Region, sum(totalsales) as [Total Sales of Region], sum(TotalSales)*1.0/(select sum(TotalSales) from [dbo].[CAPSTONE]) *100 
as [Percentage of Total Sales] from [dbo].[CAPSTONE] group by Region
```
![SQL query7](https://github.com/user-attachments/assets/b82620e0-50f0-4422-8b7b-84fe641248e8)

### Power BI
The Power BI was used to create an interactive dashboard that visualizes the insights gained from the sales data analysis. The dashboard provides an overview of sales performance in 2023 and 2024, highlights total revenue and top-selling products, and breaks down sales by product and region. Some visuals used were a Bar Chart, Line Chart, Pie Chart, and Visual Card.

- **Below is a dashboard of the overview of sales performance in 2023**
  
![Screenshot (22)](https://github.com/user-attachments/assets/0b01397f-b263-4b5e-a2e4-49cf204c6ed9)

- **Below is a dashboard of the overview of sales performance in 2024**
  
![PBI 2024](https://github.com/user-attachments/assets/e5363129-c670-4046-a592-86f34bb724ba)



## Insights Generation
1. **Regional Revenue Contribution:**
- The South region contributed the highest revenue at 44% of total revenue, nearly half of the total revenue. This suggests a strong demand for effective sales strategies in this region.
- The West region generated the least revenue at 14% of total revenue, indicating potential room for growth.

2. **Product Revenue and Quantity Analysis:**
- Shoes brought in the most revenue across all regions with a total of 614,380, followed by shirts, gloves, and jackets.
- Although shoes had the highest revenue, hats had the highest quantity sold, suggesting hats might be priced lower than shoes but sell in larger volumes.
- Shoes are popular in the South, shirts in the North and East, and hats in the West, indicating distinct regional preferences for specific products.
- Socks have low sales in the South region with no sales in other regions except in the West. This suggests that socks are either not a preferred item in other regions or they lack visibility in those markets.
- Gloves perform best in the South region but have minimal sales in the North, and are completely absent in the West and East regions. This suggests that gloves may not align with customer preferences or needs outside the South.
- Shirts had the highest revenue contribution in 2023, indicating strong demand initially, but saw a notable decrease in revenue in 2024. This could reflect changes in consumer preferences, price adjustments, or increased competition.

3. **Monthly Sales Trends:**
- February had the highest sales within the two years, possibly due to seasonal demand, promotions, or other cyclical factors.
- Notably, July 2023 had strong sales, while July 2024 saw a decline, indicating potential challenges in maintaining momentum year-over-year.
- East region was the second highest revenue generator in 2023 but experienced a sharp revenue decline in 2024, along with a reduction in total product quantity sold. This suggests potential market saturation, economic shifts, or competition impacting sales in this region.
- The north region also saw a reduction in product quantity sold from 2023 to 2024, though without as sharp a revenue decline as the East.


## Conclusions
1. The South region is a key revenue driver with high sales in both revenue and quantity. This region’s preference for shoes and strong purchasing power has significantly boosted overall revenue. However, there is a complete lack of hats, jackets, and shirts demand in this region. This might indicate either a lack of demand or gaps in inventory and distribution.
2. Shoes, as the top revenue generator, play a critical role in the sales strategy across all regions, while hats are essential for volume sales, especially in the West.
3. Monthly sales patterns suggest certain months may have promotional opportunities, such as February, which could be leveraged more across other months to balance sales and mitigate dips in months like July and April.
4. The East region’s drop in revenue and product sales quantity from 2023 to 2024 signals a need to address specific challenges in this area, such as shifting customer demand or increased market competition.
5. The decline in shirt sales and the corresponding rise in shoe sales from 2023 to 2024 suggest a change in customer preferences or possibly a successful strategy that promoted shoes more effectively. This could indicate a long-term trend favoring shoes, which should be monitored closely.


## Recommendations
1. Leverage the South region’s preference for shoes by introducing premium or limited edition models to further capitalize on this demand.
2. Test demands for hats, jackets, and shirts by gradually introducing these items through limited campaigns or promotions.
3. In the West, explore promotional campaigns or price incentives for has to sustain high sales volumes and consider bunding other less popular products with hats to increase overall revenue.
4. Since shoes are the most significant revenue contributor, core-regional campaigns should highlight this product, particularly in lower-performing regions like the North and West, to stimulate interest.
5. Use regional favorites as lead products in targeted marketing.
6. Given February’s success, analyze what drives these sales to replicate similar tactics in other months.
7. Address the July sales decline by introducing mid-year promotions, flash sales, or loyalty programs to maintain customer interest and spending.
8. Since hats sell in high quantities, consider slight price adjustments if possible to increase revenue from this product without affecting demand. Alternatively, explore bundling hats with other items to encourage additional purchases.
9. Since socks sell in low quantities, increase visibility and demand for socks by offering discounts on other popular items like shoes, especially in the South, North, and East regions where sales are low.
10. In the West, where there is some demand, experiment with limited-time promotions to strengthen interest and increase sales volume.
11. Implement special promotions, discounts, or product bundles in the East region to regain customer interest and boost sales.
12. Conduct a deeper analysis or customer surveys to understand the cause of declines in the products and regions and adapt strategies accoringly
