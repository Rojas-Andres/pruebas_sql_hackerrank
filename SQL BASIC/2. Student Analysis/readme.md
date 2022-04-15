
2. Student Analysis

A school recently conducted its annual examination and wishes to know the list of academically low performing students to organize extra classes for them. Write a query to return the roll number and names of students who have a total of less than 100 marks including all 3 subjects.


There are two tables: student_information and examination_marks. Their primary keys are roll_number.

--------------------------------------------------------------------------------
select st.roll_number,name from student_information st inner join examination_marks ex on st.roll_number=ex.roll_number group by st.roll_number,name having sum(ex.subject_one+ex.subject_two+ex.subject_three )<100