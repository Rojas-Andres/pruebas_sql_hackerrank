1. Products Without Sales

Given the product and invoice details for products at an online store, find all the products that were not sold. For each such product, display its SKU and product name. Order the result by SKU, ascending.
-----------------------------------------------------------------------
Correct answer

select pr.sku, pr.product_name from product pr left join invoice_item inv on pr.id=inv.product_id where inv.invoice_id is null order by sku;

-----------------------------------------------------------------------