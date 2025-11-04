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
<img width="995" height="143" alt="image" src="https://github.com/user-attachments/assets/b945a6a1-e232-41a5-8f8c-9e0d44dccc2c" />


```
UPDATE customer
SET grade = 5
WHERE city = 'Chennai';
```

**Output:**
<img width="1249" height="543" alt="image" src="https://github.com/user-attachments/assets/6933e05e-4e1e-43f4-9f9d-80dc10ef132c" />


**Question 2**

<img width="1402" height="834" alt="image" src="https://github.com/user-attachments/assets/f404d281-dfd9-4c05-85d3-7d98c0b5a651" />


```
UPDATE employees
SET salary = CASE 
    WHEN department_id = 40 THEN ROUND(salary * 1.25 )
    WHEN department_id = 90 THEN ROUND(salary * 1.15 )
    WHEN department_id = 110 THEN ROUND(salary * 1.10 )
    ELSE salary
END;
    
```

**Output:**

<img width="1228" height="530" alt="image" src="https://github.com/user-attachments/assets/36c1f18e-8ed0-479c-b1ca-03e31a383739" />


**Question 3**
<img width="1260" height="394" alt="image" src="https://github.com/user-attachments/assets/51635e70-4d29-4d79-af3b-8a01d9e5e6ee" />


```
UPDATE products
SET product_name = 'Premium Bread'
WHERE product_id = 5;
```

**Output:**

<img width="1235" height="482" alt="image" src="https://github.com/user-attachments/assets/47708dbb-ee5d-46ed-9cc4-272970584a1a" />


**Question 4**
<img width="1219" height="580" alt="image" src="https://github.com/user-attachments/assets/0362374a-6f40-4be2-85a0-35b72e84eade" />


```
UPDATE PRODUCTS
SET sell_price = CAST(sell_price * 1.10 AS INTEGER)
WHERE supplier_id = 6;
```

**Output:**

<img width="1214" height="554" alt="image" src="https://github.com/user-attachments/assets/0f4037a3-6258-4caa-986d-9c7870d88777" />


**Question 5**
<img width="1329" height="572" alt="image" src="https://github.com/user-attachments/assets/f773dda2-2884-4fe7-b1b3-35fae72de5b9" />


```
UPDATE PRODUCTS
SET reorder_lvl = 40
WHERE category = 'Grocery';
```

**Output:**
<img width="1221" height="469" alt="image" src="https://github.com/user-attachments/assets/25f3502c-b447-49cb-9491-be2e50cc5787" />


**Question 6**

<img width="1436" height="768" alt="image" src="https://github.com/user-attachments/assets/7e83bf9c-86b3-4135-8198-6bed7c3af113" />


```
DELETE FROM customer
WHERE cust_city LIKE 'r%';
```

**Output:**

<img width="1199" height="832" alt="image" src="https://github.com/user-attachments/assets/eb59a076-124f-4c0f-ba77-2b7a30c34c6a" />


**Question 7**

<img width="1431" height="734" alt="image" src="https://github.com/user-attachments/assets/00face9d-d48f-45db-83a9-ada66d175e7f" />


```
DELETE FROM customer
WHERE GRADE = 2;

```

**Output:**

<img width="1161" height="652" alt="image" src="https://github.com/user-attachments/assets/5bde7042-3514-44cb-9602-178894ed2101" />


**Question 8**

<img width="1169" height="573" alt="image" src="https://github.com/user-attachments/assets/e15106da-01ae-4261-a9af-1da7f5e84988" />


```
DELETE FROM Doctors
WHERE last_name IS NULL;
```

**Output:**

<img width="1216" height="727" alt="image" src="https://github.com/user-attachments/assets/edd067cb-807d-46ae-bf0e-59eadacdd08e" />


**Question 9**

<img width="1405" height="566" alt="image" src="https://github.com/user-attachments/assets/6774d0fa-f2d7-4da2-8db2-519a26334e72" />


```
DELETE FROM customer
WHERE CUST_NAME LIKE '%Holmes%';

```

**Output:**
<img width="1217" height="631" alt="image" src="https://github.com/user-attachments/assets/f94b890a-e241-43cf-b8ce-53359eec3ea9" />


**Question 10**

<img width="1396" height="537" alt="image" src="https://github.com/user-attachments/assets/70a24861-416d-4e34-8f7a-3bf4c2285798" />


```
DELETE FROM Customer
WHERE GRADE = 3
   AND CUST_NAME LIKE '%BBB%'
   AND PAYMENT_ANT > 2000;
SELECT changes();
```

**Output:**

<img width="1239" height="732" alt="image" src="https://github.com/user-attachments/assets/086c03aa-efa1-4888-b203-0cd715d52288" />


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
