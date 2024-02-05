# Danny's Restaurant-case-study-SQL
***
## Schema
<img align="center" width="600" src="https://github.com/amitgajkal/Restaurant-case-study---SQL/blob/main/Resource/Schema%201.png" alt="amitgajkal" />
<img align="center" width="600" src="https://github.com/amitgajkal/Restaurant-case-study---SQL/blob/main/Resource/Schema%202.png" alt="amitgajkal" />
***

## Business Objective
Danny wants to use the data to answer a few simple questions about his customers, especially about their visiting patterns, how much money they’ve spent and also which menu items are their favourite.

***

## ERD
<img align="Center" width="600" src="https://github.com/amitgajkal/Restaurant-case-study---SQL/blob/main/Resource/ERD.png" alt="amitgajkal" />

***
## Questions and Solutions

**1. What is the total amount each customer spent at the restaurant?**
**Steps:**
- Use JOIN to merge sales and menu tables as customer_id is available in both tables
- Use SUM to calculate the total sales contributed by each customer
- Group the aggregated results by s.customer_id
  
<img align="Center" width="600" src="https://github.com/amitgajkal/Restaurant-case-study---SQL/blob/main/Resource/Question%201.png" alt="amitgajkal" />

Solution:

<img align="Center" width="250" src="https://github.com/amitgajkal/Restaurant-case-study---SQL/blob/main/Resource/Solution%201.png" alt="amitgajkal" />

**2. How many days has each customer visited the restaurant?**

**Steps:**
- To determine the unique number of visits for each customer, using COUNT(DISTINCT order_date).
- It's important to apply the DISTINCT keyword while calculating the visit count to avoid duplicate counting of days.
   - For instance, if Customer A visited the restaurant twice on '2021–01–07', counting without DISTINCT would result in 2 days instead of the accurate count of 1 day.


<img align="Center" width="600" src="https://github.com/amitgajkal/Restaurant-case-study---SQL/blob/main/Resource/Question%202.png" alt="amitgajkal" />

Solution:

<img align="Center" width="250" src="https://github.com/amitgajkal/Restaurant-case-study---SQL/blob/main/Resource/Solution%202.png" alt="amitgajkal" />

**3. What was the first item from the menu purchased by each customer?**

**Steps:**
- Create a Common Table Expression (CTE) named cte1. Within the CTE, create a new column rnk and calculate the row number using DENSE_RANK() window function.The PARTITION BY clause divides the data by customer_id, and the ORDER BY clause orders the rows within each partition by order_date.
- In the outer query, appropriate columns are selected and a filter is applied in the WHERE clause to retrieve the only rows where the rank column equals 1, which represents the first row within each customer_id partition.
- Used the GROUP BY clause to group the result by customer_id and product_name.

<img align="Center" width="600" src="https://github.com/amitgajkal/Restaurant-case-study---SQL/blob/main/Resource/Question%203.png" alt="amitgajkal" />

Solution:

<img align="Center" width="250" src="https://github.com/amitgajkal/Restaurant-case-study---SQL/blob/main/Resource/Solution%203.png" alt="amitgajkal" />

**4. What is the most purchased item on the menu and how many times was it purchased by all customers?**

**Steps:**
- Perform a COUNT aggregation on the product_id column and ORDER BY the result in descending order using most_purchased field.
- Apply the LIMIT 1 clause to filter and retrieve the highest number of purchased items.

<img align="Center" width="600" src="https://github.com/amitgajkal/Restaurant-case-study---SQL/blob/main/Resource/Question%204.png" alt="amitgajkal" />

Solution:

<img align="Center" width="250" src="https://github.com/amitgajkal/Restaurant-case-study---SQL/blob/main/Resource/Solution%204.png" alt="amitgajkal" />
