# Experiment 3: DML Commands

## AIM
To study and implement DML (Data Manipulation Language) commands.

## THEORY

### 1. INSERT INTO
Used to add records into a relation.
These are three type of INSERT INTO queries which are as
A)Inserting a single record
**Syntax (Single Row):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES (value_1, value_2, ...);
```
**Syntax (Multiple Rows):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES
(value_1, value_2, ...),
(value_3, value_4, ...);
```
**Syntax (Insert from another table):**
```sql
INSERT INTO table_name SELECT * FROM other_table WHERE condition;
```
### 2. UPDATE
Used to modify records in a relation.
Syntax:
```sql
UPDATE table_name SET column1 = value1, column2 = value2 WHERE condition;
```
### 3. DELETE
Used to delete records from a relation.
**Syntax (All rows):**
```sql
DELETE FROM table_name;
```
**Syntax (Specific condition):**
```sql
DELETE FROM table_name WHERE condition;
```
### 4. SELECT
Used to retrieve records from a table.
**Syntax:**
```sql
SELECT column1, column2 FROM table_name WHERE condition;
```
**Question 1**
--
Write a SQL query to reduce the reorder level by 30% where cost price is more than 50 and quantity in stock is less than 100 in the products table.

```sql
UPDATE Products
SET reorder_lvl=reorder_lvl*0.70
where cost_price>50 AND quantity<100;
```

**Output:**

<img width="1228" height="529" alt="image" src="https://github.com/user-attachments/assets/63d276b0-1056-4c4e-b76a-0edd2a9fd109" />


**Question 2**
---
Change the supplier name to upper case where contact person contains ' Singh' in suppliers table.

```sql
UPDATE suppliers
set supplier_name=UPPER(supplier_name)
where contact_person LIKE '%Singh%';
```

**Output:**

<img width="1234" height="412" alt="image" src="https://github.com/user-attachments/assets/bc73a055-5a4a-4c18-b32c-9edeef23defd" />


**Question 3**
---
Write a SQL statement to Update the reorder level to 20 where the quantity in stock is less than 10 and product category is 'Snacks' in the products table.

```sql
update products
set reorder_lvl=20
where quantity<10 AND category ='Snacks';
```

**Output:**

<img width="1225" height="640" alt="image" src="https://github.com/user-attachments/assets/d63ecc2e-b2d3-4b94-8b16-21082f7ea3f8" />


**Question 4**
---
Write a SQL statement to Increase the selling price by 15% in the products table where quantity in stock is less than 50 and supplier ID is 10.

```sql
UPDATE Products set sell_price=sell_price*1.15
where quantity<50 and supplier_id=10;
```

**Output:**

<img width="1226" height="577" alt="image" src="https://github.com/user-attachments/assets/b7352d37-1114-4a61-848f-df7a7a4b8533" />


**Question 5**
---
Write a SQL statement to Update the grade of all customers in Chennai city as  5. 
```sql
UPDATE Customer
set grade=5
where city='Chennai';
```

**Output:**
<img width="1234" height="548" alt="image" src="https://github.com/user-attachments/assets/e834c012-2181-4bc6-b57a-49f6a5cbc5e5" />

**Question 6**
---
Write a SQL query to Delete customers from 'customer' table where 'CUST_NAME' has exactly 6 characters.

```sql
DELETE FROM Customer where CUST_NAME LIKE'______';
```

**Output:**

<img width="1236" height="829" alt="image" src="https://github.com/user-attachments/assets/0ea6ebd3-5fd2-4076-b61d-1f83a9c8824b" />


**Question 7**
---
Write a SQL query to remove rows from the table 'customer' with the following condition -

1. 'cust_country' must be 'India',

2. 'cus_city' must not be 'Chennai',

```sql
DELETE FROM customer where CUST_COUNTRY ='India' and CUST_CITY<>'Chennai';```

**Output:**

<img width="1227" height="951" alt="image" src="https://github.com/user-attachments/assets/f03b37bb-a45f-4cef-82ee-5de40a0cde0c" />


**Question 8**
---
Write a SQL query to Delete customers with 'GRADE' 3 and whose 'CUST_NAME' contains the substring 'BBB', and 'PAYMENT_AMT' is greater than 2000
```sql
DELETE FROM customer
WHERE GRADE ='3' AND CUST_NAME LIKE '%BBB%' AND PAYMENT_AMT>2000;
```

**Output:**

<img width="1216" height="562" alt="image" src="https://github.com/user-attachments/assets/09a8786b-a28c-4719-9018-2152081a1a90" />

**Question 9**
---
Write a SQL query to Delete customers from 'customer' table where 'GRADE' is not equal to 3.

```sql
DELETE FROM Customer 
where GRADE != '3';
```

**Output:**

<img width="741" height="605" alt="image" src="https://github.com/user-attachments/assets/74353d7a-a836-4f4a-aa4b-de7c3fe1e075" />

**Question 10**
---
Write a SQL statement to Display the order number, orderdate and the purchase amount of
orders table which will be delivered by the salesman with ID 5001.

```sql
SELECT order_no,order_date,purch_amt from orders where salesman_id=5001;
```

**Output:**

<img width="917" height="484" alt="image" src="https://github.com/user-attachments/assets/df82cd80-eacb-4b79-8efa-7903b5e48a7c" />


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
