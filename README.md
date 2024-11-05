# PROJECT-1

## Project Title: Sales Performance Analysis for a Retail Store

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
