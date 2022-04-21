2. Profitable Stocks

------------------------------------------------------------------------------

A stock is considered profitable if the predicted price is strictly greater than the current price. Write a query to find the stock_codes of all the stocks which are profitable based on this definition. Sort the output in ascending order.



There are two tables in the database: price_today and price_tomorrow. Their primary keys are stock_code.

------------------------------------------------------------------------------

select pr.stock_code from price_today pr inner join price_tomorrow pt on pr.stock_code=pt.stock_code where pt.price>pr.price
