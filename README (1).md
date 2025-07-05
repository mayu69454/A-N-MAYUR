CODE 


-- TASK 6: Monthly Revenue & Order Volume Analysis

SELECT 
    EXTRACT(YEAR FROM order_date) AS order_year,
    EXTRACT(MONTH FROM order_date) AS order_month,
    COUNT(DISTINCT order_id) AS order_volume,
    SUM(amount) AS total_revenue
FROM 
    orders
WHERE 
    order_date BETWEEN '2023-01-01' AND '2023-12-31' -- optional filter
GROUP BY 
    EXTRACT(YEAR FROM order_date), 
    EXTRACT(MONTH FROM order_date)
ORDER BY 
    order_year, 
    order_month;





