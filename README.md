# LITA_CAPSTONE_PROJECT_2
Sales Data: This is where you find the second report of my capstone project with the Incubator Hub 

## Sales Store Analysis Report

### Introduction
---

This project is tasked with analyzing the sales performance of a retail store, to gain insight such as top- selling 
products, regional performance and monthly Sales trends. 

### Data Description
---

The dataset includes the following fields:

Customer Id: The unique identity
OrderDate: Represent the transaction day
Product: Product of category
Quantity: Number of unit of product
Region: Geographical location
UnitPrice: Seling price of product

### Basic statistics about the dataset:
---

 - Total Sales: $2,101,090
 - Total QUantity Sold: 68461 items
 - NUmber of Unique Customers: 9921
 - Number of Product Category: 6


 ## Methodology:
 ---
 
### Data Collection


 The dataset for this analysis was provided by LITA under The Incubtor Hub, a Tech Skill training outfits. I received the data
 through the LMS in Microsoft Excel [ Download Here](https://www.microsoft.com)                                                      
 https://canvas.instructure.com/courses/10186984/files/folder/Portfolio%20Building%20with%20GitHub%20and%20Introduction%20to%20Power%20BI

### Data Manipulation


1. Data Cleaning:

   - Checked for spelling Errors, Duplicate Values and Blank cells: Ensured data quality by removing duplicate entries.

2. Data Transformation:

     -Data Types:Ensured that all data fields were assigned the correct data types.

    - Created new column:
      Revenue: Added new column to sum up the multiplying the quantity column by the unit price column.

      
### Tools used
---

  Microsoft SQLServer (SMSS): Used for querying 
  Download here :
  https://www.microsoft.com/en-us/sql-server/sql-server-downloads
- Microsoft Power BI  [Download Here](https://www.microsoft.com)
 
 
 
 ### Data Analysis
 ---
 Queries in SQL

 -- SQL
```
     i.SELECT Product, SUM(Sales) AS TotalSales
      FROM [dbo].[SALES RECORDS 1]
      GROUP BY Product;
 ```
---

```
     ii.SELECT Region, COUNT(*) AS NumberOfTransactions
       FROM [dbo].[SALES RECORDS 1]
       GROUP BY Region;
  ```
---

```
     iii.SELECT TOP 1 Product, SUM(Sales) AS TotalSales
        FROM [dbo].[SALES RECORDS 1]
        GROUP BY Product
```
---

```
    iv. SELECT Product, SUM(Sales) AS TotalRevenue
        FROM [dbo].[SALES RECORDS 1]
        GROUP BY Product;
 ```
---

```
     v.SELECT DATEPART(YEAR,OrderDate) AS YEAR, 
              DATEPART(MONTH,OrderDate) AS MONTH,
              SUM(Sales) AS monyhly_sales
      FROM[dbo].[SALES RECORDS 1]
      WHERE DATEPART(YEAR, OrderDate) = DATEPART(YEAR, CURRENT_TIMESTAMP)
    GROUP BY
      DATEPART (YEAR, OrderDate),DATEPART (MONTH,OrderDate)
    ORDER BY
       Year, Month;
   ```
--- 


   


### Dashboard Overview
 ---
      

       
 
![LITA PBI PROJECT 4 SALE](https://github.com/user-attachments/assets/ae104513-8676-45d0-a3e4-9f61d77f84dd)

### Insights Generation
---




![LITA_SALES_INSIGHT 1](https://github.com/user-attachments/assets/abb88d56-19d3-403f-b6ac-7f311c3782dd)




1. Revenue by Product:

The Shoes product generated the highest revenue, with approximately 613K in sales.

Shirts and Hats also performed well, bringing in 486K and 316K, respectively.

Jacket and Socks generated the lowest revenue, indicating they may be lower in demand or less profitable.







2. Revenue by Region:

South is the top-performing region, generating 927K in sales, making up the largest share of revenue.

East follows with 486K, while North and West regions trail with 387K and 300K, respectively.

The South region dominace, maybe due to higher demand or better market penetration.






3. Sales Percentage by Region:

South represents the largest portion of sales at 35.49%, while East holds 29.74%.

North and West contribute to a lesser extent, with 18.12% and 16.65%, respectively.

This distribution indicates a heavy reliance on the West region for overall sales.







![LITA_SALES_INSIGHT 2png](https://github.com/user-attachments/assets/6fbdeee7-7a82-4d24-b069-46cf7f0b6fdb)










4. Quantity Sold by Product:

Hats lead in quantity sold with approximately 15.9K units despite not bringing in the highest revenue.

Shoes and Shirt also have high quantities sold, with around 14.4K and 12.4k units.

Products like Jacket and Socks have lower quantities, aligning with their lower revenue generation.







5. Current Year Sales (by Month):

February saw the highest sales, with 299K.

Sales declined in March (55K) and April (39K) but picked up again by June (148K) and August (174K).

There is a significant fluctuation in monthly sales, which could reflect seasonality or marketing campaigns.








6. Quantity Sold by Region:

The East, North, South, and West regions all have similar quantities sold, each around 2,000 units.

This even distribution contrasts with the revenue distribution, suggesting that sales in the South region generate 
higher revenue per unit sold compared to other regions.









![LITA-SALES_INSIGHT 3](https://github.com/user-attachments/assets/d7d3c366-b591-47f0-b03e-a9c14b5299bb)









7. Revenue by Month and Year:

Sales peaked in June (247k), indicating a potential seasonal trend or successful marketing efforts.

Other months, like February and June, have significantly higher revenue.

These notable revenue spikes in February and June, may be worth investigating for future planning.




   ### Summary and Recommendations:
   ---

Product Strategy: Focus on products like Shoes, Shirts, and Hats as they generate both high revenue and quantity.
Consider promotional efforts to boost sales for low-performing products, such as Jackets and Hats.

Regional Strategy: Since the South region is a key driver of revenue, consider investing in targeted marketing campaigns 
in this area. Also, explore ways to increase profitability in the East, North, and West regions, where sales quantity 
is similar but revenue lags.

Sales Trends: The noticeable peaks in February and June may indicate seasonal demand. Analyze what drives these peaks to 
capitalize on similar trends in the future.

Revenue Optimization: Investigate why the South region achieves higher revenue per unit and explore replicating those factors 
in other regions.


This analysis can guide decision-making on product focus, regional marketing, and timing for campaigns to optimize sales and revenue.
