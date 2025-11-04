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

<img width="1035" height="707" alt="image" src="https://github.com/user-attachments/assets/7d804811-fb3e-439c-ad8a-20c1ba9a9116" />


```
SELECT
    DATE(AppointmentDateTime) AS AppointmentDate,
    COUNT(*) AS TotalAppointments
FROM
   Appointments
GROUP BY
   DATE(AppointmentDateTime)
ORDER BY
   AppointmentDate;


```

**Output:**


<img width="812" height="719" alt="image" src="https://github.com/user-attachments/assets/f6e45a43-fd2a-4a5c-8d50-c24f007e1a59" />


**Question 2**


<img width="1151" height="693" alt="image" src="https://github.com/user-attachments/assets/59a786cf-87ee-4cd7-bd0a-ea489e7df8a4" />


```
SELECT 
    InsuranceCompany,
    ROUND(AVG(JULIANDAY(EndDate)- JULIANDAY(StartDate)), 1) AS AvgCoverageDurationDays
FROM 
   Insurance
WHERE
   StartDate IS NOT NULL AND EndDate IS NOT NULL
GROUP BY
   InsuranceCompany;

```

**Output:**
<img width="1115" height="796" alt="image" src="https://github.com/user-attachments/assets/03117a01-ec6f-473e-b9b4-927e7fbae5de" />


**Question 3**

<img width="1187" height="574" alt="image" src="https://github.com/user-attachments/assets/112244b4-16ab-4c1f-9571-af0e79c07ca2" />


```
SELECT
    Specialty,
    Gender,
    COUNT(*) AS TotalDoctors
FROM
   Doctors
GROUP BY
   Specialty , Gender
ORDER BY
    Specialty, Gender;


```

**Output:**


<img width="1084" height="714" alt="image" src="https://github.com/user-attachments/assets/a19dbf8d-76d3-4f9e-a82f-7fa8a0f420f0" />


**Question 4**

<img width="1196" height="555" alt="image" src="https://github.com/user-attachments/assets/490a02df-64f2-41f5-91b2-80f7bfd8e9f6" />


```
SELECT name AS fruit_name, inventory AS lowest_quantity
FROM fruits
ORDER BY inventory ASC
LIMIT 1;
```

**Output:**

<img width="744" height="392" alt="image" src="https://github.com/user-attachments/assets/3f0a5cf8-7b5a-4d83-a907-0c245017ab45" />


**Question 5**

<img width="1260" height="525" alt="image" src="https://github.com/user-attachments/assets/29653206-c4d5-42eb-b3de-a9a7b4c9e99d" />


```
SELECT COUNT(*) AS COUNT
FROM customer
WHERE city = 'Noida';
```

**Output:**

<img width="466" height="392" alt="image" src="https://github.com/user-attachments/assets/bd5642f6-efa6-47cc-93c3-ea002e94def8" />


**Question 6**

<img width="1305" height="508" alt="image" src="https://github.com/user-attachments/assets/ec4480df-4653-4e1b-9087-1c8598c6756c" />


```
SELECT MAX(age) - MIN(age) AS age_difference FROM employee;
```

**Output:**

<img width="584" height="384" alt="image" src="https://github.com/user-attachments/assets/493e218c-e7a9-41d0-92c2-7db362c2a15b" />


**Question 7**

<img width="1171" height="502" alt="image" src="https://github.com/user-attachments/assets/4e456675-771d-4de8-aa3f-39e2f4ec3cf4" />



```
SELECT AVG(LENGTH(name)) AS avg_name_length FROM customer WHERE city = 'Chennai';
```

**Output:**

<img width="590" height="387" alt="image" src="https://github.com/user-attachments/assets/7da9a103-575c-46af-a8f5-ae0aa5ae3440" />


**Question 8**

<img width="1429" height="551" alt="image" src="https://github.com/user-attachments/assets/e5ad7ab3-7da9-47db-822f-a11ffbbdbaf1" />


```
SELECT age,MIN(income) FROM employee
GROUP BY age
HAVING MIN(income) < 400000;
```

**Output:**

<img width="775" height="478" alt="image" src="https://github.com/user-attachments/assets/00f75b45-bed0-412e-95c6-389ffb9b74ac" />


**Question 9**

<img width="1446" height="514" alt="image" src="https://github.com/user-attachments/assets/0f2e1696-43c3-43c5-91c0-d9d65fbc5e54" />


```
SELECT age, AVG(income)
FROM employee
GROUP BY age
HAVING AVG(income) BETWEEN 300000 AND 500000;

```

**Output:**

<img width="668" height="404" alt="image" src="https://github.com/user-attachments/assets/9acfee52-2b8a-4e6f-9570-5387ab2d5cca" />

**Question 10**

<img width="1409" height="551" alt="image" src="https://github.com/user-attachments/assets/59b2a315-cb56-46ad-9db8-7f8580835dcd" />


```
SELECT category_id, count(product_name)
FROM products
GROUP BY category_id
HAVING category_id < 3;
```

**Output:**

<img width="980" height="442" alt="image" src="https://github.com/user-attachments/assets/397bcecd-af5d-41b3-9542-5feb5f2c7fc2" />



## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
