# Sales Insights Data Analysis Project

In this demo project, I used the available dataset for showcasing my relevant skills when dealing with data analysis. I connect Microsoft Power BI to MySQL Server to extract the necessary tables to visualize the revenue by Customers and Products.

## Tools and technology used

Database technology: MySQL

Visualization tools: Microsoft Power BI

### Using SQL for brief data analytics

1.  Display all customer records

    `SELECT * FROM customers;`

2.  How many product lines are sold by the company?

    `SELECT count(*) FROM products;`

3.  How many customers are served by the company?

    `SELECT count(*) FROM customers;`

4.  Display transactions for Mumbai market (market code for Mumbai is Mark002)

    `SELECT * FROM transactions where market_code='Mark002';`

5.  Show the product codes that were sold in Mumbai, India

    `SELECT distinct product_code FROM transactions where market_code='Mark002';`

6.  When was the first time that the company started selling products to customers? How long has it been?

    `SELECT year(MIN(order_date)) AS Starting_year, year(MAX(order_date)) AS Year_now, round(datediff(MAX(order_date), MIN(order_date))/365, 1) AS Duration FROM transactions;`

7.  Display the number of transactions in 2020

    `SELECT count(1) as number_of_transactions FROM transactions WHERE year(order_date) = 2020;`

8.  Calculate total revenue in year 2020

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.currency="INR\r" or transactions.currency="USD\r";`

9.  Calculate total revenue in year 2020, January

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and and date.month_name="January" and (transactions.currency="INR\r" or transactions.currency="USD\r");`

# Data Analysis Using Power BI

1.  Formula to create norm_amount column

`= Table.AddColumn(#"Filtered Rows", "norm_amount", each if [currency] = "USD" or [currency] ="USD#(cr)" then [sales_amount]*75 else [sales_amount], type any)`
