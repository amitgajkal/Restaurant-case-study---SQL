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

1. What is the total amount each customer spent at the restaurant?
   
<img align="Center" width="600" src="https://github.com/amitgajkal/Restaurant-case-study---SQL/blob/main/Resource/Question%201.png" alt="amitgajkal" />

Solution:

<img align="Center" width="250" src="https://github.com/amitgajkal/Restaurant-case-study---SQL/blob/main/Resource/Solution%201.png" alt="amitgajkal" />


- Use JOIN to merge sales and menu tables as sales.customer_id and menu.price are from both tables
- Use SUM to calculate the total sales contributed by each customer
- Group the aggregated results by s.customer_id


