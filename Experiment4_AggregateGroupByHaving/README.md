# Experiment 4: Aggregate Functions, Group By and Having Clause

## AIM
To study and implement aggregate functions, GROUP BY, and HAVING clause with suitable examples.

## THEORY

### Aggregate Functions
These perform calculations on a set of values and return a single value.

- **MIN()** – Smallest value  
- **MAX()** – Largest value  
- **COUNT()** – Number of rows  
- **SUM()** – Total of values  
- **AVG()** – Average of values

**Syntax:**
```sql
SELECT AGG_FUNC(column_name) FROM table_name WHERE condition;
```
### GROUP BY
Groups records with the same values in specified columns.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name;
```
### HAVING
Filters the grouped records based on aggregate conditions.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name
HAVING condition;
```

**Question 1**
--
How many prescriptions were written for each medication?

```sql
SELECT Medication,COUNT(PrescriptionID) AS TotalPrescriptions 
FROM Prescriptions 
GROUP BY Medication;
```

**Output:**

<img width="918" height="830" alt="image" src="https://github.com/user-attachments/assets/e7629315-af04-4d1f-a939-c7f35eda64ba" />


**Question 2**
---
How many prescriptions were written in each frequency category (e.g., once daily, twice daily)?

Sample tablePrescriptions Table

```sql
SELECT Frequency,COUNT(PrescriptionID) AS TotalPrescriptions 
FROM Prescriptions 
GROUP BY Frequency;
```

**Output:**

<img width="851" height="610" alt="image" src="https://github.com/user-attachments/assets/1c0656e6-1ac1-438c-a50c-c09339affe03" />


**Question 3**
---
How many doctors specialize in each medical specialty?

```sql
SELECT Specialty,COUNT(Specialty) AS TotalDocto 
FROM Doctors 
GROUP BY Specialty;
```

**Output:**

<img width="854" height="755" alt="image" src="https://github.com/user-attachments/assets/01680a0b-a26b-4748-8aac-6fc58b8eae6d" />


**Question 4**
---
Write a SQL query to find the total number of unique cities in the customer table?

```sql
SELECT COUNT(DISTINCT city) AS unique_cities
FROM customer;
```

**Output:**

<img width="611" height="387" alt="image" src="https://github.com/user-attachments/assets/1e65e6bc-5459-47c0-8549-d7fda8eb0435" />


**Question 5**
---
Write a SQL query to Calculate the average income of the employees with names starting with 'A': 

```sql
SELECT AVG(income) AS avg_income
FROM employee
where name LIKE 'A%';

```

**Output:**

<img width="447" height="388" alt="image" src="https://github.com/user-attachments/assets/70744658-d71b-43c4-a36e-245cf0813e02" />


**Question 6**
---
Write a SQL query to find the Fruit with the lowest available quantity.

```sql
SELECT name AS fruit_name,MIN(inventory) AS lowest_quantity
FROM fruits
ORDER BY inventory ASC LIMIT 1;
```

**Output:**

<img width="711" height="383" alt="image" src="https://github.com/user-attachments/assets/69072834-1c81-45a6-aa5b-d9147036c449" />


**Question 7**
---
Write a SQL query to find the maximum purchase amount.
```sql
SELECT MAX(purch_amt) AS MAXIMUM
FROM orders;
```

**Output:**

<img width="448" height="379" alt="image" src="https://github.com/user-attachments/assets/fecd5f85-c7d2-4fe8-b15f-b1e3cc11628b" />

**Question 8**
---
Write the SQL query that accomplishes the grouping of data by age intervals using the expression (age/5)5, calculates the minimum age for each group, and excludes groups where the minimum age is not less than 25.

```sql
SELECT (age/5)*5 AS age_group,MIN(age)
FROM customer1
GROUP BY age_group
HAVING MIN(age)<25;
```

**Output:**

<img width="628" height="390" alt="image" src="https://github.com/user-attachments/assets/fb945db7-0268-49e7-9893-e7b73d36688e" />


**Question 9**
---
Write the SQL query that performs grouping by age groups and displays the maximum salary for each group, excluding groups where the maximum salary is not greater than 8000. 

Note: Calculate the age group as multiples of 5.

Eg., 20,22,23 comes in age group 20. 

25,27,29 comes in age group 25.

```sql
SELECT (age/5)*5 AS age_group,MAX(salary)
FROM customer1
GROUP BY age_group
HAVING MAX(salary)>8000;
```

**Output:**

<img width="683" height="425" alt="image" src="https://github.com/user-attachments/assets/9e36cca4-a873-4552-9558-ed001e1abb25" />


**Question 10**
---
Write the SQL query that accomplishes the selection of total number of products for each category from the "products" table, and includes only those products where the minimum category ID is less than 3.

```sql
SELECT category_id,count(product_name) 
FROM products
where category_id<3
GROUP BY category_id;
```

**Output:**

<img width="834" height="435" alt="image" src="https://github.com/user-attachments/assets/f739788c-2b01-41ae-b4ce-4673229ef8b5" />



## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
