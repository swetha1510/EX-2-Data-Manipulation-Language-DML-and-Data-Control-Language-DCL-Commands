# EX 2 Data Manipulation Language (DML) Commands and built in functions in SQL
## AIM:
To create a manager database and execute DML queries using SQL.


## DML(Data Manipulation Language)
<div align="justify">
The SQL commands that deal with the manipulation of data present in the database belong to DML or Data Manipulation Language and this includes most of the SQL statements. It is the component of the SQL statement that controls access to data and to the database. Basically, DCL statements are grouped with DML statements.
</div>

## List of DML commands: 
<div align="justify">
INSERT: It is used to insert data into a table.<br>
UPDATE: It is used to update existing data within a table.<br>
DELETE: It is used to delete records from a database table.<br>
</div>

## Create the table as given below:
```sql
create table manager(enumber number(6),ename char(15),salary number(5),commission number(4),annualsalary number(7),Hiredate date,designation char(10),deptno number(2),reporting char(10));
```
## insert the following values into the table
```sql
insert into manager values(7369,'Dharsan',2500,500,30000,'30-June-81','clerk',10,'John');
insert into manager values(7839,'Subu',3000,400,36000,'1-Jul-82','manager',null,'James');
insert into manager values(7934,'Aadhi',3500,300,42000,'1-May-82','manager',30,NULL);
insert into manager values(7788,'Vikash',4000,0,48000,'12-Aug-82','clerk',50,'Bond');
```

### Q1) Update all the records of manager table by increasing 10% of their salary as bonus.
### QUERY:
```
update manager set salary = salary*1.10;
```
### OUTPUT:
![Screenshot 2023-10-02 133402](https://github.com/swetha1510/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120623583/ad544c97-80a3-4858-8101-3fcf4aed6074)

### Q2) Delete the records from manager table where the salary less than 2750.
### QUERY:
```
delete from manager where salary<2750;
```
### OUTPUT:
![Screenshot 2023-10-02 133632](https://github.com/swetha1510/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120623583/a30afb59-224c-4b85-97b4-2d7d7d9ae9ef)

### Q3) Display each name of the employee as “Name” and annual salary as “Annual Salary” (Note: Salary in emp table is the monthly salary.
### QUERY:
```
 select ename as "Name" ,(salary*12)+NVL(commission,0) as "ANNUAL Salary" from manager;
```
### OUTPUT:
![Screenshot 2023-10-02 134141](https://github.com/swetha1510/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120623583/c7a0a57b-2e02-43ab-ad79-218f9a8a6454)

### Q5)	List the names of Clerks from emp table.
### QUERY:
```
select ename from manager where designation = 'clerk';
```
### OUTPUT:
![Screenshot 2023-10-02 134407](https://github.com/swetha1510/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120623583/3a1578ac-61ab-470a-8f32-ae9a5b443644)

### Q6)	List the names of employee who are not Managers.
### QUERY:
```
 select ename from manager where designation !='manager';
```
### OUTPUT:
![Screenshot 2023-10-02 134640](https://github.com/swetha1510/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120623583/2daac560-33d6-4b75-b113-21a0eb104c24)

### Q7)	List the names of employees not eligible for commission.
### QUERY:
```
 select ename from manager where commission=0;
```
### OUTPUT:
![Screenshot 2023-10-02 134818](https://github.com/swetha1510/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120623583/205fcd8c-b3f9-4c98-8b5d-4dc80d0d3402)

### Q8)	List employees whose name either start or end with ‘s’.
### QUERY:
```
select ename from manager where ename like 'S%' or ename like '%S';
```
### OUTPUT:
![Screenshot 2023-10-02 135101](https://github.com/swetha1510/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120623583/f5f83e06-a2f1-43a1-85c7-a31362c716c1)

### Q9) Sort emp table in ascending order by hire-date and list ename, job, deptno and hire-date.
### QUERY:
```
select ename,designation,deptno,hiredate from manager order by hiredate asc;
```
### OUTPUT:
![Screenshot 2023-10-02 135528](https://github.com/swetha1510/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120623583/e4288965-2a61-4539-a1fa-16250b48b286)

### Q10) List the Details of Employees who have joined before 30 Sept 81.
### QUERY:
```
select * from manager where hiredate<to_date('30-sep-81','DD-MON-YY');
```
### OUTPUT:
![Screenshot 2023-10-02 135935](https://github.com/swetha1510/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120623583/f8457907-20d4-4a0a-8d92-91db5325af56)

### Q11)	List ename, deptno and sal after sorting emp table in ascending order by deptno and then descending order by sal.
### QUERY:
```
 select ename,deptno,salary from manager order by deptno asc,salary desc;
```
### OUTPUT:
![Screenshot 2023-10-02 140234](https://github.com/swetha1510/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120623583/684b7e52-6381-4fca-8107-130634588c30)

### Q12) List the names of employees not belonging to dept no 30,40 & 10.
### QUERY:
```
select ename from manager where deptno not in(10,30,40);
```
### OUTPUT:
![Screenshot 2023-10-02 140434](https://github.com/swetha1510/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120623583/dbcf4456-3f7f-4abb-bed4-1409b8188d72)

### Q13) Find number of rows in the table EMP
### QUERY:
```
 select count(*) as "number of rows" from manager;
```
### OUTPUT:
![Screenshot 2023-10-02 140803](https://github.com/swetha1510/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120623583/baf0b10c-df52-414d-bf2f-922a9a3a7aaf)

### Q14) Find maximum, minimum and average salary in EMP table.
### QUERY:
```
select max(salary) as "MAXIMUM SALARY",min(salary) as "MINIMUM SALARY",avg(salary) as "AVERAGE SALARY" from manager;
```
### OUTPUT:
![Screenshot 2023-10-02 141225](https://github.com/swetha1510/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120623583/a5cbaa55-dd74-4b89-ac53-fe6f84c10765)

### Q15) List the jobs and number of employees in each job. The result should be in the descending order of the number of employees.
### QUERY:
```
SELECT designation, COUNT(*) AS "Number of Employees" FROM manager GROUP BY designation ORDER BY COUNT(*) DESC;
```
### OUTPUT:
![Screenshot 2023-10-02 141503](https://github.com/swetha1510/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120623583/b7c74589-da33-4911-8942-001969cfb6ce)
