# MySQL Cheat Sheet

## Table of Contents
- [Creating a Database](#for-creating-database)
- [Creating a Table](#creating-table)
- [Using a Specific Database](#using-a-specific-database)
- [Inserting Values into a Table](#inserting-values-into-a-table)
- [Constraints in MySQL](#constraints-in-mysql)
- [Inserting in Table with Constraints](#inserting-in-table-with-constraints)
- [Showing Columns](#showing-columns)
- [Showing All Tables](#showing-all-tables)
- [Showing Column Name with Different Heading](#showing-column-name-with-different-heading)
- [WHERE Clause with SELECT](#where-clause-with-select)
- [MySQL WHERE Comparison Operators](#mysql-where-comparison-operators)
- [Operators](#operators)
- [IN Operators](#in-operators)
- [BETWEEN Operator](#between-operator)
- [NOT BETWEEN Operator](#not-between-operator)
- [LIKE Operator](#like-operator)
- [Multiple Pattern](#multiple-pattern)
- [Wildcard Pattern](#wildcard-pattern)
- [Regular Expression](#regular-expression)
- [ORDER BY](#order-by)
- [DISTINCT](#distinct)
- [NULL and NOT NULL](#null-and-not-null)
- [LIMIT and OFFSET](#limit-and-offset)
- [UPDATE](#update)
- [COMMIT & ROLLBACK](#commit--rollback)
- [PRIMARY KEY and FOREIGN KEY Constraints](#primary-key-and-foreign-key-constraints)
- [JOIN](#join)
- [GROUP BY & HAVING](#group-by--having)
- [UNION & UNION ALL](#union--union-all)
- [IF & CASE](#if--case)
- [ALTER](#alter)
- [DROP and TRUNCATE](#drop-and-truncate)
- [VIEW](#view)
- [INDEX](#index)
- [One-To-One RelationShip](#one-to-one-relationship)
- [One-To-Many RelationShip](#one-to-many-relationship)
- [Many-To-Many RelationShip](#many-to-many-relationship)

### For creating database

`CREATE DATABASE database_name;`

### Creating table

```
CREATE TABLE table_name(
Column1 datatype,
Column2 datatype,
Column3 datatype,
);
```

**Example:**
```SQL
create table student(
    Name varchar(40),
    Roll_No int,
    Department varchar(100),
    Admission_Date date
    );
```

### Using a specific database

```SQL
use database_name;
```

### Showing all table:

```SQL 
Show tables;
```

### Inserting values into a table

`INSERT INTO table_name (column1,column2,column3) VALUES(VALUE1, VALUE2,VALUE3);`

**Example**
```SQL
INSERT INTO student(Name,Roll_No,Department,Admission_Date) VALUES("Steve",2363,"Cyber Security","2024-06-10");
```

### Inserting Multiple value in a table

```
INSERT INTO table_name (column1,column2,column3)
VALUES(VALUE1, VALUE2,VALUE3),
   (VALUE1, VALUE2,VALUE3),
   (VALUE1, VALUE2,VALUE3);
```

**Example**
```SQL
INSERT INTO student(Name,Roll_No,Department,Admission_Date)
VALUES("Steve",2363,"Cyber Security","2024-06-10"),
   ("jerry",6478,"Computer Science","2023-02-20"),
   ("broad",1896,"Software eng","2022-05-15");
```

### Constraints in MySQL

Restriction on columns

- NOT NULL
- UNIQUE
- DEFAULT
- CHECK
- FOREIGN KEY
- PRIMARY KEY

**Example**
```SQL
CREATE table STUDENT_PERSSONAL_INFO(
city varchar(100) NOT NULL,
    gender VARCHAR(20) NOT NULL,
    age INT NOT NULL CHECK(AGE>=18),
    ph_number INT NOT NULL UNIQUE,
    father_name VARCHAR(100) DEFAULT 'Not Entered'
);
```

### inserting-in-table-with-constraints

```SQL
insert INTO student_perssonal_info(city,gender,age,ph_number,father_name)
value("sydney","M",19,114320132,"steve");
```

For default condition

```SQL
insert INTO student_perssonal_info(city,gender,age,ph_number)
value("sydney","M",19,112320132);
```

If ph_number is not entered it will add a default value of not entered.

### Showing columns

`SELECT column1,column2,column3, FROM TABLE_NAME;`

**Example:**

```SQL
SELECT Name, Roll_No FROM student;
```

### Showing all tables

`SELECT * FROM TABLE_NAME;`

**Example:**

```SQL
SELECT * FROM student;
```

### Showing column name with different heading

`SELECT column1 AS COLUMN1, column2 as COLUMN2 FROM student;`

**Example**

```SQL
SELECT Name AS Student_Name, Roll_No AS ID FROM student;
```

Or

```SQL
SELECT Name AS "Student Name", "Roll No" AS ID FROM student;
```

### WHERE clause With SELECT

`SELECT Column1,Column2,Column3 FROM table_name WHERE condition;`

### MySQL Where Comparison Operators

`=,>,<,<=,>=,!= or <>,BETWEEN,LIKE,IN`

**Example:**

```SQL
SELECT Name , Roll_No FROM student WHERE Roll_NO=2363;
```

To show all column for a specific condition

```SQL
SELECT * FROM student WHERE Roll_NO !=2363;
```

### Operators

`AND ,OR, NOT`

**Example:**

```SQL
SELECT Name , Roll_No FROM student WHERE age>20 AND age<22;
```

### IN Operators

Search value if match with enter value in IN

**Example:**

```SQL
SELECT Name,Department FROM student WHERE Roll_No IN(2363);
```
Print name and department where *roll number* is 2363;

```SQL
SELECT Name,Department FROM student WHERE Admission_Date IN('2024-06-10','2023-02-20');
```

Print name and department where *admission date* is 2024-06-10 or 2023-02-20

```SQL
SELECT * FROM student WHERE Admission_Date IN('2024-06-10','2023-02-20');
```

### BETWEEN Operator

**Example:**

```SQL
AGE BETWEEN 18 AND 20
```

### BETWEEN WITH SELECT

`SELCECT column1,column2 FROM table_name WHERE column value1 AND value2;`

Examples:

```SQL
SELECT * FROM student WHERE Admission_Date BETWEEN "2022-01-15" AND "2024-05-10";
```

```SQL
SELECT Name FROM student WHERE Admission_Date BETWEEN "2022-01-15" AND "2024-05-10";
```

```SQL
SELECT * FROM student WHERE Name BETWEEN "a" AND "q";
```

All name that have starting Alphabet between a and q

Or we use

```SQL
SELECT * FROM student WHERE Name BETWEEN "aston" AND "qais";
```

### NOT BETWEEN operator

Same syntax as between just we use NOT with BETWEEN

**Example:**

```SQL
SELECT Name FROM student WHERE Admission_Date NOT BETWEEN "2022-01-15" AND "2024-05-10";
```

### LIKE operator

```SQL
Where department LIKE "d%"
```

It show all department that start with d

### use LIKE & NOT LIKE with SELECT

**LIKE**

`SELECT column1,column2,column3 FROM table_name WHERE  column_name LIKE pattern;`

**Example:**

```SQL
SELECT city,age FROM student_perssonal_info WHERE ph_number LIKE '132%';
```

```SQL
SELECT Name FROM student WHERE Name LIKE '%e%';
```

**NOT LIKE**

**Example:**

```SQL
SELECT Name FROM student WHERE Name NOT LIKE '%e%';
```

```SQL
SELECT Name FROM student WHERE Admission_Date NOT LIKE '2024%';
```

### Multiple pattern

**Example:**

```SQL
SELECT Name FROM student WHERE Admission_Date NOT LIKE '2024%' AND Admission_Date LIKE '2023%';
```

```SQL
SELECT Name FROM student WHERE Admission_Date NOT LIKE '2024%' OR Admission_Date LIKE '2023%';
```

### Wildcard pattern

`%`=Represent zero, one, or multiple character

`_`=Represent a single character

**Example of wildcard pattern**

- LIKE `'d%'`  =start with "d"

- LIKE `'%a'`=End with "a"

- LIKE `'%ad%`= string having "ad" at any position

- LIKE `'a%d'`=start with a and end with d

- LIKE `'_a%'`=second character is a

- LIKE `'__a%'`=third character is a

- LIKE `'_ar'=a` in second and r in third position

### REGULAR EXPRESSION

`WHERE name REGEXP "khan$|poor"`

**Common Expression**

- `^`  => `'^ra'` =if string start with ra

- `$` => 'he$'` = if string end with he

- `[…] `=>`'[ew]'` =if a string contain e or w

- `^[…]` =>`'^'[fdw]'`= if a string start with f, d or w

- `[a-t]` => `'[a-h]s'`= a character between a and g with second word s

- `P1|p2|p3` => `hello | new | people` =match any of the pattern


`SELECT column1,column2 FROM table WHERE column REGEXP pattern;`

**Example**

```SQL
SELECT Roll_No,Department FROM student WHERE name REGEXP '^st';
```
```SQL
SELECT Roll_No,Department FROM student WHERE name REGEXP '[tve]';
```
```SQL
SELECT Roll_No,Department FROM student WHERE name REGEXP '[tve]';
```

```SQL
SELECT Roll_No,Department FROM student WHERE name REGEXP 'jerry|^St|[oa]';
```

### ORDER BY

Use for ordering is ascending and descending order

`SELECT column1,column2 FROM table_name ORDER BY column1,column2 ASC| DESC;`

**Example:**
```SQL
SELECT * FROM student ORDER BY Name ASC;
```
```SQL
SELECT * FROM student ORDER BY Name DESC;
```
```SQL
SELECT * FROM student ORDER BY Admission_Date ASC;
```
```SQL
SELECT * FROM student WHERE Name='steve' ORDER BY Admission_Date ASC;
```

### DISTINCT

To show all different record with in a column. It remove duplicate.

`SELECT DISTINCT column1,column2 FROM table_name;`

**Example:**

```SQL
SELECT DISTINCT Name FROM student;
```
```SQL
SELECT DISTINCT Name,Department FROM student;
```

### NULL and NOT NULL

To search for value if entry is null

`WHERE name IS NULL`

`SELECT  column1,column2  FROM table WHERE name IS NULL;`

**Example:**

```SQL
SELECT * FROM student WHERE Roll_No IS NULL;
```
```SQL
SELECT * FROM student WHERE Roll_No IS NOT NULL;
```

### LIMIT and OFFSET

It use to print  limited number of record

`SELECT column1,column2 FROM table_name WHERE condition LIMIT number;`

Offset is use as a starting number if we want to print record between two point

`SELECT column1,column2 FROM table_name WHERE condition LIMIT offset, number;`

### LIMIT

**Example:**

```SQL
SELECT * FROM student LIMIT 3;
```
```SQL
SELECT * FROM student WHERE Admission_Date > '2021-01-10' LIMIT 3;
```
### LIMIT with OFFSET

```SQL
SELECT * FROM student WHERE Department = 'Cyber Security' LIMIT 2,3;
```
This query skip first two line.
```SQL
SELECT * FROM student WHERE Admission_Date > '2021-01-10' LIMIT 0,3;
```
Check first three

### UPDATE

`UPDATE table_name SET column1_name=value1,column2_name=value2..WHERE condition`

**Example**

```SQL
UPDATE student_marks SET marks=100 WHERE Name='Ben';
```

If this give error,then type
```SQL 
SET SQL_SAFE_UPDATES = 0;
``` 
This will disable safe mode. 
After query execution run 
```SQL
SET SQL_SAFE_UPDATES = 1 -- to enable safe mode;
```
```SQL
UPDATE student SET Roll_No=6478,Department='Data science'  WHERE Admission_Date='2023-02-20';
```
```SQL
UPDATE student SET Roll_No=5278 WHERE Admission_Date IN ('2022-06-10','2023-04-11');
```

### COMMIT & ROLLBACK

Roll back basically revert all changes. If I use 3 comand and then apply roll back it will revert change.

COMMIT is barrier to stop ROLL BACK to a limit.

 Roll BACK only work on three command INSERT ,UPDATE ,DELETE

```SQL
COMMIT; 
INSERT INTO student(Name,Roll_No) VALUES("Root",2643);
INSERT INTO student(Name,Roll_No) VALUES("Anderson",2643);
ROLLBACK;
```

Save previous state add two new query and then rollback

`DELETE FROM table_name WHERE condition;`

`DELETE FROM table_name;`

**Example:**

```SQL
DELETE FROM student WHERE Name='Root' OR Name='Anderson' OR Name='Henry';
DELETE FROM student_personal_info;
```

### PRIMARY KEY and FOREIGN KEY Constraints

Primar]y key always has a unique data.

Primary cannot be have a null value

A table can contain only one primary key contrainsts

Primary is not like unique because it cannot contain null value

**PRIMARY KEY**

**Example:**
```SQL
CREATE TABLE BankAccount(
    Account_No INT NOT NULL,
    Balance INT,
    Name VARCHAR(40) NOT NULL,
    PRIMARY KEY(Account_No)
);
```

If table already exist

`ALTER TABLE table_name ADD PRIMARY KEY(Column);`

**Example**

```SQL
ALTER TABLE bankaccount ADD PRIMARY KEY (Account_No);
```

**To delete a primary key**

`ALTER TABLE table_name ADD PRIMARY KEY(Column);`

**Example**
```SQL
ALTER TABLE BankAccount DROP PRIMARY KEY;
```
### FOREIGN KEY

It is used to link to table together

A primary key in one table is pointed by foreign key in another table

`FOREIGN KEY (COLUMN) REFRENCES SECOND_TABLE_NAME(COLUMN)`

**Table 1**
```SQL
CREATE TABLE Customers (
    CustomerID INT PRIMARY KEY,
    Name VARCHAR(100),
    Email VARCHAR(100)
);
```

**Table 2**
```SQL
CREATE TABLE Orders (
    OrderID INT PRIMARY KEY,
    OrderDate DATE,
    Amount DECIMAL(10, 2),
    CustomerID INT,
    FOREIGN KEY (CustomerID) REFERENCES Customers(CustomerID)
);
```

**Table1 insertion**

```SQL
INSERT INTO Customers (CustomerID, Name, Email) VALUES (1, 'John Doe', 'john@example.com');
INSERT INTO Customers (CustomerID, Name, Email) VALUES (2, 'Jane Smith', 'jane@example.com');
```

**Table2 insertion**

```SQL 
INSERT INTO Orders (OrderID, OrderDate, Amount, CustomerID) VALUES (1, '2023-01-01', 100.00, 1);
INSERT INTO Orders (OrderID, OrderDate, Amount, CustomerID) VALUES (2, '2023-01-02', 150.00, 2);
INSERT INTO Orders (OrderID, OrderDate, Amount, CustomerID) VALUES (3, '2023-01-03', 200.00, 1);
```

**If table already exist**

```SQL 
ALTER TABLE child_table_name ADD FOREIGN KEY (child_column_name);
```

```SQL
REFERENCES parent_table_name(parent_column_name);
```
### JOIN

**INNER JOIN**

An inner join is a type of join that returns rows from multiple tables where the join condition is met. The inner join selects records that have matching values in both tables. If no matching values are found, the row is not returned.

```SQL
SELECT columns
FROM table1
INNER JOIN table2
ON table1.common_column = table2.common_column;
```

**Example**

```SQL
SELECT * FROM student INNER JOIN student_marks ON student.Name=student_marks.Name;
SELECT student.Name FROM student INNER JOIN student_marks ON student.Name=student_marks.Name;
SELECT S.Name FROM student S INNER JOIN student_marks SM ON S.Name=SM.Name;
```

**LEFT JOIN**

It print all data from left table and matching data from right table

```SQL
SELECT columns
FROM table1
LEFT JOIN table2
ON table1.common_column = table2.common_column;
Where table 1 is left
```

**Example**

```SQL
SELECT * FROM bankaccount LEFT JOIN student ON bankaccount.Name=student.Name;
SELECT Department FROM student LEFT JOIN bankaccount ON bankaccount.Name=student.Name;
```

**RIGHT JOIN**

It print all data from left table and matching data from right table

```SQL
SELECT columns
FROM table1
RIGHT JOIN table2
ON table1.common_column = table2.common_column;
Where table 1 is RIGHT
```

**Example**

```SQL
SELECT * FROM bankaccount RIGHT JOIN student ON bankaccount.Name=student.Name;
SELECT Department FROM student RIGHT JOIN bankaccount ON bankaccount.Name=student.Name;
```

**CROSS JOIN**

In cross join all row of table1 make combination of all row of table2

If we have 3 rows in table 1 and 5 rows in table2 then number of combination will be 3x5=15

```SQL
SELECT *
FROM table1
CROSS JOIN table2;
```

```SQL
SELECT * FROM table1 CROSS JOIN table2;
JOIN
SELECT
    column1, column2, ...
FROM
    table1
INNER JOIN table2 ON table1.common_column = table2.common_column
INNER JOIN table3 ON table2.common_column = table3.common_column
WHERE
    condition;
```

### GROUP BY & HAVING:

The GROUP BY clause in MySQL is used to group rows that have the same values in specified columns into summary rows. It's often used with aggregate functions like COUNT(), SUM(), AVG(), MAX(), and MIN() to perform operations on each group of data.

| order_id | customer_id | product_id | quantity | price |
|----------|-------------|------------|----------|-------|
| 1        | 101         | 201        | 5        | 10.00 |
| 2        | 102         | 202        | 3        | 20.00 |
| 3        | 101         | 201        | 2        | 10.00 |
| 4        | 103         | 203        | 4        | 30.00 |
| 5        | 102         | 201        | 1        | 10.00 |


```SQL
SELECT customer_id, SUM(quantity) AS total_quantity
FROM orders
GROUP BY customer_id;
```

Output

| customer_id | total_quantity |
|-------------|----------------|
| 101         | 7              |
| 102         | 4              |
| 103         | 4              |

The HAVING clause in MySQL is used to filter groups of rows after the GROUP BY clause has been applied. It is similar to the WHERE clause but is used specifically for aggregate functions.

```SQL
SELECT product_id, SUM(quantity * price) AS total_sales
FROM orders
GROUP BY product_id
HAVING total_sales > 50;
```

| product_id | total_sales |
|------------|-------------|
| 201        | 80.00       |
| 203        | 120.00      |

### UNION & UNION ALL

UNION print only unique entries

UNION ALL print all entries includinf duplicate

```SQL
SELECT column1,column2 FROM tabal1
UNION/UNION ALL
SELELCT column1,column2 FROM table2;
```

**Example:**

```SQL
SELECT Account_No FROM bankaccount
UNION ALL
SELECT order_id FROM orders;
```

### IF & CASE

The IF function is used to return one value if a condition is true and another value if it is false.

```SQL
IF(condition, true_value, false_value) AS alias_name
FROM table_name;
```

The CASE statement is more versatile than IF and allows for multiple conditions.

```SQL
CASE expression
    WHEN value1 THEN result1
    WHEN value2 THEN result2
    ...
    ELSE resultN
END AS alias_name
FROM table_name;
```

**IF example:**

`SQL SELECT *, IF(marks>40, "Pass","Fail") AS result FROM student_marks;`

**CASE example:**

```SQL
SELECT Name,marks, CASE
WHEN marks>40 && marks<60 THEN "c"
        WHEN marks>=60 && marks<80 THEN "B"
        WHEN marks>80 THEN "A"
        ELSE "F"
        END AS result
FROM student_marks;
```

### ALTER

The ALTER command in MySQL is used to modify the structure of an existing table.

**Add new column**

`ALTER TABLE table_name ADD column_name column_type;`

```SQL 
ALTER TABLE student ADD marks int;
```

**DROP column**

```SQL 
ALTER TABLE student DROP COLUMN marks;
```

**Modify column**

`ALTER TABLE table_name MODIFY column_name new_column_type;`

```SQL 
ALTER TABLE student MODIFY COLUMN marks varchar(100);
```

**Change a Column Name**

`ALTER TABLE table_name CHANGE old_column_name new_column_name column_type;`

```SQL 
ALTER TABLE student CHANGE COLUMN marks student_marks varchar(100);
```

**Rename a Table**

`ALTER TABLE old_table_name RENAME new_table_name;`

```SQL 
ALTER table student_marks RENAME marks_detail;
```

**Add a Primary Key**

```SQL 
ALTER TABLE table_name ADD PRIMARY KEY (column_name);
```

**Drop a Primary Key**

```SQL 
ALTER TABLE table_name DROP PRIMARY KEY;
```

### DROP and TRUNCATE

`DROP TABLE table_name;`

Completely removes the table and all its data from the database.

```SQL 
DROP TABLE orders;
```

```SQL 
TRUNCATE  TABLE table_name;
```

Removes all rows from the table but retains the table structure for future use.

```SQL 
TRUNCATE TABLE student_perssonal_info;
```

### VIEW 

It is used to save large query which is used multiple time in a database. We can access it with a key view name

```
CREATE VIEW view_name AS
query here
```

**Example**

```SQL
CREATE VIEW print_table AS
SELECT student.Name
FROM student
INNER JOIN bankaccount
ON student.Name = bankaccount.Name;
To execute same query now we use
SELECT * FROM print_table;
DELETE VIEW
`DROP VIEW view_name;`
DROP VIEW print_table;
```

**Modifying a View**

To modify an existing view, you use the CREATE OR REPLACE VIEW statement.

```
CREATE OR REPLACE VIEW view_name AS
SELECT column1, column2, ...
FROM table_name
WHERE new_condition;
INDEX
```

### INDEX

It is used for fat search but using if for table having 50 to 200 or 300 entries ha no such effect.

`CREATE INDEX index_name ON TABLE(column1,column2);`

**DELETE INDEX**

`DROP INDEX index_name ON table_name;`

**Example**

```SQL
CREATE INDEX student_name ON student(Name);
```

### One To One RelationShip

In a one-to-one relationship, each record in one table is linked to a single record in another table. This relationship is commonly used to split data into multiple tables for better organization, security, or performance.

Table 1: Employees

```SQL
CREATE TABLE Employees (
    EmployeeID INT PRIMARY KEY,
    FirstName VARCHAR(50) NOT NULL,
    LastName VARCHAR(50) NOT NULL,
    Email VARCHAR(100) NOT NULL UNIQUE
);
```

Table 2: EmployeeDetails
```SQL
CREATE TABLE EmployeeDetails (
    DetailID INT PRIMARY KEY,
    EmployeeID INT UNIQUE,
    PhoneNumber VARCHAR(15),
    Address VARCHAR(255),
    FOREIGN KEY (EmployeeID) REFERENCES Employees(EmployeeID)
);
```
To insert  we use

```SQL
INSERT INTO Employees (EmployeeID,FirstName,LastName,Email)
	VALUES(1,"Henry","Ben","Henry@Nothing.com"),
			(2,"Jason","Ben","jason@Nothing.com");
            
INSERT INTO EmployeeDetails (DetailID,EmployeeID,PhoneNumber,Address)
	VALUES(1,1,"223456543234543","No address"),
		  (2,2,"235678654565666","No address");
```

## Tables After Insertion

### Employees Table

| EmployeeID | FirstName | LastName | Email                   |
|-------------|-----------|----------|-------------------------|
| 1           | Henry     | Ben      | Henry@Nothing.com       |
| 2           | Jason     | Ben      | jason@Nothing.com       |

### EmployeeDetails Table

| DetailID | EmployeeID | PhoneNumber      | Address      |
|----------|------------|------------------|--------------|
| 1        | 1          | 223456543234543  | No address   |
| 2        | 2          | 235678654565666  | No address   |


TO show Data From Both Table we use

```SQL
SELECT 
	E.Email,
    Ed.PhoneNumber 
FROM 
	Employees E 
JOIN 
	EmployeeDetails Ed on Ed.EmployeeID=E.EmployeeID;

```

Resulting Table After View Query

| Email                   | Phone Number            |
|-------------------------|-------------------------|
| Henry@Nothing.com       |223456543234543          |
| jason@Nothing.com       |235678654565666          |


### One To Many RelationShip

A one-to-many relationship is a type of database relationship where a single record in one table can be associated with multiple records in another table, while each record in the second table is linked to only one record in the first table.

Table1: Teacher

```SQL
CREATE TABLE Teacher(
	TeacherID INT PRIMARY KEY,
    TeacherName VARCHAR(50)
);
```

Table2: NewStudent

```SQL
CREATE TABLE NewStudent(
	StudentID INT PRIMARY KEY,
    StudentName VARCHAR(50),
    TeacherID INT,
    FOREIGN KEY (TeacherID) REFERENCES Teacher(TeacherID)
);

```

The one key difference that distinguishes a **one-to-one relationship** from a **one-to-many relationship** is `the uniqueness of the foreign key`

### Many To Many RelationShip

A many-to-many relationship in a database allows multiple records in one table to be associated with multiple records in another table, typically implemented through a junction table that contains foreign keys from both tables.

Table1: Student

```SQL
CREATE TABLE Student(
    StudentID INT PRIMARY KEY,
    StudentName VARCHAR(50)
);
```


Table2: Course

```SQL
CREATE TABLE Course(
	CourseID INT PRIMARY KEY,
    CourseName VARCHAR(50)
);
```
Table to create many to many relationship 

Junction Table: Enrollment
```SQL
CREATE TABLE ENrollement(
	EnrollementID INT PRIMARY KEY,
    StudentID INT,
    CourseID INT,
    FOREIGN KEY (StudentID) REFERENCES Student(StudentID),
    FOREIGN KEY (CourseID) REFERENCES Course(CourseID)
);
```

**By:** [Muhammad Munib](https://github.com/mun1bxD)
