# Experiment 2: DDL Commands

## AIM
To study and implement DDL commands and different types of constraints.

## THEORY

### 1. CREATE
Used to create a new relation (table).

```sql
CREATE TABLE (
  field_1 data_type(size),
  field_2 data_type(size),
  ...
);
```
### 2. ALTER
Used to add, modify, drop, or rename fields in an existing relation.
(a) ADD
```sql
ALTER TABLE std ADD (Address CHAR(10));
```
(b) MODIFY
```sql
ALTER TABLE relation_name MODIFY (field_1 new_data_type(size));
```
(c) DROP
```sql
ALTER TABLE relation_name DROP COLUMN field_name;
```
(d) RENAME
```sql
ALTER TABLE relation_name RENAME COLUMN old_field_name TO new_field_name;
```
### 3. DROP TABLE
Used to permanently delete the structure and data of a table.
```sql
DROP TABLE relation_name;
```
### 4. RENAME
Used to rename an existing database object.
```sql
RENAME TABLE old_relation_name TO new_relation_name;
```
### CONSTRAINTS
Constraints are used to specify rules for the data in a table. If there is any violation between the constraint and the data action, the action is aborted by the constraint. It can be specified when the table is created (using CREATE TABLE) or after it is created (using ALTER TABLE).
### 1. NOT NULL
When a column is defined as NOT NULL, it becomes mandatory to enter a value in that column.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) NOT NULL
);
```
### 2. UNIQUE
Ensures that values in a column are unique.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) UNIQUE
);
```
### 3. CHECK
Specifies a condition that each row must satisfy.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) CHECK (logical_expression)
);
```
### 4. PRIMARY KEY
Used to uniquely identify each record in a table.
Properties:
Must contain unique values.
Cannot be null.
Should contain minimal fields.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) PRIMARY KEY
);
```
### 5. FOREIGN KEY
Used to reference the primary key of another table.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size),
  FOREIGN KEY (column_name) REFERENCES other_table(column)
);
```
### 6. DEFAULT
Used to insert a default value into a column if no value is specified.

Syntax:
```sql
CREATE TABLE Table_Name (
  col_name1 data_type,
  col_name2 data_type,
  col_name3 data_type DEFAULT 'default_value'
);
```

**Question 1**
--
Insert all products from Discontinued_products into Products.

Table attributes are ProductID, ProductName, Price, Stock

```sql
INSERT INTO Products 
SELECT ProductID, ProductName, Price, Stock from Discontinued_products;
```

**Output:**

<img width="1230" height="364" alt="image" src="https://github.com/user-attachments/assets/fd9ef98f-67ba-498b-8870-092b6699618e" />


**Question 2**
---
In the Books table, insert a record where some fields are NULL, another record where all fields are filled without any NULL values, and a third record where some fields are filled, and others are left as NULL.

```sql
INSERT INTO Books(ISBN,Title,Author)
VALUES('978-1234567890','Introduction to AI','John Doe');

INSERT INTO Books(ISBN,Title,Author,Publisher,Year)
VALUES('978-9876543210','Deep Learning','Jane Doe','TechPress',2022);

INSERT INTO Books(ISBN,Title,Author,Year)
VALUES('978-1122334455','Cybersecurity Essentials','Alice Smith',2021);
```

**Output:**

<img width="1225" height="372" alt="image" src="https://github.com/user-attachments/assets/bfef1c4c-066f-4061-a1d5-3ab779e43a8e" />


**Question 3**
---
Write a SQL query to add a new column MobileNumber of type NUMBER and a new column Address of type VARCHAR(100) to the Student_details table.

```sql
ALTER TABLE Student_details
ADD MobileNumber NUMBER;

