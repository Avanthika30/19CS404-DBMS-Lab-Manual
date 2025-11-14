# Experiment 6: Joins

## AIM
To study and implement different types of joins.

## THEORY

SQL Joins are used to combine records from two or more tables based on a related column.

### 1. INNER JOIN
Returns records with matching values in both tables.

**Syntax:**
```sql
SELECT columns
FROM table1
INNER JOIN table2
ON table1.column = table2.column;
```

### 2. LEFT JOIN
Returns all records from the left table, and matched records from the right.

**Syntax:**

```sql
SELECT columns
FROM table1
LEFT JOIN table2
ON table1.column = table2.column;
```
### 3. RIGHT JOIN
Returns all records from the right table, and matched records from the left.

**Syntax:**

```sql
SELECT columns
FROM table1
RIGHT JOIN table2
ON table1.column = table2.column;
```
### 4. FULL OUTER JOIN
Returns all records when there is a match in either left or right table.

**Syntax:**

```sql
SELECT columns
FROM table1
FULL OUTER JOIN table2
ON table1.column = table2.column;
```

**Question 1**
--
Write the SQL query that achieves the selection of the first name from the "patients" table, with an inner join on the "patient_id" column and a condition filtering for surgeries with a surgery date of '2024-01-15'.

```sql
SELECT p.first_name
FROM patients p
INNER JOIN surgeries s
ON p.patient_id = s.patient_id
WHERE s.surgery_date = '2024-01-15';
```

**Output:**

<img width="520" height="459" alt="image" src="https://github.com/user-attachments/assets/ffb6babb-65f3-4773-830c-6d772eab05f1" />

**Question 2**
---
From the following tables write a SQL query to find salespeople who received commissions of more than 12 percent from the company. Return Customer Name, customer city, Salesman, commission.  

Sample table: customer

```sql
SELECT 
    c.cust_name AS "Customer Name",
    c.city AS "city",
    s.name AS "Salesman",
    s.commission
FROM 
    customer c
INNER JOIN 
    salesman s
ON 
    c.salesman_id = s.salesman_id
WHERE 
    s.commission > 0.12;
```

**Output:**

<img width="1219" height="865" alt="image" src="https://github.com/user-attachments/assets/f569a5d0-1d46-41e2-a53d-cc49aee5d108" />

**Question 3**
---
Write the SQL query that achieves the selection of all columns from the "test_results" table (aliased as "t"), with an inner join on the "patient_id" column and a condition filtering for patients with the first name 'Alice'.
```sql
SELECT t.*
FROM test_results t
INNER JOIN patients p
ON t.patient_id = p.patient_id
WHERE p.first_name = 'Alice';
```

**Output:**

<img width="1279" height="352" alt="image" src="https://github.com/user-attachments/assets/6ee7d7b2-80ea-490c-a654-3eec4527aa48" />

**Question 4**
---
From the following tables write a SQL query to find those orders where the order amount exists between 500 and 2000. Return ord_no, purch_amt, cust_name, city.

```sql
SELECT 
    o.ord_no,
    o.purch_amt,
    c.cust_name,
    c.city
FROM 
    orders o
INNER JOIN 
    customer c
ON 
    o.customer_id = c.customer_id
WHERE 
    o.purch_amt BETWEEN 500 AND 2000;
```

**Output:**

<img width="1144" height="409" alt="image" src="https://github.com/user-attachments/assets/25298e20-4298-4b6a-bf86-ca11246921d4" />

**Question 5**
---
From the following tables write a SQL query to find those orders where the order amount exists between 500 and 2000. Return ord_no, purch_amt, cust_name, city.

Sample table: customer

```sql
SELECT 
    o.ord_no,
    o.purch_amt,
    c.cust_name,
    c.city
FROM 
    orders o
INNER JOIN 
    customer c
ON 
    o.customer_id = c.customer_id
WHERE 
    o.purch_amt BETWEEN 500 AND 2000;
```

**Output:**

<img width="1272" height="624" alt="image" src="https://github.com/user-attachments/assets/4712fa4b-76f7-4d82-a1fe-a824afd3c859" />

**Question 6**
---
From the following tables write a SQL query to display the customer name, customer city, grade, salesman, salesman city. The results should be sorted by ascending customer_id.  

Sample table: customer

```sql
SELECT 
    c.cust_name AS "cust_name",
    c.city AS "city",
    c.grade,
    s.name AS "Salesman",
    s.city AS "city"
FROM 
    customer c
INNER JOIN 
    salesman s
ON 
    c.salesman_id = s.salesman_id
ORDER BY 
    c.customer_id ASC;
```

**Output:**

<img width="1233" height="743" alt="image" src="https://github.com/user-attachments/assets/281759d2-bb80-4609-b498-053ea3331371" />

**Question 7**
---
write a SQL query to find the salesperson and customer who reside in the same city. Return Salesman, cust_name and city.
```sql
SELECT 
    s.name AS "Salesman",
    c.cust_name,
    c.city
FROM 
    salesman s
INNER JOIN 
    customer c
ON 
    s.city = c.city;
```

**Output:**

<img width="814" height="575" alt="image" src="https://github.com/user-attachments/assets/c26a7d27-c62c-48d1-91fb-b0b5e2aa6b45" />

**Question 8**
---
Write the SQL query that achieves the selection of all columns from the "customer" table (aliased as "c"), with a left join on the "salesman_id" column and a condition filtering for salesman with the name 'Mc Lyon'.

Customer Table: (customer_id, cust_name, city, grade, salesman_id)

Salesman Table: (salesman_id, name, city, commission)

```sql
SELECT 
    c.*
FROM 
    customer c
LEFT JOIN 
    salesman s
ON 
    c.salesman_id = s.salesman_id
WHERE 
    s.name = 'Mc Lyon';
```

**Output:**

<img width="1195" height="346" alt="image" src="https://github.com/user-attachments/assets/1f94b42e-04d4-4bd6-bb59-525edcfce694" />

**Question 9**
---
Write the SQL query that achieves the selection of the "name" column from the "salesman" table (aliased as "s"), the "cust_name," "city," "grade," and "salesman_id" columns from the "customer" table (aliased as "c"), with a left join on the "salesman_id" column and a condition filtering for salesman_id values that have more than one associated customer.

Customer Table: (customer_id, cust_name, city, grade, salesman_id)

Salesman Table: (salesman_id, name, city, commission)

```sql
SELECT 
    s.name,
    c.cust_name,
    c.city,
    c.grade,
    c.salesman_id
FROM 
    salesman s
LEFT JOIN 
    customer c
ON 
    s.salesman_id = c.salesman_id
WHERE 
    c.salesman_id IN (
        SELECT salesman_id
        FROM customer
        GROUP BY salesman_id
        HAVING COUNT(*) > 1
    )
ORDER BY c.grade;
```

**Output:**

<img width="1204" height="513" alt="image" src="https://github.com/user-attachments/assets/7e334c11-b1da-4de5-b467-c5c3b64f6c6a" />

**Question 10**
---
From the following tables write a SQL query to find the salesperson(s) and the customer(s) he represents. Return Customer Name, city, Salesman, commission.
```sql
SELECT 
    c.cust_name AS "Customer Name",
    c.city AS "city",
    s.name AS "Salesman",
    s.commission
FROM 
    customer c
INNER JOIN 
    salesman s
ON 
    c.salesman_id = s.salesman_id;
```

**Output:**

<img width="1034" height="741" alt="image" src="https://github.com/user-attachments/assets/f6aeca19-1be1-4ce8-9876-48cef99d4f9a" />


## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
