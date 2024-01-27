# SuperStore-Sales-Analysis
Here I have analyzed a Superstore dataset and made a short and detailed analysis report on the sales &amp; order trend  and tried to understand the customer  behaviour
# SuperStore Sales Data Analysis & Dashboard Creation using Power BI

## Dashboard Link :https://app.powerbi.com/groups/me/reports/83581b07-5113-4383-942e-43db0e8af16e/ReportSection?experience=power-bi

## About

The objective of this project is to analyze Super Store Sales data, with a focus on identifying top-performing Regions , Cities , States , Categories and subcategories & analyzing the sales trends  and understanding customer behavior.
The goal is to investigate opportunities for enhancing and optimizing sales strategies.

## Purpose Of The Project

The primary objective of this project is to get  insights from Superstore sales data, aiming to comprehend the diverse factors influencing the sales performance.


## About Data

The dataset was obtained from kaggle & The data contains 23 columns and 5901 rows:

| Column                  | Description                             
| :---------------------- | :-------------------------------------- 
| Row ID+O6G3A1:R6        | Row_ID              		    
| Order ID                | All the Order IDs of a particular order      
| Order Date              | The date on which order was placed            
| Ship Date         	  | The Date on which order was shipped             
| Ship Mode               | Mode of Shipment 
| Customer ID          	  | IDs of the customers who made the purchase 
| Customer Name           | Name of the customer             
| Segment             	  | Product Segment         
| Country                 | Country where the product is being Shipped
| City                    | City where the product is being Shipped
| State                   | State where the product is being Shipped
| Region                  | Region of the country
| Product ID        	  | ID of the product ordered                   
| Category                | Category of the product                   
| Sub-Category		  | Sub Category of the product                 
| Product Name            | Name/Description of the Product                          
| Sales                   | Sale done for each product 
| Quantity                | Quantity of each product                           
| Profit                  | Profit done on each sale
| Returns 		  | Order Return if any                           
| Profit                  | Profit done on each sale
| Returns 		  | Order Return if any                           
| Payment Mode            | Mode of Payment 
| ind1            	  | Blank 
| ind2            	  | Blank                                                          

Problem Statement:
Identify the below mentioned KPIs and provide valuable Insights / recommendations:

1. Total Sales Generated  ?
2. Total Unique Products availabe ?
3. Total number of Orders ?
4. Total unique Customers ?
5. Which segment has the max sales ?
6. Which Region has the max sales ?
7. Which Category / Subcategory has the max sales ?
8. Which is the most preffered payment method ?
9. Average no of days for an order to get shipped ?
10.Average order value and average orders per customer ?
11.Top 10 selling Products?
12.Highest Sales/profit  Month?
13.Top Cities and Sates with respect to sales 


## Steps Used
-- Data Cleaning:
> 1.Import the data into Power BI . Dataset is a csv file .
> 2.Open power query editor & in view tab under Data preview section, check "column distribution", "column quality" & "column profile" options. 
> 3.It was observed that  none of the columns had errors .For Column named 'Returns' #N/A value as replaced with "0" for ease of calculation .
> 4.Columns ind1,ind2 were removed  as both the columns were comepletely null

	-- Calculated Columns & Measures 
	# Calculated Columns
	> Average Delivery Days = DATEDIFF(SuperStore_Sales_Dataset[Order Date],SuperStore_Sales_Dataset[Ship Date],DAY)
	> OrderDay = FORMAT(SuperStore_Sales_Dataset[Order Date],"dddd")

	# Measures :
	> AvgOrderPerCustomer = CALCULATE(DISTINCTCOUNT(SuperStore_Sales_Dataset[Order ID])/DISTINCTCOUNT(SuperStore_Sales_Dataset[Customer ID]))
	> AvgOrderValue = CALCULATE(SUM(SuperStore_Sales_Dataset[Sales])/DISTINCTCOUNT(SuperStore_Sales_Dataset[Order ID]))
	> TotalOrders = DISTINCTCOUNT(SuperStore_Sales_Dataset[Order ID])
	> TotalReturn = CALCULATE(COUNT(SuperStore_Sales_Dataset[Returns]),SuperStore_Sales_Dataset[Returns]="1")

> 5.The Report has 3 seperate sheets  Summary , Insights  and Sales Forecast 



## Insights :

1> Overall $1.6M worth of total sales was done
2> Total of $175.3k profit was generated 
4> Average Shipping Days is 4 
5> 1742 unique products are available 
6> The superstore has 773  unique customers who ordered 3003 number of times
7> Average Order value is $521.4  with an average 4 orders per customer 
8> Consumer is the most selling segment with 48 %  share 
9> Most preffered payment method is Cash on Delivery(COD)
10>Phone is most selling product subcategory and Office Supplies is the most selling Category.
11>From YOY sales it can be seen that max sales in the month of  Dec 
12>3D Systems Cube Printer , 2nd Generation ,Magenta is the top selling Product 
13>Max order frequeny  can be seen on weekdays where as weekends typically sees less number of sales 
14>California( State)  and New York City registers highet number of sales 

In addition to these insights I have also added a Sales forecast page  where I have analysed the sales trend based on the order dates and predicted the sales trend for next 30 days at 95% confidence interval


## Dashbaord Snaps :
![Dashboard(Summary)](https://github.com/bigit91/SuperStore-Sales-Analysis/assets/155818756/5dfed2e5-a627-45ea-90bf-7e3a1f98c62c)
![Dashbaord(Insights)](https://github.com/bigit91/SuperStore-Sales-Analysis/assets/155818756/c0267409-328a-411f-bba1-938207f65ab3)
![Dashbaord(Forecast)](https://github.com/bigit91/SuperStore-Sales-Analysis/assets/155818756/783e637f-69bf-4d02-a540-a964cd24487f)



