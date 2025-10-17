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
<img width="949" height="303" alt="image" src="https://github.com/user-attachments/assets/f681969a-8c96-494c-ae4c-7713be209af2" />


```sql
UPDATE Products
SET quantity = quantity*1.10;
```

**Output:**

<img width="1227" height="628" alt="image" src="https://github.com/user-attachments/assets/3a4a4546-d964-4593-b016-57556d179292" />

**Question 2**
---
<img width="1192" height="289" alt="image" src="https://github.com/user-attachments/assets/48d7c12a-31ba-4457-97a7-540401b785e2" />


```sql
UPDATE sales
SET total_sell_price = quantity*sell_price
WHERE product_id = 10;
```

**Output:**
<img width="1228" height="521" alt="image" src="https://github.com/user-attachments/assets/6a9414d3-64ba-40aa-990c-7d7bca6673d3" />


**Question 3**
---
<img width="740" height="210" alt="image" src="https://github.com/user-attachments/assets/a83b0951-5f36-439d-9635-79a5968c2ffd" />

```sql
UPDATE products
SET availability= availability*2
WHERE product_id=1;
```

**Output:**

<img width="1228" height="250" alt="image" src="https://github.com/user-attachments/assets/a6834079-d3a2-4850-b5df-9f96a58d145d" />


**Question 4**
---
<img width="1205" height="422" alt="image" src="https://github.com/user-attachments/assets/c18a143b-73af-4d5f-b82f-f78bbeb2b846" />


```sql
UPDATE employees
SET salary = salary+500,email='updated'
WHERE job_id='SA_REP'
  AND commission_pct>0.15;
```

**Output:**

<img width="1220" height="521" alt="image" src="https://github.com/user-attachments/assets/aa43f5ae-e749-4ed8-846a-f8ea7783854d" />


**Question 5**
---
<img width="1228" height="584" alt="image" src="https://github.com/user-attachments/assets/3c0461b8-29f8-41b6-a70b-23dcd304b57f" />


```sql
DELETE FROM customer WHERE WORKING_AREA='New York';

```

**Output:**
<img width="1203" height="748" alt="image" src="https://github.com/user-attachments/assets/7ed7b78c-4a04-4b1d-a7aa-22f38dfc5e9f" />


**Question 6**
---
<img width="910" height="547" alt="image" src="https://github.com/user-attachments/assets/bc8ef6cb-cecc-4eb0-9e68-bcb989dd740d" />


```sql
DELETE from Doctors WHERE specialization ISNULL;
```

**Output:**

<img width="1218" height="968" alt="image" src="https://github.com/user-attachments/assets/82e2e2eb-2f76-46c1-86f1-d226900ff355" />


**Question 7**
---
<img width="777" height="555" alt="image" src="https://github.com/user-attachments/assets/384344b5-a621-45f6-a480-1afa19d97119" />


```sql
DELETE FROM Doctors
WHERE last_name IS NULL;
```

**Output:**

<img width="1212" height="734" alt="image" src="https://github.com/user-attachments/assets/6e8c7ebf-4ee2-48dc-bbc5-a390811372dd" />


**Question 8**
---
<img width="1221" height="541" alt="image" src="https://github.com/user-attachments/assets/eec40611-f1b5-4536-9205-59e6c66383b2" />

```sql
DELETE FROM customer
WHERE cust_name LIKE '%Holmes%';
```

**Output:**
<img width="1214" height="559" alt="image" src="https://github.com/user-attachments/assets/b275a75b-b6cd-41fc-adb4-5d21fd7c00b1" />


**Question 9**
---
<img width="1240" height="701" alt="image" src="https://github.com/user-attachments/assets/5fba00f1-5787-4b63-a67b-29b00a388b82" />

```sql
DELETE FROM customer 
WHERE GRADE>=2;
```

**Output:**
<img width="1214" height="559" alt="image" src="https://github.com/user-attachments/assets/159b07b7-8474-4d6d-bd30-d481a4f8b37a" />


**Question 10**
---
<img width="981" height="454" alt="image" src="https://github.com/user-attachments/assets/625c0dbe-335f-49ae-a5d3-88951f0cf952" />


```sql
SELECT * from EmployeeInfo WHERE EmpFname LIKE 'S%';
```

**Output:**
<img width="1215" height="280" alt="image" src="https://github.com/user-attachments/assets/7271b5c6-32cf-492c-b3ae-c3e0f12286c7" />




## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
