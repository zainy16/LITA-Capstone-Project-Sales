# LITA-Capstone-Project-Sales
This shows one of the two final projects I worked on while undergoing the Ladies in Tech Africa training organised by The Incubator Hub.

[Project Title](#project-title)

[Project Overview](#project-overview)

[Data Sources](#data-sources)

[Tools Used](#tools-used)

[Data Cleaning and Preparations](#data-cleaning-and-preparations)

[Exploratory Data Analysis](#exploratory-data-analysis)

[Data Analysis](#data-analysis)

[Data Visualization](#data-visualization)

### Project Title: Sales Data Analysis

### Project Overview
The aim of this project is to analyze the sales performance of a retail store for the past two years. The data was explored to unveil insights that would help in better decision-making.

### Data Sources
The data used is LITA Capstone Dataset.xslx and was provided on the LMS portal by the tutors.

### Tools Used
- Microsoft Excel- Data Cleaning and Analysis
- SQL(Structured Query Language)- Data Querying
- Microsoft PowerBI- Data Visualization
- Github- Documentation and Portfolio Building

### Data Cleaning and Preparations
The following actions were performed before the data was worked on for analysis and visualization:
1. Data loading and inspection
2. Removal of duplicates

### Exploratory Data Analysis
The data was explored to answer questions like:
- average sales per product.
- total revenue by region.
- the total sales for each product category.
- the number of sales transactions in each region.
- the highest-selling product by total sales value.
- total revenue per product.
- monthly sales totals for the current year.
- the top 5 customers by total purchase amount.
- the percentage of total sales contributed by each region.
- products with no sales in the last quarter.

### Data Analysis
Listed below are the queries I used in answering the questions:

```SQL
select [product], sum(sales) as TotalSales from SalesData
group by [product] 
order by 2 desc

select region, COUNT(sales) as Amount_of_Sales from SalesData
group by region 
order by 2 desc

select top(1) [product], SUM(sales) as TotalSales from SalesData
group by [product] 
order by 2 desc

select [product], SUM(sales) as TotalRevenue from SalesData
group by [product] 
order by 2 desc

select month(orderdate) as Months, sum(sales) as Total_MonthlySales from SalesData
where OrderDate between '2024-01-31' and '2024-12-31'
group by month(OrderDate)
order by 1asc

select top (5) Customer_Id, sum(sales) from SalesData
group by Customer_Id
order by 1desc

select region, sum(sales) as Region_Sales, sum(sales) * 100.0 / sum(sum(sales)) over () as Percentage
from SalesData
group by region 
order by 2 desc

select [Product] from SalesData where OrderDate between '2024-06-01' and '2024-08-31'
group by [Product]
having sum(sales) = 0
```

### Data Visualization

![Sales Excel](https://github.com/user-attachments/assets/50d83bff-50b7-46d4-bca3-1b11b493c375)

