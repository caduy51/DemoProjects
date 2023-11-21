# Sales Insights Data Analysis Project

## Overview

In this demo project, I use an available dataset in the internet to showcase my relevant skills when dealing with data analysis in the Power BI platform. Additionally, I run MySQL queries to perform basic calculations and gain insights into the data.

I connect Microsoft Power BI to MySQL Server to extract the necessary tables to visualize the revenue by Customers and Products.

## Tools and technology used

Database technology: MySQL

Visualization tools: Microsoft Power BI

## Data analysis using Power BI

1.  Formula to create norm_amount column

`= Table.AddColumn(#"Filtered Rows", "norm_amount", each if [currency] = "USD" or [currency] ="USD#(cr)" then [sales_amount]*75 else [sales_amount], type any)`

2.  Data modeling

![The figure shows how tables are related to each other](img/Data%20modeling.PNG){width="443"}

The database schema has 5 entities: sales transactions, sales product, sales markets, sales date and sales customers.

The architecture of data modeling is star schema with sales transactions table sitting in the center.

2.  Data visualization

This dashboard gives the quick look at sales activity of the company.

![Overview of selling activity](img/Sales%20Dashboard.PNG){width="493"}

The stakeholder will grasp the general trend of the company revenue between 2018 and 2020. From here, they are going to evaluate and find the solution to improve the sales in the future.

In addition, the dashboard shows 5 customers with highest revenue, and amount of revenue by market_code, and by products. These are important information to analyze which market is profitable, which product is performing well in terms of revenue.
