# PROJECT TITLE :CUSTOMER-DATA-ANALYSIS
---
### Project Overview
---



### SQL
```SQL
---------------project 2 Analysis---------
-------Customer Segmentation For a Subscription Service-------

1 ---Total number of customers for each region---
select*from[dbo].[Customer Data ]

select Region, count(CustomerID) AS Total_Customer
from [dbo].[Customer Data ]
group by Region

-------or count using customer name------
select Region, count(CustomerName) AS Total_Customer
from [dbo].[Customer Data ]
group by Region

2-------Most popular subscription----
select TOP 1 SubscriptionType,
count(CustomerID)as MOST_POPULAR
FROM[dbo].[Customer Data ]
Group by SubscriptionType
order by Most_popular desc

 3-------Customers who cancelled within 6 months---
Select CustomerID
 FROM[dbo].[Customer Data ]
 WHERE DATEDIFF (Month,SubscriptionStart,SubscriptionEnd)<=6;

 ---or-----

 4------average sub. duration for all customers-----
 select AVG(datediff(day,SubscriptionStart,SubscriptionEnd)) 
 as Average_Subscription_Duration
 FROM [dbo].[Customer Data ]

 5------customers with sub. longer than 12 months----
 SELECT CustomerID FROM [dbo].[Customer Data ]
 WHERE Datediff(month,SubscriptionStart,SubscriptionEnd)>12;

 6------total revenue by sub. type---------
 select SubscriptionType, 
 SUM (Revenue) as Totalrevenue
 from [dbo].[Customer Data ]
GROUP BY SubscriptionType

 -----Top the 3 regions by subscription type----
 select*from[dbo].[Customer Data ]

SELECT Top 3 Region,
count(*) as Top_Region
from [dbo].[Customer Data ]
group by Region
order by Top_Region desc
-----or------
select TOP 3 Region,
count(SubscriptionType)as Top_Regions
FROM[dbo].[Customer Data ]
Group by Region
order by Top_Regions desc

-----Top the 3 regions by subscription Cancellation----
select TOP 3 Region,
count(*)as Region_cancellation
FROM[dbo].[Customer Data ]
where canceled=1
Group by Region
order by Region_cancellation desc
----
select TOP 3 Region,
count(*)as Region_cancellation
FROM[dbo].[Customer Data ]
where canceled=0
Group by Region
order by Region_cancellation desc


8------Total active and cancelled sub.------

Select canceled,count(*) as Total_subscriptions
from [dbo].[Customer Data ]
group by canceled
```

### Data Visualisation
---

![Customer Data1](https://github.com/user-attachments/assets/d2e1dd60-3171-4c4c-bd1f-6336ef58cf63)


![CUSTOMER PIVOT](https://github.com/user-attachments/assets/bdf91633-9976-42d1-9300-638c2ac5e472)


![Customer dashboard](https://github.com/user-attachments/assets/10945264-5b7e-43b8-8f8a-002b7b8babd1)



![Customer data 1 (1)](https://github.com/user-attachments/assets/7e868354-a8fb-4174-8803-204472ed64f0)

