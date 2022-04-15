2. Country Codes
--------------------------------------------------------

A company wants to contact each of its customers regarding the policy changes. They have international customers, but their database does not include country codes with their phone numbers.

There are two tables in the database: customers and country_codes. The first table contains details of every customer including customer_id, name, phone_number, and country. The second table contains the country code for every country.

Write a query to retrieve a list of all customer ids, names, and phone numbers, with their country codes concatenated with their phone numbers. Sort the output in the order of their customer_id.

Note: The phone number should be in the following format: +COUNTRY_CODE PHONENUMBER (without spaces)

-----------------------------------------------------------

select customer_id ,name ,concat('+',country_code,phone_number) from customers cu inner join country_codes co on cu.country=co.country


-------------------------------------------------------------
