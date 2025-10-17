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
--<img width="940" height="308" alt="image" src="https://github.com/user-attachments/assets/f63b3979-a23f-465e-b7cf-37183351e52d" />


```sql
UPDATE Products
SET quantity = quantity*1.10;
```

**Output:**

![Output1](output.png)

**Question 2**
---
<img width="1176" height="478" alt="image" src="https://github.com/user-attachments/assets/0d351cde-fcf2-40d7-a31e-2422d9c45f11" />


```sql
UPDATE sales
SET total_sell_price = quantity*sell_price
WHERE product_id = 10;
```

**Output:**

<img width="1231" height="515" alt="image" src="https://github.com/user-attachments/assets/0e5832e2-65cb-49f0-9d9a-34d3ef1a2785" />



**Question 3**
---
<img width="727" height="226" alt="image" src="https://github.com/user-attachments/assets/41411ba8-9c1e-49b3-9fca-e801efc3f589" />


```sql
UPDATE products
SET availability= availability*2
WHERE product_id=1;
```

**Output:**

<img width="1233" height="234" alt="image" src="https://github.com/user-attachments/assets/01ca0b0a-e5d7-47f0-a5ce-fca7378bf151" />


**Question 4**
---
<img width="1208" height="422" alt="image" src="https://github.com/user-attachments/assets/99a96d65-bedd-44b1-baf2-eb2323f033a1" />


```sql
UPDATE employees
SET salary = salary+500,email='updated'
WHERE job_id='SA_REP'
  AND commission_pct>0.15;

```

**Output:**

<img width="1211" height="529" alt="image" src="https://github.com/user-attachments/assets/b96f8e8d-6ace-476c-8f22-8fa09444e475" />



**Question 5**
---

<img width="1232" height="272" alt="image" src="https://github.com/user-attachments/assets/18cf6f34-7306-4faa-bda3-b6225b7a0eb5" />



```sql
DELETE FROM customer WHERE WORKING_AREA='New York';
```

**Output:**


<img width="1191" height="800" alt="image" src="https://github.com/user-attachments/assets/e90aa40b-b9e3-4daa-bbef-e34d2ce840f9" />


**Question 6**
---

<img width="1146" height="548" alt="image" src="https://github.com/user-attachments/assets/334ba57b-32bd-4f67-bc6c-5ea76a7a3e7b" />


```sql
DELETE from Doctors WHERE specialization ISNULL;
```

**Output:**


<img width="1196" height="911" alt="image" src="https://github.com/user-attachments/assets/6bde74ca-8306-44bf-82ca-2c0894b06139" />


**Question 7**
---

<img width="895" height="562" alt="image" src="https://github.com/user-attachments/assets/1f62d804-45f3-43d1-aff2-cc3447f0d2f3" />

```sql
DELETE FROM Doctors
WHERE last_name IS NULL;
```

**Output:**


<img width="1201" height="649" alt="image" src="https://github.com/user-attachments/assets/0430fd01-3d7f-4d96-949d-202b607c55a2" />


**Question 8**
---

<img width="1205" height="549" alt="image" src="https://github.com/user-attachments/assets/b31876b2-1e15-4912-afee-92d854635f44" />

```sql
DELETE FROM customer
WHERE cust_name LIKE '%Holmes%';
```

**Output:**


<img width="1229" height="514" alt="image" src="https://github.com/user-attachments/assets/f5808098-b0f6-48cf-9828-82373bcd1f5e" />


**Question 9**
---

<img width="1231" height="674" alt="image" src="https://github.com/user-attachments/assets/61e85a94-98fe-4907-aadc-cee0068f5665" />


```sql
DELETE FROM customer 
WHERE GRADE>=2;
```

**Output:**


<img width="1218" height="572" alt="image" src="https://github.com/user-attachments/assets/4ee4cd3c-c516-42ea-9ee1-7cee137425bb" />


**Question 10**
---

<img width="994" height="406" alt="image" src="https://github.com/user-attachments/assets/5c152f84-9856-4a06-b5e5-a8b14a3faaaa" />


```sql
SELECT * from EmployeeInfo WHERE EmpFname LIKE 'S%';
```

**Output:**


<img width="1225" height="267" alt="image" src="https://github.com/user-attachments/assets/55d6c2c3-eb09-4fc0-91f3-2f6d4c2ebc3a" />


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
