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
-- Create a new table named contacts with the following specifications:
contact_id as INTEGER and primary key.
first_name as TEXT and not NULL.
last_name as TEXT and not NULL.
email as TEXT.
phone as TEXT and not NULL with a check constraint to ensure the length of phone is at least 10 characters.

```sql
-- CREATE TABLE contacts(
contact_id INTEGER PRIMARY KEY, 
first_name TEXT NOT NULL,
last_name TEXT NOT NULL, 
email TEXT,
phone TEXT NOT NULL CHECK(LENGTH(phone) >= 10)); 
```

**Output:**

<img width="1189" height="312" alt="image" src="https://github.com/user-attachments/assets/7c4dc73a-8ee9-495b-b6fe-4aa830401a2e" />


**Question 2**
---
-- Insert a student with RollNo 201, Name David Lee, Gender M, Subject Physics, and MARKS 92 into the Student_details table.

```sql
-- INSERT INTO Student_details(RollNo, Name, Gender, Subject, MARKS)
VALUES(201, "David Lee", "M", "Physics", 92);
```

**Output:**

<img width="1223" height="252" alt="image" src="https://github.com/user-attachments/assets/33861cae-4a7d-4511-b4a1-79b2cf9a6ce5" />


**Question 3**
---
-- Create a table named Locations with the following columns:

LocationID as INTEGER
LocationName as TEXT
Address as TEXT

```sql
--  CREATE TABLE Locations(
LocationID INTEGER,
LocationName TEXT,
Address TEXT);
```

**Output:**

<img width="1202" height="386" alt="image" src="https://github.com/user-attachments/assets/6ab17a96-de33-434f-ac33-3f8f3c4696ba" />


**Question 4**
---
-- Write a SQL query to add a new column MobileNumber of type NUMBER and a new column Address of type VARCHAR(100) to the Student_details table.

```sql
--  ALTER TABLE Student_details ADD MobileNumber NUMBER; 
ALTER TABLE Student_details ADD Address VARCHAR(100);
```

**Output:**

<img width="1208" height="400" alt="image" src="https://github.com/user-attachments/assets/05824a9e-f77e-4fb6-a7a6-0a6a74a89dbb" />


**Question 5**
---
-- Create a table named Bonuses with the following constraints:
BonusID as INTEGER should be the primary key.
EmployeeID as INTEGER should be a foreign key referencing Employees(EmployeeID).
BonusAmount as REAL should be greater than 0.
BonusDate as DATE.
Reason as TEXT should not be NULL.

```sql
-- CREATE TABLE Bonuses(
BonusID INTEGER PRIMARY KEY,
EmployeeID INTERGER,
BonusAmount REAL CHECK(BonusAmount > 0),
BonusDate DATE, 
Reason TEXT NOT NULL,
FOREIGN KEY(EmployeeID) REFERENCES Employees(EmployeeID)); 
```

**Output:**

<img width="1214" height="295" alt="image" src="https://github.com/user-attachments/assets/768318a2-23b7-4402-85b9-77c2d72c6811" />


**Question 6**
---
-- Insert all products from Discontinued_products into Products.
Table attributes are ProductID, ProductName, Price, Stock

```sql
-- INSERT into Products(ProductID, ProductName, Price, Stock)
SELECT ProductID, ProductName, Price, Stock from Discontinued_products;
```

**Output:**

<img width="1206" height="299" alt="image" src="https://github.com/user-attachments/assets/23806a80-f126-4d12-b32d-d8e59bf58753" />


**Question 7**
---
-- Create a table named Invoices with the following constraints:
InvoiceID as INTEGER should be the primary key.
InvoiceDate as DATE.
Amount as REAL should be greater than 0.
DueDate as DATE should be greater than the InvoiceDate.
OrderID as INTEGER should be a foreign key referencing Orders(OrderID).


```sql
-- CREATE TABLE Invoices(
InvoiceID INTEGER PRIMARY KEY,
InvoiceDate DATE,
Amount REAL CHECK(Amount > 0),
DueDate DATE CHECK (DueDate > InvoiceDate),
OrderID INTEGER,
FOREIGN KEY (OrderID) REFERENCES Orders(OrderID)); 
```

**Output:**

<img width="1222" height="295" alt="image" src="https://github.com/user-attachments/assets/87aa3c74-3101-49c3-b589-c0de6bee3790" />


**Question 8**
---
-- Write a SQL query to Add a new column State as text in the Student_details table.

```sql
-- ALTER TABLE Student_details 
ADD State TEXT; 
```
**Output:**

<img width="1206" height="377" alt="image" src="https://github.com/user-attachments/assets/61a5753e-a28f-4835-8f56-6230dca31b7f" />


**Question 9**
---
-- In the Student_details table, insert a student record where some fields are NULL, another record where all fields are filled without any NULL values, and a third record where some fields are filled, and others are left as NULL.

```sql
-- INSERT into Student_details(RollNo, Name, Gender, Subject, MARKS)
values(205, "Olivia Green", "F", NULL, NULL);
INSERT into Student_details(RollNo, Name, Gender, Subject, MARKS)
values(207, "Liam Smith", "M", "Mathematic", 85);
INSERT into Student_details(RollNo, Name, Gender, Subject, MARKS)
values(208, "Sophia Johns", "F", "Science", NULL); 
```

**Output:**
<img width="1215" height="300" alt="image" src="https://github.com/user-attachments/assets/be65637c-ada4-4efd-8eb5-85806200c9f0" />



**Question 10**
---
-- Create a table named ProjectAssignments with the following constraints:
AssignmentID as INTEGER should be the primary key.
EmployeeID as INTEGER should be a foreign key referencing Employees(EmployeeID).
ProjectID as INTEGER should be a foreign key referencing Projects(ProjectID).
AssignmentDate as DATE should be NOT NULL.

```sql
-- CREATE TABLE ProjectAssignments(
AssignmentID INTEGER PRIMARY KEY,
EmployeeID INTEGER,
ProjectID INTEGER,
AssignmentDate DATE NOT NULL,
FOREIGN KEY (EmployeeID) REFERENCES Employees(EmployeeID),
FOREIGN KEY (ProjectID) REFERENCES Projects(ProjectID)); 
```

**Output:**

<img width="1207" height="287" alt="image" src="https://github.com/user-attachments/assets/98360cf0-310a-4f66-9154-f530ce03db49" />



## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
