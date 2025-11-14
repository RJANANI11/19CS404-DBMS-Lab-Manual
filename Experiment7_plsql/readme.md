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
# PROGRAM
<img width="726" height="310" alt="Screenshot 2025-11-14 111146" src="https://github.com/user-attachments/assets/7dc04aaa-f65e-4a68-81e5-ea0021fa9d18" />


**Expected Output:**  
<img width="388" height="220" alt="Screenshot 2025-11-14 111206" src="https://github.com/user-attachments/assets/548cf769-c520-4baa-8a16-d471e1445010" />

---

## 2. Write a PL/SQL program to Calculate Sum of First N Natural Numbers

### Steps:
- Declare a variable `n` and assign a value (e.g., 10).
- Initialize a `sum` variable to 0.
- Use a `WHILE` loop to iterate from 1 to `n`, adding each number to the sum.
- Display the result using `DBMS_OUTPUT.PUT_LINE`.
# PROGRAM
<img width="869" height="243" alt="Screenshot 2025-11-14 111741" src="https://github.com/user-attachments/assets/6d6879e5-4d29-4cb7-835f-aee283bba8fd" />


**Expected Output:**  
<img width="351" height="32" alt="Screenshot 2025-11-14 111750" src="https://github.com/user-attachments/assets/125e078c-6baa-4dfe-8460-80dd728546e8" />


---

## 3. Write a PL/SQL program to generate Fibonacci series

### Steps:
- Declare the variable `n` to indicate how many terms to generate.
- Initialize the first two Fibonacci numbers (0 and 1).
- Use a loop to generate the next terms using the formula `c = a + b`.
- Print each term in the series.
  # PROGRAM
  <img width="537" height="384" alt="Screenshot 2025-11-14 112154" src="https://github.com/user-attachments/assets/35493872-bfb9-48ce-9955-ec3150c5d473" />


**Expected Output:**  
<img width="428" height="116" alt="Screenshot 2025-11-14 112100" src="https://github.com/user-attachments/assets/daf2829c-20b5-40dd-867c-f84f85e27318" />


---

## 4. Write a PL/SQL Program to display the number in Reverse Order

### Steps:
- Declare a variable `n` and assign a value (e.g., 1535).
- Use a loop to extract each digit using modulo and reverse the number.
- Display the reversed number.
# PROGRAM
<img width="645" height="355" alt="Screenshot 2025-11-14 112503" src="https://github.com/user-attachments/assets/e32d84c1-9012-4b58-acab-17123a31adbb" />

**Expected Output:**  
<img width="272" height="58" alt="Screenshot 2025-11-14 112516" src="https://github.com/user-attachments/assets/a77dbfbc-a0f6-43cb-adce-087c197da9fe" />

---

## 5. Write a PL/SQL program to find the largest of three numbers

### Steps:
- Declare three numeric variables `a`, `b`, and `c`.
- Use nested `IF-ELSIF-ELSE` conditions to find the largest among the three.
- Display the largest number.
# PROGRAM
<img width="645" height="355" alt="Screenshot 2025-11-14 112503" src="https://github.com/user-attachments/assets/0ad67791-245d-42f6-aadb-a13c381fa505" />


**Expected Output:**  
<img width="272" height="58" alt="Screenshot 2025-11-14 112516" src="https://github.com/user-attachments/assets/a9d5cd28-4708-4d14-91cd-743007022bdb" />


## RESULT
Thus, the PL/SQL programs using variables, conditionals, and loops were executed successfully.

