2. Product Sales per City

For each pair of city and product, return the names of the city and product, as well the total amount spent on the product to 2 decimal places. Order the result by the amount spent from high to low then by city name and product name in ascending order.
------------------------------------------------------------------
select city_name,product_name,sum(line_total_price) as total from city ci inner join customer cus on ci.id=cus.city_id inner join invoice inv on inv.customer_id=cus.id inner join invoice_item inv_i on inv_i.invoice_id=inv.id inner join product prd on prd.id=inv_i.product_id group by city_name,product_name order by total desc , city_name,product_name asc

-----------------------------------------------------------------------