--------------------------------------------------------
2. Student Advisor
A university has started a student-advisor plan which assigns a professor as an advisor to each student for academic guidance. Write a query to find the roll number and names of students who either have a male advisor with a salary of more than 15,000 or a female advisor with a salary of more than 20,000.

There are two tables in the database: student_information and faculty_information. The primary key of student_information is roll_number whereas that of faculty_information is employee_ID.

--------------------------------------------------------

select roll_number,name from student_information st inner join faculty_information fi on st.advisor=fi.employee_id where (gender='M' and salary>15000) or (gender='F' and salary>20000)