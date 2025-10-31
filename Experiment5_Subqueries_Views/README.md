# Experiment 5: Subqueries and Views

## AIM
To study and implement subqueries and views.

## THEORY

### Subqueries
A subquery is a query inside another SQL query and is embedded in:
- WHERE clause
- HAVING clause
- FROM clause

**Types:**
- **Single-row subquery**:
  Sub queries can also return more than one value. Such results should be made use along with the operators in and any.
- **Multiple-row subquery**:
  Here more than one subquery is used. These multiple sub queries are combined by means of ‘and’ & ‘or’ keywords.
- **Correlated subquery**:
  A subquery is evaluated once for the entire parent statement whereas a correlated Sub query is evaluated once per row processed by the parent statement.

**Example:**
```sql
SELECT * FROM employees
WHERE salary > (SELECT AVG(salary) FROM employees);
```
### Views
A view is a virtual table based on the result of an SQL SELECT query.
**Create View:**
```sql
CREATE VIEW view_name AS
SELECT column1, column2 FROM table_name WHERE condition;
```
**Drop View:**
```sql
DROP VIEW view_name;
```

**Question 1**
--
From the following tables write a SQL query to count the number of customers with grades above the average in New York City. Return grade and count.
``sql
```SELECT grade, COUNT(*) 
FROM customer
WHERE grade > (
    SELECT AVG(grade) 
    FROM customer 
    WHERE city = 'New York'
)
GROUP BY grade;



```

**Output:**

<img width="886" height="322" alt="image" src="https://github.com/user-attachments/assets/39ef352a-734f-4d40-b63c-25d9bf3881bf" />


**Question 2**
---
From the following tables, write a SQL query to find all the orders issued by the salesman 'Paul Adam'. Return ord_no, purch_amt, ord_date, customer_id and salesman_id.

```sql
SELECT ord_no, purch_amt, ord_date, customer_id, orders.salesman_id
FROM orders
JOIN salesman ON orders.salesman_id = salesman.salesman_id
WHERE salesman.name = 'Paul Adam';

```

**Output:**

<img width="1237" height="347" alt="image" src="https://github.com/user-attachments/assets/97a46d70-9d0d-40b3-831b-ee6404e180cf" />

**Question 3**
---
From the following tables, write a SQL query to find those salespeople who earned the maximum commission. Return ord_no, purch_amt, ord_date, and salesman_id.
```sql
SELECT ord_no, purch_amt, ord_date, orders.salesman_id
FROM orders
JOIN salesman ON orders.salesman_id = salesman.salesman_id
WHERE salesman.commission = (
    SELECT MAX(commission) FROM salesman
);

```

**Output:**

<img width="1011" height="406" alt="image" src="https://github.com/user-attachments/assets/71e27164-dbaf-488e-8935-170c4f58a3e9" />

**Question 4**
---
Write a SQL query to retrieve all columns from the CUSTOMERS table for customers whose salary is LESS than $2500.
```sql
SELECT *
FROM CUSTOMERS
WHERE SALARY < 2500;

```

**Output:**

<img width="1237" height="421" alt="image" src="https://github.com/user-attachments/assets/cdc22a7f-0546-4eaa-9561-cd9451474b2a" />

**Question 5**
---
Write a SQL query to Find employees who have an age less than the average age of employees with incomes over 2.5 Lakh

```sql
SELECT *
FROM Employee
WHERE age < (
    SELECT AVG(age)
    FROM Employee
    WHERE income > 250000
);

```

**Output:**

<img width="1237" height="481" alt="image" src="https://github.com/user-attachments/assets/8426ce5b-6fda-46a0-ba93-b1b537a990c6" />


**Question 6**
---
Write a SQL query to Retrieve the names of customers who have a phone number that is not shared with any other customer.
```sql
SELECT name
FROM customer
WHERE phone IN (
    SELECT phone
    FROM customer
    GROUP BY phone
    HAVING COUNT(phone) = 1
);

```

**Output:**

<img width="546" height="404" alt="image" src="https://github.com/user-attachments/assets/402e783c-4691-47aa-8650-adf306a6580c" />

**Question 7**
---
Write a SQL query to Retrieve the names and cities of customers who have the same city as customers with IDs 3 and 7

```sql
SELECT name, city
FROM customer
WHERE city IN (
    SELECT city
    FROM customer
    WHERE id IN (3, 7)
);

```

**Output:**

<img width="597" height="417" alt="image" src="https://github.com/user-attachments/assets/d98ebd88-ad02-4acb-b124-61f7034215c2" />


**Question 8**
---
Write a SQL query to Find employees who have an age less than the average age of employees with incomes over 1 million
```sql
SELECT id, name, age, city, income
FROM Employee
WHERE age < (
    SELECT AVG(age)
    FROM Employee
    WHERE income > 1000000
);

```

**Output:**

<img width="1258" height="396" alt="image" src="https://github.com/user-attachments/assets/b0518c11-b765-4c83-bf2c-8bfd60188999" />


**Question 9**
---
Write a SQL query to Identify customers whose city is different from the city of the customer with the highest ID

```sql
SELECT id, name, city, email, phone
FROM customer
WHERE city <> (
    SELECT city
    FROM customer
    WHERE id = (
        SELECT MAX(id)
        FROM customer
    )
);

```

**Output:**

<img width="1245" height="452" alt="image" src="https://github.com/user-attachments/assets/55571c7e-d713-4c3f-b52b-6f69742c753d" />


**Question 10**
---
Write a SQL query that retrieves the names of students and their corresponding grades, where the grade is equal to the maximum grade achieved in each subject.

```sql
SELECT student_name, grade
FROM GRADES g
WHERE grade = (
    SELECT MAX(grade)
    FROM GRADES
    WHERE subject = g.subject
);

```

**Output:**
<img width="745" height="371" alt="image" src="https://github.com/user-attachments/assets/8bf4af57-931e-4477-b2de-ebda2f49a533" />



## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
