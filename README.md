## PROJECT TOPIC: SALES -DATA-ANALYSIS
---
[Project Overview](#project-overview)

[Tools Used](#tools-used)

[Structured Query Language](#structured-query-language)

[Data Visualisation Excel](#data-visualisation-excel)

[Data Visualisation Power BI](#data-visualisation-power-bi)

### Project Overview
This project  is a comprehensive analysis of Sales Data to identify trends,patterns and oppourtunities for profit maximization,growth ,enabling data driven decision making and improved sale performance. The major purpose of this analysis is to enehance performence through Data Driven Insights. Insights to uncover in this project include;top selling products. Performance per region,monthly sales trends etc


### Tools Used

- Microsoft Excel[Download Here](https://www.microsoft.com)
- For Data Cleaning
- For Data Analysis
- For Data Visualisation on pivot Table and Dashboard.
- Structured Query language
- Power Business intelligence for data summary and visualisation
  
 ### Structured Query Language
 ```SQL
Select*from[dbo].[capstone 1]

 -----Total sales for each product----
 select sum(Quantity)as Total_sales_by_Quantity,product from[dbo].[capstone 1]  
 Group by product

 -----Number of sales transactions in each Region----
 
 select count(Quantity)as Total_sales,Region from[dbo].[capstone 1]  
 Group by Region

 -------Highest selling product by Total sales value-----
 SELECT Top 1 PRODUCT,SUM(Quantity)as Best_seller
 from [dbo].[capstone 1]
 group by product
 order by best_seller desc
 
 ------Total Revenue per product---
 select sum(Revenue)as Total_Revenue,product from[dbo].[capstone 1]  
 Group by product


 --	Monthly sales totals for the current year--
  Select orderdate, sum (Quantity) as Total_Sales 
 from [dbo].[capstone 1]
 where orderdate >= '2024-01-01'
 group by orderdate

-----5 top customers by total purchase(quantity)--
SELECT TOP 5 Customer_id,
sum(Quantity) as total_purchase
from [dbo].[capstone 1]
group by customer_id
order by 
total_purchase desc

--------5 top customers by Total purchase amount(unit price)--
SELECT TOP 5 Customer_id,
sum(UnitPrice) as total_purchase_amount
from [dbo].[capstone 1]
group by customer_id
order by 
total_purchase_amount desc

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

### Data Visualisation Excel

![Sales Data worksheet](https://github.com/user-attachments/assets/505f24e6-bda4-45bf-afdb-c96c32a346da)





![Sales data pivot 1](https://github.com/user-attachments/assets/da797fc8-298b-4fcf-a7a2-c4d3df142e64)





![Sales pivot2](https://github.com/user-attachments/assets/fd4fec96-ca10-4d9a-b174-d1399ce2667a)



![Sales Data Dashboard](https://github.com/user-attachments/assets/b0c7a855-fb62-4cab-af54-acc2e5ee6852)



![dashboard 2](https://github.com/user-attachments/assets/3f383d7c-1b4f-4f21-a0a0-77bf6c4d1dbf)


### Data Visualisation Power BI

![sales report new1](https://github.com/user-attachments/assets/88def056-2316-4148-a60b-f46eb82bc4a1)




![Sales Report new2](https://github.com/user-attachments/assets/7954dae7-4e6e-42c4-94c3-5bf72fe2dee5)












### INSIGHTS

-The top selling product is Hat
-Regional Sales overview:
-For all product the Total quantity sold is 345,000 Southern Region is the top performance region as it holds 35% of the total quantity of product sold by selling 122500 units of good
- Eastern Region holds 30% of the Total Quantity  sold with a Total sales quantity of 102500 
- Northern Region holds  18% of the Total quantity sold by selling 62500 0f goods
- Western Region is least performing Region with 17% total quantity sold by selling 52500 units,Check dashboard 2 for visuals
- 
- 


