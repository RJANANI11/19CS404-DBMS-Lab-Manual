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
<img width="1117" height="256" alt="image" src="https://github.com/user-attachments/assets/0fbe0ab2-c70a-4227-86e4-533a6ffdbbfa" />


```sql
SELECT Diagnosis, COUNT(Diagnosis) AS DiagnosisCount
FROM MedicalRecords
GROUP BY Diagnosis
ORDER BY DiagnosisCount DESC
LIMIT 1;
```

**Output:**

<img width="1206" height="321" alt="image" src="https://github.com/user-attachments/assets/d347c9a5-fdc5-4f04-bb04-0efd7c13154c" />


**Question 2**
---
<img width="867" height="330" alt="image" src="https://github.com/user-attachments/assets/a94f5b76-f62e-4ba0-90fc-d72dd8e8337a" />


```sql
SELECT 
     DATE(AppointmentDateTime) AS AppointmentDate,
     COUNT(AppointmentID) AS TotalAppointments
FROM
   Appointments
GROUP BY
   AppointmentDate;
```

**Output:**

<img width="826" height="593" alt="image" src="https://github.com/user-attachments/assets/08a82fac-256e-499d-ab17-674b9a648646" />


**Question 3**
---
<img width="1153" height="249" alt="image" src="https://github.com/user-attachments/assets/2b69b17c-3a9f-4229-a2fd-16fbebc7855a" />


```sql
SELECT Specialty, COUNT(DoctorID) AS TotalDoctors
FROM Doctors
GROUP BY Specialty;

```

**Output:**

<img width="674" height="619" alt="image" src="https://github.com/user-attachments/assets/9a7a7939-2996-4933-98cc-34f38892cb80" />


**Question 4**
---
<img width="870" height="284" alt="image" src="https://github.com/user-attachments/assets/eab0fd56-3eb2-4863-972d-30afb529a95a" />

```sql
SELECT AVG(income) AS Average_Salary
FROM employee;
```

**Output:**

<img width="456" height="255" alt="image" src="https://github.com/user-attachments/assets/95342391-09b6-4d0e-b144-b2adcd4b0cd7" />


**Question 5**
---
<img width="809" height="295" alt="image" src="https://github.com/user-attachments/assets/38b39652-71a8-462d-b4b5-f81706672c1d" />


```sql
SELECT COUNT(customer_id) AS COUNT
FROM customer;

```

**Output:**

<img width="1179" height="260" alt="image" src="https://github.com/user-attachments/assets/70405e76-ff81-49d0-884f-6eea48e65308" />


**Question 6**
---


```sql
SELECT SUM(inventory) AS total_available_amount
FROM fruits
WHERE price>0.5;
```
**Output:**
<img width="588" height="235" alt="image" src="https://github.com/user-attachments/assets/4cd7c6d8-949a-4545-aa53-28aeff5e02c2" />

**Question 7**
---
<img width="1139" height="300" alt="image" src="https://github.com/user-attachments/assets/d23c939c-9dea-43fe-835f-7e58fafe0fea" />

```sql
SELECT SUM(workhour) AS "Total working hours"
FROM employee1;
```

**Output:**

<img width="494" height="241" alt="image" src="https://github.com/user-attachments/assets/f56d5c8d-a65a-4581-8def-f94e6da88787" />


**Question 8**
---
<img width="1248" height="300" alt="image" src="https://github.com/user-attachments/assets/ba3dcee7-f777-442b-8fa1-a140fafb78ad" />


```sql
SELECT city, AVG(income) AS "AVG(income)"
FROM employee
GROUP BY city
HAVING AVG(income)>500000;
```

**Output:**

<img width="584" height="362" alt="image" src="https://github.com/user-attachments/assets/88fa3170-3277-45a0-ad80-8370ef1992b3" />


**Question 9**
---
<img width="1199" height="248" alt="image" src="https://github.com/user-attachments/assets/20d4a1ac-30c8-47ab-9303-511a67506873" />

```sql
SELECT address, AVG(salary) AS "AVG(salary)"
FROM customer1
GROUP BY address
HAVING AVG(salary)>5000;
```

**Output:**

<img width="608" height="366" alt="image" src="https://github.com/user-attachments/assets/b7d646c8-4b3b-44e1-8e7a-8b69f76af10b" />

**Question 10**
---
<img width="1201" height="293" alt="image" src="https://github.com/user-attachments/assets/4dc4d635-8229-4a4a-9270-d23181226194" />

```sql
SELECT city, SUM(income) AS Income
FROM employee
GROUP BY city
HAVING SUM(income)>200000;
```

**Output:**
<img width="553" height="462" alt="image" src="https://github.com/user-attachments/assets/247b6d49-fd1a-4bc8-b7f8-a72e0909a408" />


![Output10](output.png)


## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
