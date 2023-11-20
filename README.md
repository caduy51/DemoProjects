# Sales Insights Data Analysis Project

In this demo project, I used the available dataset for showcasing my relevant skills when dealing with data analysis. I connect Microsoft Power BI to MySQL Server to extract the necessary tables to visualize the revenue by Customers and Products.

## Tools and technology used

Database technology: MySQL

Visualization tools: Microsoft Power BI

## Data Analysis Using Power BI

1.  Formula to create norm_amount column

`= Table.AddColumn(#"Filtered Rows", "norm_amount", each if [currency] = "USD" or [currency] ="USD#(cr)" then [sales_amount]*75 else [sales_amount], type any)`
