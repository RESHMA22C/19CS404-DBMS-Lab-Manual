# ER Diagram Workshop – Submission Template

## Objective
To understand and apply ER modeling concepts by creating ER diagrams for real-world applications.

## Purpose
Gain hands-on experience in designing ER diagrams that represent database structure including entities, relationships, attributes, and constraints.

---

# Scenario A: City Fitness Club Management

**Business Context:**  
FlexiFit Gym wants a database to manage its members, trainers, and fitness programs.

**Requirements:**  
- Members register with name, membership type, and start date.  
- Each member can join multiple programs (Yoga, Zumba, Weight Training).  
- Trainers assigned to programs; a program may have multiple trainers.  
- Members may book personal training sessions with trainers.  
- Attendance recorded for each session.  
- Payments tracked for memberships and sessions.

### ER Diagram:
<img width="992" height="640" alt="image" src="https://github.com/user-attachments/assets/dc5cf7ef-fd4e-43de-b89b-55bdfba72e51" />


### Entities and Attributes

<img width="1170" height="687" alt="image" src="https://github.com/user-attachments/assets/0434d20c-78a5-47c1-a506-956fc9ce4b86" />


### Relationships and Constraints

<img width="913" height="549" alt="image" src="https://github.com/user-attachments/assets/fd9d9ee8-1ae2-4b22-bf85-12472c0e3bb6" />


### Assumptions
A member must enroll in at least one program.

A program must be led by at least one trainer.

Payments are tied to members and programs (not to trainers directly).

# Scenario B: City Library Event & Book Lending System

**Business Context:**  
The Central Library wants to manage book lending and cultural events.

**Requirements:**  
- Members borrow books, with loan and return dates tracked.  
- Each book has title, author, and category.  
- Library organizes events; members can register.  
- Each event has one or more speakers/authors.  
- Rooms are booked for events and study.  
- Overdue fines apply for late returns.

### ER Diagram:
<img width="803" height="642" alt="image" src="https://github.com/user-attachments/assets/a91e3d66-9f05-43d8-aa1b-5d14a5e1396c" />


### Entities and Attributes

<img width="924" height="411" alt="image" src="https://github.com/user-attachments/assets/cb75168b-3865-4365-bab2-359dd7aabd3d" />

### Relationships and Constraints
<img width="1136" height="513" alt="image" src="https://github.com/user-attachments/assets/0ffce8fa-cebf-42c1-b159-be4dd576f1a9" />

### Assumptions
A member must exist before borrowing books or registering for events.

A book may or may not be borrowed; not all books will always have loans.

Fines are only generated if a book is returned late.

# Scenario C: Restaurant Table Reservation & Ordering

**Business Context:**  
A popular restaurant wants to manage reservations, orders, and billing.

**Requirements:**  
- Customers can reserve tables or walk in.  
- Each reservation includes date, time, and number of guests.  
- Customers place food orders linked to reservations.  
- Each order contains multiple dishes; dishes belong to categories (starter, main, dessert).  
- Bills generated per reservation, including food and service charges.  
- Waiters assigned to serve reservations.

### ER Diagram:
<img width="763" height="786" alt="image" src="https://github.com/user-attachments/assets/813904fc-19dd-46c8-9ade-bb8b334505f2" />


### Entities and Attributes

<img width="909" height="332" alt="image" src="https://github.com/user-attachments/assets/22804286-bebd-424b-bf0d-2d64529a72ec" />

<img width="918" height="125" alt="image" src="https://github.com/user-attachments/assets/d682b192-bd15-480a-859b-ff1d48bad3a5" />

### Relationships and Constraints

<img width="1133" height="651" alt="image" src="https://github.com/user-attachments/assets/420bbb97-0faa-4f72-b2fd-7aa8c91ff735" />


### Assumptions
A customer may exist without making a reservation or placing an order.

A reservation must be tied to both a customer and a restaurant.

Every order must belong to a customer and a restaurant.

## Instructions for Students

1. Complete **all three scenarios** (A, B, C).  
2. Identify entities, relationships, and attributes for each.  
3. Draw ER diagrams using **draw.io / diagrams.net** or hand-drawn & scanned.  
4. Fill in all tables and assumptions for each scenario.  
5. Export the completed Markdown (with diagrams) as **a single PDF**
