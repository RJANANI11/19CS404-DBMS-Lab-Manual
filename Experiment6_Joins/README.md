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
From the following tables write a SQL query to find the details of an order. Return ord_no, ord_date, purch_amt, Customer Name, grade, Salesman, commission. 

```sql
SELECT
    o.ord_no,
    o.ord_date,
    o.purch_amt,
    c.cust_name AS "Customer Name",
    c.grade,
    s.name AS Salesman,
    s.commission
FROM
    orders o
JOIN
    customer c ON o.customer_id = c.customer_id
JOIN
    salesman s ON o.salesman_id = s.salesman_id;
```

**Output:**

<img width="1253" height="786" alt="Screenshot 2025-11-14 104717" src="https://github.com/user-attachments/assets/1f00d7d4-4a3f-4a2a-b22b-f4ed72e6ca60" />


**Question 2**
---
Write a SQL statement to make a report with customer name, city, order number, order date, and order amount in ascending order according to the order date to determine whether any of the existing customers have placed an order or not.

```sql
SELECT
    c.cust_name,
    c.city,
    o.ord_no,
    o.ord_date,
    o.purch_amt AS "Order Amount"
FROM
    customer c
LEFT JOIN
    orders o ON c.customer_id = o.customer_id
ORDER BY
    o.ord_date ASC;
```

**Output:**

<img width="1257" height="776" alt="Screenshot 2025-11-14 104833" src="https://github.com/user-attachments/assets/6a52bc4a-5f8e-434b-be37-ae48a77d15d4" />


**Question 3**
---
Write the SQL query that achieves the selection of the first name from the "patients" table and all columns from the "surgeries" table, with an inner join on the "patient_id" column and a condition filtering for patients with a date of birth after '1990-01-01'.

```sql
SELECT
    p.first_name,
    s.*
FROM
    patients p
INNER JOIN
    surgeries s ON p.patient_id = s.patient_id
WHERE
    p.date_of_birth > '1990-01-01';
```

**Output:**

<img width="1275" height="414" alt="image" src="https://github.com/user-attachments/assets/5634081b-23b1-4a31-98ef-c07d5afae0ef" />


**Question 4**
---
Write an SQL query to retrieve all columns from the 'customer' table (aliased as 'c') using a LEFT JOIN with the 'orders' table on the 'customer_id' column, and filter the results to include only those orders placed between '2012-07-01' and '2012-07-30'.

```sql
SELECT
    c.*
FROM
    customer c
LEFT JOIN
    orders o ON c.customer_id = o.customer_id
WHERE
    o.ord_date BETWEEN '2012-07-01' AND '2012-07-30';
```

**Output:**

<img width="1246" height="376" alt="image" src="https://github.com/user-attachments/assets/27ce81c6-1439-408d-b8f0-8c4aa3118394" />


**Question 5**
---
Write a SQL statement to join the tables salesman, customer and orders so that the same column of each table appears once and only the relational rows are returned. 

```sql
SELECT
    o.ord_no,
    o.purch_amt,
    o.ord_date,
    c.cust_name,
    c.city AS customer_city,
    c.grade,
    s.name AS salesman_name,
    s.city AS salesman_city,
    s.commission
FROM
    orders o
JOIN
    customer c ON o.customer_id = c.customer_id
JOIN
    salesman s ON o.salesman_id = s.salesman_id;
```

**Output:**

<img width="1242" height="900" alt="image" src="https://github.com/user-attachments/assets/e01c1497-1651-4e6a-8b4c-80fc5bd6530a" />


**Question 6**
---
Write the SQL query that achieves the selection of the first name from the "patients" table (aliased as "patient_name") and all columns from the "appointments" table (aliased as "a"), with an inner join on the "patient_id" column.

```sql
SELECT
    p.first_name AS patient_name,
    a.*
FROM
    patients p
INNER JOIN
    appointments a ON p.patient_id = a.patient_id;
```

**Output:**

<img width="1225" height="490" alt="image" src="https://github.com/user-attachments/assets/63a4605d-4b76-4e9b-b694-ce161a6262fb" />


**Question 7**
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
JOIN
    customer c ON o.customer_id = c.customer_id
WHERE
    o.purch_amt BETWEEN 500 AND 2000;
```

**Output:**

<img width="1238" height="410" alt="image" src="https://github.com/user-attachments/assets/25da8e04-97ee-4aff-8ed1-2522fbb8f24c" />


**Question 8**
---
Write the SQL query that achieves the selection of all columns from the "test_results" table (aliased as "t"), with an inner join on the "patient_id" column and a condition filtering for patients with the first name 'Alice'.
```sql
SELECT
    t.*
FROM
    test_results t
INNER JOIN
    patients p ON t.patient_id = p.patient_id
WHERE
    p.first_name = 'Alice';


```

**Output:**
<img width="1295" height="388" alt="image" src="https://github.com/user-attachments/assets/4416b647-2f1b-43b9-892d-27a8bbfc83ff" />


**Question 9**
---
Write the SQL query that achieves the selection of the "cust_name" column from the "customer" table (aliased as "c"), and the "ord_no," "ord_date," and "purch_amt" columns from the "orders" table (aliased as "o"), with a left join on the "customer_id" column.
```sql
SELECT
    c.cust_name,
    o.ord_no,
    o.ord_date,
    o.purch_amt
FROM
    customer c
LEFT JOIN
    orders o ON c.customer_id = o.customer_id;
```

**Output:**

<img width="1252" height="755" alt="image" src="https://github.com/user-attachments/assets/ec378628-deca-4130-9704-8794401d9c85" />


**Question 10**
---
Write the SQL query that achieves the selection of the first name from the "patients" table (aliased as "patient_name") and all columns from the "test_results" table (aliased as "t"), with an inner join on the "patient_id" column and a condition filtering for test results with the test name 'Blood Pressure'.

```sql
SELECT
    pn.first_name AS patient_name,
    t.*
FROM
    patients pn
INNER JOIN
    test_results t ON pn.patient_id = t.patient_id
WHERE
    t.test_name = 'Blood Pressure';
```

**Output:**

<img width="1244" height="396" alt="image" src="https://github.com/user-attachments/assets/0fc10901-f558-405f-8af1-834a0bf3fe63" />



## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
