SELECT
    strftime('%Y', Date) AS year,
    strftime('%m', Date) AS month,
    SUM(Unit_Price) AS monthly_revenue,
    COUNT(DISTINCT Transaction_ID) AS order_volume
FROM
    online_sales_data
GROUP BY
    strftime('%Y', Date),
    strftime('%m', Date)
ORDER BY
    year, month;
