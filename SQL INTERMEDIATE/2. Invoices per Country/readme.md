2. Invoices per Country

A business is analyzing data by country. For each country, display the country name, total number of invoices, and their average amount. Format the average as a floating-point number with 6 decimal places. Return only those countries where their average invoice amount is greater than the average invoice amount over all invoices.

---------------------------------------------------------------------------------

select co.country_name,count(inv.id),avg(inv.total_price) from country co inner join customer cu on co.id=cu.city_id inner join invoice inv on inv.customer_id=cu.id group by co.country_name having avg(inv.total_price)> ( 
    select avg(inv.total_price) from country co inner join  customer cu on co.id=cu.city_id inner join invoice inv on inv.customer_id=cu.id
)

------------------------------------------------------------------------------

