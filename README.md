# Using-SQl-for-pizza-sales-analysis
In order to identify trends in orders, revenue, popular pizzas, and consumer behaviour, this research used SQL to examine actual pizza sales data. It transforms unprocessed data into understandable insights that support better business choices.

-- Retrieve the total number of orders placed.

SELECT 
    COUNT(order_id) AS total_orders
FROM
    orders;

-- Calculate the total revenue generated from pizza sales.   

SELECT 
    round(sum(orders_details.quantity * pizzas.price),1)  AS total_sales
FROM
    orders_details
        JOIN
    pizzas ON pizzas.pizza_id = orders_details.pizza_id
