# Experiment 2: DDL Commands

## AIM
To study and implement DDL commands and different types of constraints.

## THEORY

### 1. CREATE
Used to create a new relation (table).

**Syntax:**
```sql
CREATE TABLE (
  field_1 data_type(size),
  field_2 data_type(size),
  ...
);
```
### 2. ALTER
Used to add, modify, drop, or rename fields in an existing relation.
(a) ADD
```sql
ALTER TABLE std ADD (Address CHAR(10));
```
(b) MODIFY
```sql
ALTER TABLE relation_name MODIFY (field_1 new_data_type(size));
```
(c) DROP
```sql
ALTER TABLE relation_name DROP COLUMN field_name;
```
(d) RENAME
```sql
ALTER TABLE relation_name RENAME COLUMN old_field_name TO new_field_name;
```
### 3. DROP TABLE
Used to permanently delete the structure and data of a table.
```sql
DROP TABLE relation_name;
```
### 4. RENAME
Used to rename an existing database object.
```sql
RENAME TABLE old_relation_name TO new_relation_name;
```
### CONSTRAINTS
Constraints are used to specify rules for the data in a table. If there is any violation between the constraint and the data action, the action is aborted by the constraint. It can be specified when the table is created (using CREATE TABLE) or after it is created (using ALTER TABLE).
### 1. NOT NULL
When a column is defined as NOT NULL, it becomes mandatory to enter a value in that column.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) NOT NULL
);
```
### 2. UNIQUE
Ensures that values in a column are unique.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) UNIQUE
);
```
### 3. CHECK
Specifies a condition that each row must satisfy.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) CHECK (logical_expression)
);
```
### 4. PRIMARY KEY
Used to uniquely identify each record in a table.
Properties:
Must contain unique values.
Cannot be null.
Should contain minimal fields.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) PRIMARY KEY
);
```
### 5. FOREIGN KEY
Used to reference the primary key of another table.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size),
  FOREIGN KEY (column_name) REFERENCES other_table(column)
);
```
### 6. DEFAULT
Used to insert a default value into a column if no value is specified.

Syntax:
```sql
CREATE TABLE Table_Name (
  col_name1 data_type,
  col_name2 data_type,
  col_name3 data_type DEFAULT 'default_value'
);
```

**Question 1**
--
Insert all products from Discontinued_products into Products.

Table attributes are ProductID, ProductName, Price, Stock

```sql
INSERT INTO Products 
SELECT ProductID, ProductName, Price, Stock from Discontinued_products;
```

**Output:**

<img width="1214" height="371" alt="image" src="https://github.com/user-attachments/assets/0ea38ca0-7283-4804-a965-165351d06285" />


**Question 2**
---
Write an SQL query to add two new columns, first_name and last_name, to the table employee. Both columns should have a data type of varchar(50).

```sql
ALTER TABLE employee
ADD first_name varchar(50);
ALTER TABLE employee
ADD last_name varchar(50);
```

**Output:**

<img width="1229" height="381" alt="image" src="https://github.com/user-attachments/assets/8a80f98c-f3d9-44b7-b4e5-0b7aa308cab5" />


**Question 3**
---
Create a new table named products with the following specifications:
product_id as INTEGER and primary key.
product_name as TEXT and not NULL.
list_price as DECIMAL (10, 2) and not NULL.
discount as DECIMAL (10, 2) with a default value of 0 and not NULL.
A CHECK constraint at the table level to ensure:
list_price is greater than or equal to discount
discount is greater than or equal to 0
list_price is greater than or equal to 0

```sql
CREATE TABLE products
(
product_id INTEGER PRIMARY KEY,
product_name TEXT NOT NULL,
list_price DECIMAL(10,2)NOT NULL CHECK(list_price>=discount),
discount DECIMAL(10,2) DEFAULT 0 NOT NULL CHECK(discount>=0)
)
```

**Output:**

<img width="1226" height="362" alt="image" src="https://github.com/user-attachments/assets/13802a7a-0af7-45ac-9fbc-c46d4fbd1a20" />


**Question 4**
---
Create a table named Shipments with the following constraints:
ShipmentID as INTEGER should be the primary key.
ShipmentDate as DATE.
SupplierID as INTEGER should be a foreign key referencing Suppliers(SupplierID).
OrderID as INTEGER should be a foreign key referencing Orders(OrderID).

```sql
CREATE TABLE Shipments
(
ShipmentID INTEGER PRIMARY KEY,
ShipmentDate DATE,
SupplierID INTEGER,
OrderID INTEGER,
FOREIGN KEY(SupplierID) REFERENCES Suppliers(SupplierID),
FOREIGN KEY(OrderID) REFERENCES Orders(OrderID)
);

