# PROJECT-1

## Project Title: Sales Performance Analysis for a Retail Store

## Outline
[Project Overview](#project-overview)

[Data Description](#data-description)

[Methodology](#methodology)

[Dashboard Overview](#dashboard-overview)

[Exploratory Data Analysis](#exploratory-data-analysis)

[Insights Generation](#insights-generation)


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
- **Importing Data Into SQL**: The data which was in excel format was converted to csv file. To import the data into SQL, I used SQL Server Management Studio(SSMS). A database was created named CAPSTONE using the following command: ```CREATE DATABASE CAPSTONEPROJECT```.
The csv file was then imported by right clicking on the database created, go to taks, go to import flat files, browse the file, click on next, and then finish. The file was scanned through before importing. It was then viewed in SQL by using the following command: ```Select * from SalesData```

- **Importing Data Into Power BI**: For Power  BI, the file was imported by selecting the Get Data option and choosing Excel workbook. The file was searched for in my files and taken to the transform workshop before loading.
      
3. **Data Transformation**
- Ensured all data fields were assigned the correct data types, with numerical fields formatted as currencies where appropriate, and date fields set to date format.
- **Created New column**: A new column was added to get the revenue generated for each quantity of product old per transaction by multiplying the quantity sold by the unit price.

 ## Dashboard Overview
![Sales Perform Analysis](https://github.com/user-attachments/assets/8ff8b134-9f78-4b49-9884-f4aecacc6a8f)

## Exploratory Data Analysis 

### Excel
The pivot table in excel was used to summarize and analyze the dataset to generate some interesting reports.
- Total Revenue  by Product
- Total Revenue by Region
- Total Quantity Sold by Product
- Total Quantity Sold by Region
- Total Sales by Order Date
  
![Pivot Tables(Excel)](https://github.com/user-attachments/assets/97057a46-9aef-4fc1-b8e4-648aef41f043)

### SQL
Some SQL queries were written to extract key insights from the retail store’s data. The goal was to analyze sales performance, identify trends, and support decision making through these insights. They are:
- The total sales for each product category.
- The number of sales transactions in each region.
- The highest-selling product by total sales value. 
- Calculate total revenue per product. 
- Calculate monthly sales totals for the current year. 
- Top 5 customers by total purchase amount. 
- Calculate the percentage of total sales contributed by each region. 
- Identify products with no sales in the last quarter.
  
  ```SQL
  select Product, sum(Quantity) as [Total Sales For Each Product] from [dbo].[CAPSTONE] group By Product

![SQL query1](https://github.com/user-attachments/assets/3a193074-d5e8-493e-9776-800113cf94aa)

```
select Region, count(OrderDate) as [Number of Sales Transaction In Each Region] from [dbo].[CAPSTONE] group By Region
```
![SQL query 2](https://github.com/user-attachments/assets/3add88e1-02cd-4c74-ad63-a284c12e1895)

  ```SQL
  select top 1 Product, sum(Quantity) as [Highest Selling Product] from [dbo].[CAPSTONE] group By Product
```
![SQL query3](https://github.com/user-attachments/assets/fad897b1-d211-4820-bbe7-31bedd2b0ed7)

```SQL
select Product, sum(TotalSales) as [Total Revenue For Each Product] from [dbo].[CAPSTONE] group By Product
```
![SQL query4](https://github.com/user-attachments/assets/9ab0f988-5572-46ec-b704-16eabf091661)

  ```SQL
  select month(OrderDate) as Month, sum(TotalSales) as [Monthly Sales] from [dbo].[CAPSTONE] where year(OrderDate)='2024' 
group by Month(OrderDate) order by Month
```
![SQL query5](https://github.com/user-attachments/assets/b39b2e06-f46c-4df2-868b-2cf7b91b480a)

```SQL
select top 5 TotalSales, customer_id from [dbo].[CAPSTONE] order by TotalSales desc
```
![SQL query6](https://github.com/user-attachments/assets/2fcbbccb-460e-40f0-ad27-1952d4463293)

  ```SQL
  select Region, sum(totalsales) as [Total Sales of Region], sum(TotalSales)*1.0/(select sum(TotalSales) from [dbo].[CAPSTONE]) *100 
as [Percentage of Total Sales] from [dbo].[CAPSTONE] group by Region
```
![SQL query7](https://github.com/user-attachments/assets/b82620e0-50f0-4422-8b7b-84fe641248e8)

### Power BI
The Power BI was used to create an interactive dashboard that visualizes the nsights gained from the sales data analysis. The dashboard provides and overview of sales performance in 2023 and 2024, highlights total revenue and top selling product and breakdown sales by product and region. Some visuals used were Bar Chart, Line Chart, Pie Chart, Visual Card.

- **Below is a dashboard of the overview of sales performance in 2023**
  
![Screenshot (22)](https://github.com/user-attachments/assets/0b01397f-b263-4b5e-a2e4-49cf204c6ed9)

- **Below is a dashboard of the overview of sales performance in 2024**
  
![PBI 2024](https://github.com/user-attachments/assets/e5363129-c670-4046-a592-86f34bb724ba)



##  Insights Generation
- The top selling product based on the number of quantity and highest number of transactions sold across all regions during the last two years is hat.
- The product that generated the highest amount of revenue across all regions during the last two years is shoes.
- The region that generated the highest amount of revenue during the last two years is the South region accounting for 44% of total sales. 
- East had the highest number of transactions and highest number of quantity sold over the last two years.
- In 2023, the revenue generated was higher than that of 2024, highlighting a downward trend in sales.

