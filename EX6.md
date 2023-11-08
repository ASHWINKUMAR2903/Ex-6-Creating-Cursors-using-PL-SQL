# Ex. No: 6 Creating Cursors using PL/SQL
### DATE : 07.09.23
### AIM: To create a cursor using PL/SQL.

### Steps:
1. Create employee table with following attributes (empid NUMBER, empname VARCHAR(10), dept VARCHAR(10),salary NUMBER);
2. Create a cursor named as employee_cursor
3. Using cursor read each record and display the result
4. Close the cursor

### Program:
### Create employee table
```
create table employee(empid NUMBER, empname VARCHAR(10), dept VARCHAR(10),salary NUMBER);

insert into employee values(1,'Shiro','CSE',50000);
insert into employee values(2,'kieo','IT',65000);
insert into employee values(3,'Shishimaru','EEE',55000);
```
### PLSQL Cursor code
```
SQL> set serveroutput on;
SQL> DECLARE
  2  cursor employee_cursor is
  3  select empid, empname, dept, salary
  4  from employee;
  5  emp_id number;
  6  emp_name varchar(50);
  7  emp_dept varchar(20);
  8  emp_salary number;
  9  BEGIN
 10  open employee_cursor;
 11  loop
 12  fetch employee_cursor into emp_id, emp_name, emp_dept, emp_salary;
 13  exit when employee_cursor%NOTFOUND;
 14  dbms_output.put_line('EMPLOYEE ID: ' ||emp_id);
 15  dbms_output.put_line('EMPLOYEE NAME: ' ||emp_name);
 16  dbms_output.put_line('DEPARTMENT: ' ||emp_dept);
 17  dbms_output.put_line('SALARY: ' ||emp_salary);
 18  dbms_output.put_line('---------------------------------------------------');
 19  end loop;
 20  close employee_cursor;
 21  end;
 22  /
```
### Output:
![image](https://github.com/ASHWINKUMAR2903/Ex-6-Creating-Cursors-using-PL-SQL/assets/119407186/f9c47316-6924-4d4b-b020-badfa7f2c14f)

### Result:
To create a cursor using PL/SQL is executed successfully.
