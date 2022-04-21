1. Business Expansion

------------------------------------------------------

As part of business expansion efforts at a company, your help is needed to find all pairs of customers and agents who have been in contact more than once. For each such pair, display the user id, first name, and last name, and the customer id, name, and the number of their contacts. Order the result by user id ascending.

There are 3 tables: customer, user_account, contact.
------------------------------------------------------------------------

Recordar subir el count con el asterisco...

select us.id , us.first_name, us.last_name, cust.id,cust.customer_name,count(*) from contact con inner join user_account us on us.id=con.user_account_id inner join customer cust on cust.id=con.customer_id group by us.id , us.first_name, us.last_name, cust.id,cust.customer_name,cust.contact_person having count(*)>1