ALTER TABLE Student_details
ADD Address VARCHAR(100);
```

**Output:**

<img width="1229" height="457" alt="image" src="https://github.com/user-attachments/assets/92844956-8c3c-4045-8c7d-5e0931c82fff" />

**Question 4**
---
Create a new table named item with the following specifications and constraints:
item_id as TEXT and as primary key.
item_desc as TEXT.
rate as INTEGER.
icom_id as TEXT with a length of 4.
icom_id is a foreign key referencing com_id in the company table.
The foreign key should set NULL on updates and deletes.
item_desc and rate should not accept NULL.

```sql
CREATE TABLE item
(
  item_id TEXT PRIMARY KEY,
  item_desc TEXT NOT NULL,
  rate INTEGER NOT NULL,
  icom_id TEXT(4),
  FOREIGN KEY(icom_id) REFERENCES company(com_id) ON UPDATE SET NULL ON DELETE SET NULL
);
```

**Output:**


**Question 5**
---
Insert the below data into the Employee table, allowing the Department and Salary columns to take their default values.

Note: The Department and Salary columns will use their default values. 

```sql
INSERT INTO Employee(EmployeeID,Name,Position)
VALUES(4,'Emily White','Analyst');
```

**Output:**

<img width="1225" height="385" alt="image" src="https://github.com/user-attachments/assets/343469d6-47c6-46a7-890f-d171df26da60" />


**Question 6**
---
Create a table named Events with the following columns:

EventID as INTEGER
EventName as TEXT
EventDate as DATE

```sql
CREATE TABLE Events
(
 EventID INTEGER,
 EventName TEXT,
 EventDate DATE
);
```

**Output:**

<img width="1227" height="452" alt="image" src="https://github.com/user-attachments/assets/c42ea290-553f-4f96-9b5a-be5ffc1beed7" />


**Question 7**
---
Create a table named Orders with the following constraints:
OrderID as INTEGER should be the primary key.
OrderDate as DATE should be not NULL.
CustomerID as INTEGER should be a foreign key referencing Customers(CustomerID).

```sql
CREATE TABLE Orders
(
OrderID INTEGER PRIMARY KEY,
OrderDate DATE NOT NULL,
CustomerID INTEGER,
FOREIGN KEY(CustomerID) REFERENCES Customers(CustomerID)
);
```

**Output:**

<img width="1222" height="356" alt="image" src="https://github.com/user-attachments/assets/0659ff4c-3d43-4a06-a219-22f9f9f29af5" />


**Question 8**
---
Write a SQL Query  to Rename attribute "name" to "first_name"  and add mobilenumber as number ,DOB as Date,State as varchar(30) in the table Companies. 

```sql
ALTER TABLE Companies
RENAME COLUMN name TO first_name;

ALTER TABLE Companies
ADD mobilenumber number; 

ALTER TABLE Companies
ADD DOB Date;

ALTER TABLE Companies
ADD State varchar(30);
```

**Output:**

<img width="1222" height="474" alt="image" src="https://github.com/user-attachments/assets/269499c2-1601-4c3a-b41f-467f88e88c4a" />


**Question 9**
---
Create a table named Products with the following constraints:
ProductID as INTEGER should be the primary key.
ProductName as TEXT should be unique and not NULL.
Price as REAL should be greater than 0.
StockQuantity as INTEGER should be non-negative.

```sql
CREATE TABLE Products
(
ProductID INTEGER PRIMARY KEY,
ProductName TEXT UNIQUE NOT NULL,
Price REAL CHECK(Price>0),
StockQuantity INTEGER CHECK(StockQuantity>0)
);
```

**Output:**

<img width="1224" height="357" alt="image" src="https://github.com/user-attachments/assets/d02f81c1-1fa1-4216-aa98-116ca084e717" />


**Question 10**
---
create a table named jobs including columns job_id, job_title, min_salary and max_salary, and make sure that, the default value for job_title is blank and min_salary is 8000 and max_salary is NULL will be entered automatically at the time of insertion if no value assigned for the specified columns.

```sql
CREATE TABLE jobs(
job_id INTEGER PRIMARY KEY,
job_title TEXT NOT NULL DEFAULT '',
min_salary INTEGER DEFAULT 8000,
max_salary INTEGER DEFAULT NULL
);
```

**Output:**

<img width="1217" height="386" alt="image" src="https://github.com/user-attachments/assets/2415c620-ba7c-4434-98b3-c5899a24f47f" />



## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.

<img width="1920" height="1200" alt="image" src="https://github.com/user-attachments/assets/e6d051fe-7eaf-44a2-a329-5852b9bcd057" />
