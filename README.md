# dbms02
https://github.com/princejadhav01/dbms01/blob/main/README.md
Problem Statement: Design following SQL DML statements:
Create a university/college database containing following tables-
Student (stud_idi, deptnm, sem, name, yr, credits)
Teaches (teacher_id, teacher_name, salary, deptnm)
1. Insert records into all tables.
2. Update record on student tables as department name comp to IT.
3. Find the department that has highest or average salary
4. Delete the records of all teacher with salary below 2000.
5. Find the sum of salary of each department(use groupby).


✅ Step 1: Create Tables
sql
CREATE TABLE Student (
  stud_id   INT PRIMARY KEY,
  deptnm    VARCHAR(50),
  sem       INT,
  name      VARCHAR(100),
  yr        INT,
  credits   INT
);

CREATE TABLE Teaches (
  teacher_id   INT PRIMARY KEY,
  teacher_name VARCHAR(100),
  salary       INT,
  deptnm       VARCHAR(50)
);

✅ Step 2: Insert Records
sql
-- Insert into Student
INSERT INTO Student VALUES (1, 'COMP', 5, 'Rahul', 2023, 20);
INSERT INTO Student VALUES (2, 'IT',   3, 'Sneha', 2023, 15);

-- Insert into Teaches
INSERT INTO Teaches VALUES (101, 'Amit', 3000, 'COMP');
INSERT INTO Teaches VALUES (102, 'Priya', 1800, 'IT');
INSERT INTO Teaches VALUES (103, 'Kiran', 2500, 'COMP');


✅ Step 3: Update Department Name (COMP → IT)
sql
UPDATE Student
SET deptnm = 'IT'
WHERE deptnm = 'COMP';



Step 3:-highest/ average ( this is for maximum)
select dept_nm from teaches group by dept_nm order by max(salary) desc limit 1;

average(this is average)
select dept_nm, avg(salary) as avg_salary
from  teaches
group by dept_nm;

✅ Step 5: Delete Teachers with Salary < 2000
Sql

DELETE FROM Teaches
WHERE salary < 2000;

Step 6: Find Sum of Salary per Department
select dept_nm, sum(salary) as total_salary
from teaches
group by dept_nm;
