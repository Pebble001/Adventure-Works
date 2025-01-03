SELECT * from sales.SalesOrderHeader

/*SELECT count(CustomerID) from Sales.SalesOrderHeader*/

/*select MAX(OrderDate) from Sales.SalesOrderHeader*/

--select CustomerID, DATEDIFF(MONTH, MAX(OrderDate),'2014-06-30') as f INTO #test2 from Sales.SalesOrderHeader
group by CustomerID-- recency

SELECT * from #test2

/*select from #test2*/

 /* frequency*/

 select * from Sales.SalesOrderDetail




 /*SELECT count(SalesOrderID) as no_of_orders, SalesOrderID into #test3 from Sales.SalesOrderDetail
GROUP BY SalesOrderID*/


SELECT MAX(COUNT(SalesOrderID)) FROM Sales.SalesOrderDetail

select distinct SalesOrderID from Sales.SalesOrderDetail

--select max(no_of_orders) from #test3

--select count(SalesOrderID) as count_orders,  sum_order into #test4 from Sales.SalesOrderDetail
--GROUP BY LineTotal--

--select * from #test4

--select max(sum_order) from #test4--




/*select a.CustomerID, 

DATEDIFF (MONTH, MAX(a.OrderDate),'2014-06-30') as Recency,

CASE WHEN DATEDIFF(MONTH, MAX(a.OrderDate),'2014-06-30') between 0 and 6 then 'highrecency_customer'
      WHEN DATEDIFF(MONTH, MAX(a.OrderDate),'2014-06-30') between 7 and 12 then 'goodrecency_customer'
      WHEN DATEDIFF(MONTH, MAX(a.OrderDate),'2014-06-30') between 13 and 24 then 'fairrecency_customer'
      WHEN DATEDIFF(MONTH, MAX(a.OrderDate),'2014-06-30')  > 24 THEN 'poorrecency_customer'
      End as 'Recency_rating' ,
count(a.SalesOrderID) as Frequency,
CASE when count(a.SalesOrderID) between 1 and 5 then 'lowfrequency_customer'
     when count(a.SalesOrderID) between  6 and 10 then 'fairfrequency_customer'
     when count(a.SalesOrderID) between  11 and 15 then 'goodfrequency_customer'
     when count(a.SalesOrderID) > 15 then 'highfrequency_customer'
     End as 'Frequency_rating',

sum(b.LineTotal) as Monetaryvalue,
CASE WHEN sum(b.LineTotal) BETWEEN 1 and 1000 Then 'lowballer_customer'
      When sum(b.LineTotal)  <=5000 THEN 'Fairballer_customer'
      When sum(b.LineTotal) <=10000  then 'goodballer_customer'
      When sum(b.LineTotal)  >10000 then 'highballer_customer'
 End as Monetary_Rating     
      
into #RFM      
from sales.SalesOrderHeader a
Inner JOIN Sales.SalesOrderDetail b

on a.SalesOrderID = b.SalesOrderID

GROUP BY a.CustomerID
ORDER BY Monetaryvalue DESC*/

select *
FROM #RFM
ORDER BY MONETARYVALUE

/*
customer segmentation*/

/*SELECT * ,
CASE WHEN Monetary_Rating='highballer_customer' and recency_rating BETWEEN 'fairrecency_customer' and 'highrecency_customer' THEN 'high_value'
     WHEN Frequency_rating='fairfrequency_customer' or frequency_rating='goodfrequency_customer' or frequency_rating='highfrequency_customer' then 'loyal'
     WHEN Recency_rating='lowrecency_customer' then 'dormant'
     WHEN Monetary_rating='lowballer_customer' then 'lowspender'
     WHEN Frequency_rating='lowfrequency_customer' then 'atrisk'
     WHEN recency_rating='highfrequency_customer' or recency_rating='goodfrequency_customer' and monetary_rating='fairballer_customer' or monetary_rating='goodballer_customer' and Frequency_rating='lowfrequency_customer' THEN 'occasional_ballers'
     ELSE 'ungrouped'
     END AS Customer_segment
       into #customer_segs
     FROM #RFM
ORDER BY MONETARYVALUE*/

SELECT *
from #customer_segs


--SELECT * from Sales.SalesOrderDetail--
--SELECT * FROM Sales.SalesOrderHeader--

--products frequently bought together--

/*SELECT A.name as product_name1,a.ProductID, e.name as product_name2,count (distinct b.SalesOrderID) as frequency 
into #Freqbought_together
from Production.Product A
join Sales.SalesOrderDetail b
on a.ProductID = b.ProductID
JOIN Sales.SalesOrderHeader c
ON b.SalesOrderID = c.SalesOrderID
join Sales.SalesOrderDetail d
on c.SalesOrderID = d.SalesOrderID
JOIN Production.Product e
ON d.ProductID = e.ProductID
group by a.Name, e.Name, a.ProductID

/*SELECT distinct product_name1, product_name2, frequency from #Freqbought_together
where product_name1 <> product_name2
order by frequency desc*/

select * ,

case when frequency >=200 then 'high_freqbought_together'
     WHEN frequency >=100 then  'moderatelybought_together'
     when frequency >=50 then 'lessboughttogether'
     when frequency <50   then 'leastboughtogehter'
end as freqboughttogether_segments

into #purchasedtogehter_segments
from #Freqbought_together

select distinct product_name1, product_name2, frequency, freqboughttogether_segments from #purchasedtogehter_segments

where product_name1 <> product_name2
order by frequency desc
