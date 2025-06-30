# Kultra-Mega-Stores-Inventory-
# Capstone Project 1
## Company Overview 
##### Kultra Mega Stores (KMS), headquartered in Lagos, specialises in office supplies and furniture. Its customer base includes individual consumers, small businesses (retail), and large corporate clients (wholesale) across Lagos, Nigeria. I have been engaged as a Business Intelligence Analyst to support the Abuja division of KMS. The Business Manager has shared an Excel file containing order data from 2009 to 2012 and has requested that I analyze the data and present your key insights and findings. 
##### I am to apply my SQL skills from the DSA Data Analysis class and solve both case scenarios as shared in the document. 

#### The dataset was successfully loaded. It contains 8,399 records and 21 columns with data ranging from 2009 to 2012, including order information, customer segments, product details, financial metrics, and shipping information. However, key numeric fields like Sales, Discount, Profit, Unit Price, and Shipping Cost are stored as strings with currency symbols or percentage signs, which need cleaning for proper analysis.

![Screenshot 2025-06-26 002810](https://github.com/user-attachments/assets/3e3dff70-47a9-4e1b-84b5-4aafb52cb4cd)

![image](https://github.com/user-attachments/assets/407dac72-f9bc-4353-94ed-b4bf74b53773)

Before I proceed, I made sure I Cleaning the relevant columns. The dataset was cleaned and ready for analysis. All relevant columns such as Sales, Discount, Profit, Unit Price, and Shipping Cost are numeric, and date fields are in proper datetime format.

✅ Case Scenario I
### 1. Which product category had the highest sales?
<pre> <code>select Product_Category, Sales from [dbo].[KMS Sql Case Study2]
where Sales = (select max(sales) from [dbo].[KMS Sql Case Study2])</code></pre>
![image](https://github.com/user-attachments/assets/e3cecd0f-aafb-4702-8a05-f252dae57adc)

--2. What are the Top 3 and Bottom 3 regions in terms of sales?
<pre> <code>select  top 3 Region, SUM(Sales) as totalsales  from [dbo].[KMS Sql Case Study2]
GROUP BY Region
ORDER BY totalsales DESC</code></pre>

<pre> <code>select  top 3 Region, SUM(Sales) as totalsales  from [dbo].[KMS Sql Case Study2]
GROUP BY Region
ORDER BY totalsales ASC</code></pre>

--3. What were the total sales of appliances in Ontario?

<pre> <code>Select sum(Sales) as TotalSales from [dbo].[KMS Sql Case Study2]
where Region = 'Ontario'</code></pre>

--4. Advise the management of KMS on what to do to increase the revenue from the bottom 10 customers 
<pre> <code>Select  Top 10 * from [dbo].[KMS Sql Case Study2] 
order by Profit DESC</code></pre>

<pre> <code>Select  Top 10 * from [dbo].[KMS Sql Case Study2] 
order by Profit ASC</code></pre>
--Shipping cost - Order Quantity
--Unit price
--I will advise KMS to to increase discount for the customers and also increase adverstiment to atract those customers

--5. KMS incurred the most shipping cost using which shipping method?
<pre> <code>Select shipping_Cost,Ship_Mode from [dbo].[KMS Sql Case Study2]
where shipping_Cost =(Select  Max(shipping_Cost) as Max_shipping_Cost from [dbo].[KMS Sql Case Study2])</code></pre>

--Case Scenario II 
--6. Who are the most valuable customers, and what products or services do they 
--typically purchase? 
<pre> <code>select * from [dbo].[KMS Sql Case Study2] </code></pre>
<pre> <code>SELECT Top 5 profit ,sales, Product_Name, Customer_Name
FROM [dbo].[KMS Sql Case Study2]
ORDER BY profit DESC</code></pre>


--7. Which small business customer had the highest sales? 
<pre> <code>SELECT Top 1 Customer_Name, SUM(Sales) AS Total_Sales
FROM [dbo].[KMS Sql Case Study2]
WHERE Customer_Segment = 'Small Business'
GROUP BY Customer_Name
ORDER BY Total_Sales DESC</code></pre>
--8. Which Corporate Customer placed the most number of orders in 2009 – 2012? 
<pre> <code>select * from [dbo].[KMS Sql Case Study2]
SELECT Top 1 Customer_Name, COUNT(Order_ID) AS Order_Count
FROM [dbo].[KMS Sql Case Study2]
WHERE Customer_Segment = 'Corporate'
GROUP BY Customer_Name
ORDER BY Order_Count DESC</code></pre>
--9. Which consumer customer was the most profitable one? 
<pre> <code>SELECT Top 1 Customer_Name, SUM(Profit) AS Total_Profit
FROM [dbo].[KMS Sql Case Study2]
WHERE Customer_Segment = 'Consumer'
GROUP BY Customer_Name
ORDER BY Total_Profit DESC</code></pre>
--10. Which customer returned items, and what segment do they belong to? 


--11. If the delivery truck is the most economical but the slowest shipping method and 
--Express Air is the fastest but the most expensive one, do you think the company 
--appropriately spent shipping costs based on the Order Priority? Explain your answer
<pre> <code>Select ship_mode, order_Priority,shipping_cost, Order_Date, Ship_Date from 
[dbo].[KMS Sql Case Study2]
order by shipping_cost DESC</code></pre>


