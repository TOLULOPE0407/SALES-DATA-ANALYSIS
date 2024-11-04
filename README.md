## PROJECT TOPIC: SALES-DATA-ANALYSIS
---
### Project Overview


### TOOLS USED
-MICROSOFT EXCEL[Download Here](https://www.microsoft.com)
- For Data Cleaning
- For Data Analysis
- For Data Visualisation on pivot Table and Dashboard.
  
 ### SQL
 ```SQL
Select*from[dbo].[capstone 1]

 -----Total sales for each product----
 select sum(Quantity)as Total_sales_by_Quantity,product from[dbo].[capstone 1]  
 Group by product

 -----Number of sales transactions in each Region----
 
 select count(Quantity)as Total_sales,Region from[dbo].[capstone 1]  
 Group by Region

 -------Highest selling product by Total sales value-----
 SELECT PRODUCT,SUM(Quantity)as Best_seller
 from [dbo].[capstone 1]
 group by product
 order by best_seller desc
 
 ------Total Revenue per product---
 select sum(Revenue)as Total_Revenue,product from[dbo].[capstone 1]  
 Group by product


 --	Monthly sales totals for the current year--
 SELECT datepart(month,orderDate)as sales_month,
 sum(Quantity)as Monthly_Sales
 from [dbo].[capstone 1]
 group by
 datepart(Month,OrderDate)
 order by sales_month


-----5 top customers by total purchase amount--
SELECT TOP 5 Customer_id,
sum(Quantity) as total_purchase
from [dbo].[capstone 1]
group by customer_id
order by 
total_purchase desc


---percentage of Total sales contributed by each region----
Select Region,
sum (Quantity) as Regional_sales,
ROUND((sum(Quantity) * 100.0)/(select sum(Quantity)
from[dbo].[capstone 1]),1) as sales_percentage
from [dbo].[capstone 1]
group by
region
order by
Regional_sales desc

----product with no sales in last quarter----
select Product fROM[dbo].[capstone 1]
GROUP BY Product
having max(OrderDate)
<dateadd(quarter,-1,getdate());
-------or------------
select distinct product
fROM[dbo].[capstone 1]
where product not in (select product from[dbo].[capstone 1]
where orderdate>=dateadd(quarter,-1,getdate()))
```




  



 



### DATA VISUALISATION
