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
<img width="1360" height="293" alt="image" src="https://github.com/user-attachments/assets/bd1de13b-fd45-4ece-a0cf-d0285d10d1e3" />

```
INSERT INTO student_details (RollNo, Name, Gender, Subject, MARKS)
VALUES(201, 'David Lee', 'M', 'Physics', 92);
```

**Output:**

<img width="1240" height="329" alt="image" src="https://github.com/user-attachments/assets/9a2f01ce-90a1-4a8d-870c-91a5ce36c333" />


**Question 2**
<img width="1023" height="408" alt="image" src="https://github.com/user-attachments/assets/afca51e1-9944-471b-9d85-26d37723fbbe" />


```
CREATE TABLE Shipments(
    ShipmentID INT PRIMARY KEY,
    ShipmentDate DATE,
    SupplierID INT,
    OrderID INT,
    FOREIGN KEY(SupplierID) REFERENCES Suppliers(SupplierID),
    FOREIGN KEY (OrderID) REFERENCES Orders(OrderID)
);
```

**Output:**
<img width="1247" height="317" alt="image" src="https://github.com/user-attachments/assets/19886c28-fa69-4d7a-8126-82f4f9b87fa8" />


**Question 3**

<img width="1215" height="447" alt="image" src="https://github.com/user-attachments/assets/f27c8593-fee0-490d-9530-7e0bb4581d73" />


```
CREATE TABLE contacts(
    contact_id INTEGER PRIMARY KEY,
    first_name TEXT NOT NULL,
    last_name TEXT NOT NULL,
    email TEXT,
    phone TEXT NOT NULL CHECK(length(phone)>=10)
);
```

**Output:**

<img width="1228" height="417" alt="image" src="https://github.com/user-attachments/assets/df031407-2148-4668-9e55-946a988b4db9" />


**Question 4**
<img width="973" height="511" alt="image" src="https://github.com/user-attachments/assets/d241d8cc-226c-4b04-a053-062692e4ee2d" />


```
INSERT INTO Student_details(RollNo, Name, Gender, Subject, MARKS)
SELECT RollNo, Name, Gender, Subject, MARKS
FROM Archived_students;
```

**Output:**
<img width="1222" height="358" alt="image" src="https://github.com/user-attachments/assets/9354eaea-11e2-4f30-bfc6-c4e0af24a264" />


**Question 5**
<img width="1246" height="504" alt="image" src="https://github.com/user-attachments/assets/5cbe2df8-5cff-49ec-9d56-8eecced5da36" />


```
INSERT INTO Student_details(RollNo, Name, Gender, Subject, MARKS)
VALUES(202, 'Ella King', 'F', 'Chemistry',87);
INSERT INTO Student_details(RollNo, Name, Gender, Subject, MARKS)
VALUES(203, 'James Bond', 'M', 'Literature' , 78); 

```

**Output:**

<img width="1234" height="372" alt="image" src="https://github.com/user-attachments/assets/3eeedc9f-3709-4e3d-853d-aef9b04dfeea" />


**Question 6**
<img width="1400" height="488" alt="image" src="https://github.com/user-attachments/assets/f21c1bbc-ada6-4773-9887-89e4a706d3dd" />


```
CREATE TABLE orders(
     ord_id TEXT(4) NOT NULL,
     item_id TEXT NOT NULL,
     ord_date DATE,
     ord_qty INTEGER,
     cost INTEGER,
     PRIMARY KEY(item_id,ord_date)
);
INSERT INTO orders (ord_id, item_id, ord_date, ord_qty, cost) 
SELECT * FROM orders; 
```

**Output:**

<img width="1226" height="423" alt="image" src="https://github.com/user-attachments/assets/e4469a95-67a2-4069-b858-1ec9c99b71b2" />


**Question 7**
<img width="1388" height="382" alt="image" src="https://github.com/user-attachments/assets/cb62bc07-b3cf-4773-a2d5-1554045e5ae7" />


```
ALTER TABLE employee
ADD COLUMN first_name varchar(50);
ALTER TABLE employee
ADD COLUMN last_name varchar(50);
```

**Output:**
<img width="1222" height="400" alt="image" src="https://github.com/user-attachments/assets/bb7bf7fd-b228-417b-9601-cd01a2138c33" />


**Question 8**
<img width="1429" height="374" alt="image" src="https://github.com/user-attachments/assets/1f3c2ebb-6e0f-48fc-b9d1-857575f38c23" />


```
CREATE TABLE ProjectAssignments(
    AssignmentID INT PRIMARY KEY,
    EmployeeID INT,
    ProjectID INT,
    AssignmentDate DATE NOT NULL,
    FOREIGN KEY(EmployeeID) REFERENCES Employees(EmployeeID),
    FOREIGN KEY(ProjectID) REFERENCES Projects(ProjectID)
);
```

**Output:**

<img width="1220" height="375" alt="image" src="https://github.com/user-attachments/assets/7f6adce2-9b89-4f51-a075-63c9eab611d6" />


**Question 9**
<img width="1386" height="613" alt="image" src="https://github.com/user-attachments/assets/83f3d448-2abc-4abc-a00c-9b3abf90b3db" />


```
ALTER TABLE customer
ADD COLUMN birth_date timestamp;
```

**Output:**

<img width="1210" height="427" alt="image" src="https://github.com/user-attachments/assets/c11930d4-a334-44e0-a3a2-7cadf4bfed46" />


**Question 10**
<img width="1243" height="430" alt="image" src="https://github.com/user-attachments/assets/a776240f-9f9a-4627-9b2d-d9d1fa3a6ca0" />


```
CREATE TABLE Members(
    MemberID INTEGER,
    MemberName TEXT,
    JoinDate DATE
);
```

**Output:**

<img width="1227" height="447" alt="image" src="https://github.com/user-attachments/assets/508ea1a3-52e0-4a65-841b-e964d361fe1f" />



## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
