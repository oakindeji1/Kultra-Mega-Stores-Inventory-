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


