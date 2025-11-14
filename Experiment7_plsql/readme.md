# Experiment 7: PL/SQL – Variables, Control Structures and Loops

## AIM
To write and execute simple PL/SQL programs using variables, loops, and conditional statements.


## THEORY

PL/SQL, which stands for Procedural Language extensions to the Structured Query Language (SQL). It is a combination of SQL along with the procedural features of programming languages.

**Syntax:**
```sql
DECLARE 
   <declarations section> 
BEGIN 
   <executable command(s)>
EXCEPTION 
   <exception handling> 
END;
```

### Basic Components of PL/SQL Block:
- DECLARE: Section to declare variables and constants.
- BEGIN: The execution section that contains PL/SQL statements.
- EXCEPTION: Handles errors or exceptions that occur in the program.
- END: Marks the end of the PL/SQL block.

# PL/SQL Programs – Steps and Expected Output

## 1. Write a PL/SQL program to find the Greatest of Two Numbers

### Steps:
- Declare two numeric variables and initialize them.
- Use an `IF` statement to compare the values.
- Display the greater number using `DBMS_OUTPUT.PUT_LINE`.

# Program:
<img width="638" height="240" alt="image" src="https://github.com/user-attachments/assets/f0774cf0-45aa-4d97-bb01-1a8df722b656" />


**Expected Output:**  
Greater number is: 80


# Output:
<img width="278" height="178" alt="image" src="https://github.com/user-attachments/assets/20a7b931-a35e-4b0b-ad9b-55ef0a210c0c" />


---

## 2. Write a PL/SQL program to Calculate Sum of First N Natural Numbers

### Steps:
- Declare a variable `n` and assign a value (e.g., 10).
- Initialize a `sum` variable to 0.
- Use a `WHILE` loop to iterate from 1 to `n`, adding each number to the sum.
- Display the result using `DBMS_OUTPUT.PUT_LINE`.


# Program:
<img width="799" height="303" alt="image" src="https://github.com/user-attachments/assets/4bcb056c-6d43-4067-a141-efc19464f530" />


**Expected Output:**  
Sum of first 10 natural numbers is: 55


# Output:
<img width="446" height="431" alt="image" src="https://github.com/user-attachments/assets/e333ae71-e7dd-4bc9-969f-29cd1303be67" />

---

## 3. Write a PL/SQL program to generate Fibonacci series

### Steps:
- Declare the variable `n` to indicate how many terms to generate.
- Initialize the first two Fibonacci numbers (0 and 1).
- Use a loop to generate the next terms using the formula `c = a + b`.
- Print each term in the series.

# Program:
<img width="681" height="360" alt="image" src="https://github.com/user-attachments/assets/e5185efe-526b-4716-bdee-9ce756c2410d" />


**Expected Output:**  
n = 7  
Fibonacci sequence: 0, 1, 1, 2, 3, 5, 8


# Output:
<img width="512" height="427" alt="image" src="https://github.com/user-attachments/assets/8aebed07-5cb5-4124-9a7b-11b022d197ad" />

---

## 4. Write a PL/SQL Program to display the number in Reverse Order

### Steps:
- Declare a variable `n` and assign a value (e.g., 1535).
- Use a loop to extract each digit using modulo and reverse the number.
- Display the reversed number.

# Program:
<img width="737" height="314" alt="image" src="https://github.com/user-attachments/assets/1238fd0f-04da-4bab-9e17-d3299692dcc7" />


**Expected Output:**  
n = 1535  
Reversed number is 5351


# Output:
<img width="532" height="343" alt="image" src="https://github.com/user-attachments/assets/fc4ec404-b0fa-4911-9d23-641c2f89b29b" />

---

## 5. Write a PL/SQL program to find the largest of three numbers

### Steps:
- Declare three numeric variables `a`, `b`, and `c`.
- Use nested `IF-ELSIF-ELSE` conditions to find the largest among the three.
- Display the largest number.

# Program:
<img width="717" height="342" alt="image" src="https://github.com/user-attachments/assets/b0eb88e9-9c81-4d52-9720-5ffa4044ebcf" />


**Expected Output:**  
a = 10, b = 9, c = 15  
Largest of three number is 15


# Output:
<img width="398" height="420" alt="image" src="https://github.com/user-attachments/assets/97c78993-726f-4d5e-bec6-3c11af982a0a" />

## RESULT
Thus, the PL/SQL programs using variables, conditionals, and loops were executed successfully.