```

**Output:**

<img width="1228" height="319" alt="image" src="https://github.com/user-attachments/assets/a72d812d-54d0-4b3a-af62-4caf0fe4e510" />


**Question 5**
---
In the Student_details table, insert a student record where some fields are NULL, another record where all fields are filled without any NULL values, and a third record where some fields are filled, and others are left as NULL.

```sql
INSERT INTO Student_details (RollNo, Name,Gender) 
VALUES (205,'Olivia Green','F');
INSERT INTO Student_details(RollNo,Name,Gender,Subject,MARKS) 
VALUES(207, 'Liam Smith','M','Mathematic',85);
INSERT INTO Student_details(RollNo,Name,Gender,Subject)
VALUES(208,'Sophia Johns','F','Science');
```

**Output:**

<img width="1215" height="375" alt="image" src="https://github.com/user-attachments/assets/bec7ad98-3876-4416-a062-ec930fcef836" />


**Question 6**
---
Insert all customers from Old_customers into Customers

Table attributes are CustomerID, Name, Address, Email

```sql
INSERT INTO Customers
SELECT  CustomerID, Name, Address, Email FROM Old_customers;
```

**Output:**

<img width="1227" height="309" alt="image" src="https://github.com/user-attachments/assets/bf20002a-de5a-400b-b79f-9604fea56af9" />


**Question 7**
---
Write a SQL query to Add a new column named "discount" with the data type DECIMAL(5,2) to the "customer" table.

Sample table: customer

```sql
ALTER TABLE customer
ADD discount DECIMAL(5,2);
```

**Output:**

<img width="1233" height="447" alt="image" src="https://github.com/user-attachments/assets/3c0b9b56-f467-4d3c-94a0-73e1eecc5a0f" />


**Question 8**
---
Create a table named Employees with the following constraints:

EmployeeID should be the primary key.
FirstName and LastName should be NOT NULL.
Email should be unique.
Salary should be greater than 0.
DepartmentID should be a foreign key referencing the Departments table.

```sql
CREATE TABLE Employees(
EmployeeID Int primary key,
FirstName varchar(50) not null,
LastName varchar(50) not null,
Email text UNIQUE,
Salary INT CHECK(Salary>0),
DepartmentID int,
FOREIGN KEY(DepartmentID) REFERENCES  Departments(DepartmentID)
);
```

**Output:**

<img width="1228" height="509" alt="image" src="https://github.com/user-attachments/assets/d696617f-a21c-4332-96b8-7841951c912a" />


**Question 9**
---
Insert a customer with CustomerID 301, Name Michael Jordan, Address 123 Maple St, City Chicago, and ZipCode 60616 into the Customers table.

```sql
INSERT INTO Customers
VALUES(301,'Michael Jordan','123 Maple St','Chicago',60616);
```

**Output:**

<img width="1220" height="320" alt="image" src="https://github.com/user-attachments/assets/1ed11a50-842f-4ef3-83d1-858d9df697fb" />


**Question 10**
---
Create a table named Members with the following columns:

MemberID as INTEGER
MemberName as TEXT
JoinDate as DATE

```sql
CREATE TABLE Members(
MemberID INTEGER,
MemberName TEXT,
JoinDate DATE 
);
```

**Output:**
<img width="1219" height="446" alt="image" src="https://github.com/user-attachments/assets/e49695cc-7acc-40e9-8af1-e8182493d492" />


## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
