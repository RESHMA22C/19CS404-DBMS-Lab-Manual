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

<img width="1432" height="524" alt="image" src="https://github.com/user-attachments/assets/99a6ae4d-fe8f-4c5d-9cdd-7932c47d65bb" />


```
SELECT grade, COUNT(*) AS count
FROM customer
WHERE city = 'New York'
  AND grade > (
    SELECT AVG(grade)
    FROM customer
    WHERE city = 'New York'
)
GROUP BY grade;

```

**Output:**

<img width="726" height="403" alt="image" src="https://github.com/user-attachments/assets/065a6624-d82f-4bee-8b71-1c3439379a41" />


**Question 2**

<img width="1361" height="479" alt="image" src="https://github.com/user-attachments/assets/966121c8-1473-46ae-ad13-79cb2dcf4093" />


```
SELECT department_id, department_name
FROM Departments
WHERE LENGTH(department_name) > (
    SELECT AVG(LENGTH(department_name))
    FROM Departments
);

```

**Output:**

<img width="834" height="463" alt="image" src="https://github.com/user-attachments/assets/023cdc55-17d1-4139-9c86-08763ba81325" />


**Question 3**

<img width="1485" height="674" alt="image" src="https://github.com/user-attachments/assets/c3d795e3-79bc-4ff8-bbf4-7db68f153491" />



```
SELECT student_name, grade
FROM GRADES g
WHERE grade = (
    SELECT MAX(grade)
    FROM GRADES
    WHERE subject = g.subject
);

```

**Output:**

<img width="868" height="516" alt="image" src="https://github.com/user-attachments/assets/c640e026-97b8-4ed8-930a-523bbacd9726" />



**Question 4**

<img width="1438" height="577" alt="image" src="https://github.com/user-attachments/assets/06e42e56-dc2e-43f8-b2fe-596ca5b04156" />


```
SELECT ord_no, purch_amt, ord_date, customer_id, salesman_id
FROM orders
WHERE salesman_id IN (
    SELECT salesman_id
    FROM orders
    WHERE customer_id = 3007
);

```

**Output:**

<img width="1328" height="484" alt="image" src="https://github.com/user-attachments/assets/44a7a5c8-f69f-4b1d-9fa2-1da1cb46b86a" />


**Question 5**

<img width="1229" height="718" alt="image" src="https://github.com/user-attachments/assets/527e9cbd-8388-4805-add4-feed05078fc0" />

```
SELECT *
FROM customer
WHERE customer_id = (
    SELECT salesman_id - 2001
    FROM salesman
    WHERE name = 'Mc Lyon'
);

```

**Output:**

<img width="1272" height="385" alt="image" src="https://github.com/user-attachments/assets/a3b42eff-8290-4b2d-a9dd-da2d423ea933" />


**Question 6**

<img width="1372" height="687" alt="image" src="https://github.com/user-attachments/assets/3a54052d-2591-4d4c-8e91-36cf98418d32" />


```
SELECT *
FROM Employee
WHERE age < (
    SELECT AVG(age)
    FROM Employee
    WHERE income > 250000
);

```

**Output:**

<img width="1295" height="596" alt="image" src="https://github.com/user-attachments/assets/42308c65-1f69-47a7-afcb-230437920915" />


**Question 7**

<img width="1269" height="665" alt="image" src="https://github.com/user-attachments/assets/2afcb5cb-148a-4abb-b3ff-df0d7c477cc6" />

```
SELECT *
FROM CUSTOMERS
WHERE ADDRESS = 'Delhi';

```

**Output:**

<img width="1282" height="429" alt="image" src="https://github.com/user-attachments/assets/63731d3a-67ba-4f30-b59b-cbbdc4fba74d" />


**Question 8**

<img width="1469" height="685" alt="image" src="https://github.com/user-attachments/assets/1d360b33-0b99-4994-ba0d-b197c8c508de" />


```
SELECT *
FROM GRADES g
WHERE grade = (
    SELECT MIN(grade)
    FROM GRADES
    WHERE subject = g.subject
);

```

**Output:**

<img width="1322" height="406" alt="image" src="https://github.com/user-attachments/assets/71224559-2423-41af-983d-25643b35979b" />


**Question 9**


<img width="1416" height="649" alt="image" src="https://github.com/user-attachments/assets/a7dbb53f-f75f-4e97-a64d-f1431f4e1380" />



```
SELECT *
FROM Employee
WHERE age < (
    SELECT AVG(age)
    FROM Employee
    WHERE income > 1000000
);

```

**Output:**

<img width="1288" height="405" alt="image" src="https://github.com/user-attachments/assets/2aa5203c-9156-4cf4-bad8-5a6ad6c528e4" />


**Question 10**

<img width="1349" height="553" alt="image" src="https://github.com/user-attachments/assets/13e96c12-a38f-4ac0-85a8-aeb2498dfd2e" />


```
SELECT name, city
FROM customer
WHERE city IN (
    SELECT city
    FROM customer
    WHERE id IN (3, 7)
);

```

**Output:**

<img width="683" height="535" alt="image" src="https://github.com/user-attachments/assets/b8824bf7-12ca-4f52-99d9-10c5fd8f680f" />



## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
