Here is the SQL Analysis, I did to identify trends of 10K customer records to get the insights of the profitable market segments.

1. To Create a Temporary Table to combining all the tables from all the regions 

WITH superstore_db AS (
	SELECT * FROM superstore_dataset___west
	UNION
SELECT * FROM superstore_dataset___cental
	UNION 
SELECT * FROM superstore_dataset___east
	UNION
SELECT * FROM superstore_dataset___south
	)

SELECT * FROM superstore_db	


2. Alter table columns name by replacing space with “_”

ALTER TABLE `superstore_dataset___west` CHANGE `Sub-Category` `Sub_Category` VARCHAR(11) CHARACTER SET utf8 COLLATE utf8_general_ci NULL DEFAULT NULL;


3. To Find Total Sales and Profit in each region and states.

SELECT superstore_dataset___west.Region,superstore_dataset___west.State,ROUND(SUM(superstore_dataset___west.Sales) ,2) AS Total_Sales, ROUND(SUM(superstore_dataset___west.Profit),2) AS Total_Profit FROM superstore_dataset___west
GROUP BY superstore_dataset___west.Region,superstore_dataset___west.State 
UNION
SELECT superstore_dataset___central.Region,superstore_dataset___central.State,ROUND(SUM(superstore_dataset___central.Sales),2) AS Total_Sales, ROUND(SUM(superstore_dataset___central.Profit),2) AS Total_Profit FROM superstore_dataset___central
GROUP BY superstore_dataset___central.Region,superstore_dataset___central.State 
UNION
SELECT superstore_dataset___east.Region,superstore_dataset___east.State,ROUND(SUM(superstore_dataset___east.Sales),2) AS Total_Sales, ROUND(SUM(superstore_dataset___east.Profit),2) AS Total_Profit FROM superstore_dataset___east
GROUP BY superstore_dataset___east.Region,superstore_dataset___east.State 
UNION
SELECT superstore_dataset___south.Region,superstore_dataset___south.State,ROUND(SUM(superstore_dataset___south.Sales),2) AS Total_Sales, ROUND(SUM(superstore_dataset___south.Profit),2) AS Total_Profit FROM superstore_dataset___south
GROUP BY superstore_dataset___south.Region,superstore_dataset___south.State 


4. To find Avg Price of a top 10 products 

SELECT superstore_dataset___west.Row_ID, superstore_dataset___west.Product_Name, round(AVG(superstore_dataset___west.Sales), 2) AS Total_Sales
FROM superstore_dataset___west
GROUP BY superstore_dataset___west.Product_Name
UNION
SELECT superstore_dataset___central.Row_ID, superstore_dataset___central.Product_Name, round(AVG(superstore_dataset___central.Sales),2) AS Total_Sales
FROM superstore_dataset___central
GROUP BY superstore_dataset___central.Product_Name
UNION
SELECT superstore_dataset___east.Row_ID, superstore_dataset___east.Product_Name, round(AVG(superstore_dataset___east.Sales),2) AS Total_Sales
FROM superstore_dataset___east
GROUP BY superstore_dataset___east.Product_Name
UNION
SELECT superstore_dataset___south.Row_ID, superstore_dataset___south.Product_Name, round(AVG(superstore_dataset___south.Sales),2) AS Total_Sales
FROM superstore_dataset___south
GROUP BY superstore_dataset___south.Product_Name
ORDER BY Total_Sales DESC
LIMIT 10;


5 To find top 5 categories, sub categpries, product and profit associated with it

SELECT superstore_dataset___west.Row_ID, superstore_dataset___west.Category, superstore_dataset___west.Sub_Category, superstore_dataset___west.Product_Name, round(SUM(superstore_dataset___west.Profit),2) AS Profit
FROM superstore_dataset___west
GROUP BY superstore_dataset___west.Category,superstore_dataset___west.Sub_Category, superstore_dataset___west.Product_Name
UNION
SELECT superstore_dataset___central.Row_ID, superstore_dataset___central.Category, superstore_dataset___central.Sub_Category, superstore_dataset___central.Product_Name, round(SUM(superstore_dataset___central.Profit),2) AS Profit
FROM superstore_dataset___central
GROUP BY superstore_dataset___central.Category,superstore_dataset___central.Sub_Category, superstore_dataset___central.Product_Name
UNION
SELECT superstore_dataset___east.Row_ID, superstore_dataset___east.Category, superstore_dataset___east.Sub_Category, superstore_dataset___east.Product_Name, round(SUM(superstore_dataset___east.Profit),2) AS Profit
FROM superstore_dataset___east
GROUP BY superstore_dataset___east.Category,superstore_dataset___east.Sub_Category, superstore_dataset___east.Product_Name
UNION
SELECT superstore_dataset___south.Row_ID, superstore_dataset___south.Category, superstore_dataset___south.Sub_Category, superstore_dataset___south.Product_Name, round(SUM(superstore_dataset___south.Profit),2) AS Profit
FROM superstore_dataset___south
GROUP BY superstore_dataset___south.Category,superstore_dataset___south.Sub_Category, superstore_dataset___south.Product_Name
ORDER BY Profit DESC
LIMIT 5;


6. Getting all the details of customer name as ”Darrin Van Huff", "Brosina Hoffman”

SELECT * 
FROM superstore_dataset___west
WHERE superstore_dataset___west.Customer_Name IN ("Darrin Van Huff", "Brosina Hoffman");


7. Getting top 10 potential customers with count of shopping

SELECT superstore_dataset___west.Customer_ID, superstore_dataset___west.Region, superstore_dataset___west.Customer_Name, COUNT(superstore_dataset___west.Sales) AS Potential_Customers
FROM superstore_dataset___west
GROUP BY superstore_dataset___west.Customer_ID  
UNION
SELECT superstore_dataset___central.Customer_ID, superstore_dataset___central.Region, superstore_dataset___central.Customer_Name, COUNT(superstore_dataset___central.Sales) AS Potential_Customers
FROM superstore_dataset___central
GROUP BY superstore_dataset___central.Customer_ID  
UNION
SELECT superstore_dataset___east.Customer_ID, superstore_dataset___east.Region, superstore_dataset___east.Customer_Name, COUNT(superstore_dataset___east.Sales) AS Potential_Customers
FROM superstore_dataset___east
GROUP BY superstore_dataset___east.Customer_ID  
UNION
SELECT superstore_dataset___south.Customer_ID, superstore_dataset___south.Region, superstore_dataset___south.Customer_Name, COUNT(superstore_dataset___south.Sales) AS Potential_Customers
FROM superstore_dataset___south
GROUP BY superstore_dataset___south.Customer_ID  
ORDER BY `Potential_Customers` DESC
LIMIT 10;

