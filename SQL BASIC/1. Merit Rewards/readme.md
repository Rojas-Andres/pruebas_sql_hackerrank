1. Merit Rewards

--------------------------------------------------
SQL CERTIFICATE BASIC - SQL (Basic) - Skills certification test - Hackerrank
On the basis of merit, a company decides to promote some of its employee in its HR division at the end of the quarter because of their high performance. Write a query to find the employee IDs along with the names of all its employees who work in the HR department who earned a bonus of 5000 dollars or more in the last quarter.

There are two tables in the database: employee_information and last_quarter_bonus. Their primary keys are employee_ID.

---------------------------------------------------

select em.employee_id,name from employee_information em inner join last_quarter_bonus lb on em.employee_id=lb.employee_id where bonus>=5000 and division='HR';
