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
### Program: 
<img width="833" height="703" alt="image" src="https://github.com/user-attachments/assets/64199c57-63c7-4040-af3f-9027ded84991" />

**Expected Output:**  
Greater number is: 80

---

## 2. Write a PL/SQL program to Calculate Sum of First N Natural Numbers

### Steps:
- Declare a variable `n` and assign a value (e.g., 10).
- Initialize a `sum` variable to 0.
- Use a `WHILE` loop to iterate from 1 to `n`, adding each number to the sum.
- Display the result using `DBMS_OUTPUT.PUT_LINE`.
### Program: 
<img width="836" height="705" alt="image" src="https://github.com/user-attachments/assets/9303bd1c-c387-4115-b011-42a6586d7be6" />

**Expected Output:**  
Sum of first 10 natural numbers is: 55

---

## 3. Write a PL/SQL program to generate Fibonacci series

### Steps:
- Declare the variable `n` to indicate how many terms to generate.
- Initialize the first two Fibonacci numbers (0 and 1).
- Use a loop to generate the next terms using the formula `c = a + b`.
- Print each term in the series.
### Program: 
<img width="827" height="525" alt="image" src="https://github.com/user-attachments/assets/06d20afc-96f8-4650-8961-e4eeacd14be8" />
<img width="682" height="389" alt="image" src="https://github.com/user-attachments/assets/b70564a4-4b4b-4d81-9228-9bbcbfbfef73" />


**Expected Output:**  
n = 7  
Fibonacci sequence: 0, 1, 1, 2, 3, 5, 8

---

## 4. Write a PL/SQL Program to display the number in Reverse Order

### Steps:
- Declare a variable `n` and assign a value (e.g., 1535).
- Use a loop to extract each digit using modulo and reverse the number.
- Display the reversed number.
### Program: 
<img width="839" height="460" alt="image" src="https://github.com/user-attachments/assets/ede24df8-ac0e-441e-a5f2-8f2f7c70cd63" />
<img width="679" height="263" alt="image" src="https://github.com/user-attachments/assets/a61cf841-191e-458d-87fc-ed7614f0df78" />

**Expected Output:**  
n = 1535  
Reversed number is 5351

---

## 5. Write a PL/SQL program to find the largest of three numbers

### Steps:
- Declare three numeric variables `a`, `b`, and `c`.
- Use nested `IF-ELSIF-ELSE` conditions to find the largest among the three.
- Display the largest number.
### Program: 
<img width="827" height="467" alt="image" src="https://github.com/user-attachments/assets/201d6f24-4d2f-4e04-a2a2-030284eda04a" />
<img width="680" height="275" alt="image" src="https://github.com/user-attachments/assets/1d5e1f52-760f-42a5-a890-908bb879c9e5" />


**Expected Output:**  
a = 10, b = 9, c = 15  
Largest of three number is 15

## RESULT
Thus, the PL/SQL programs using variables, conditionals, and loops were executed successfully.

