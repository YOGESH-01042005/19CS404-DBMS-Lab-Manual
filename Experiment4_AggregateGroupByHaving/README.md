# Experiment 4: Aggregate Functions, Group By and Having Clause
REG NO:212224230009
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
![Screenshot 2025-05-04 110534](https://github.com/user-attachments/assets/170836bc-5715-4562-9e94-9d25b5575efc)


```sql
SELECT Specialty,COUNT(*) AS TotalDoctors
FROM Doctors
GROUP BY Specialty;
```

**Output:**

![Screenshot 2025-05-04 111037](https://github.com/user-attachments/assets/49009031-131a-4743-814a-537068086047)


**Question 2**
---
![Screenshot 2025-05-04 110544](https://github.com/user-attachments/assets/9467feee-c867-449d-bf66-78a59dd73304)


```sql
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

![Screenshot 2025-05-04 111046](https://github.com/user-attachments/assets/8311d063-f70c-4a5a-9af0-9f68c69bc5d4)


**Question 3**
---
![Screenshot 2025-05-04 110553](https://github.com/user-attachments/assets/f3ec9f2d-3e25-4da7-a51b-cfa3c0a37efa)


```sql
SELECT
    DoctorID,COUNT(*) AS TotalAppointments
FROM
    Appointments
GROUP BY
    DoctorID;
```

**Output:**

![Screenshot 2025-05-04 111051](https://github.com/user-attachments/assets/d7598a8c-a113-40d2-9292-eb147f19b76c)


**Question 4**
---
![Screenshot 2025-05-04 110600](https://github.com/user-attachments/assets/f4e93b2d-5850-4e50-8ace-22810b599e72)


```sql
SELECT
    DoctorID,COUNT(*) AS TotalAppointments
FROM
    Appointments
GROUP BY
    DoctorID;
```

**Output:**

![Screenshot 2025-05-04 111058](https://github.com/user-attachments/assets/c3b4c4d3-d4d6-413f-af46-6568d83e24fe)


**Question 5**
---
![Screenshot 2025-05-04 110610](https://github.com/user-attachments/assets/30c3e1e0-26cc-4647-87ae-2c065155abc5)


```sql
SELECT SUM(inventory) AS total
FROM fruits
WHERE unit = 'LB';
```

**Output:**

![Screenshot 2025-05-04 111103](https://github.com/user-attachments/assets/59d35f43-2b15-4cd1-81d1-3905dee4ece9)


**Question 6**
---
![Screenshot 2025-05-04 110617](https://github.com/user-attachments/assets/4309969a-e6de-4b77-bf9a-e36f2da9ec33)


```sql
SELECT name, LENGTH(name) AS length
FROM customer
ORDER BY LENGTH(name) DESC
LIMIT 1;
```

**Output:**

![Screenshot 2025-05-04 111108](https://github.com/user-attachments/assets/621e04dd-2694-431b-afd0-cbccd2bbf6df)


**Question 7**
---
![Screenshot 2025-05-04 110624](https://github.com/user-attachments/assets/db1f461b-d8f9-41a7-bece-6c3513cbfc7f)


```sql
SELECT AVG(income) AS Average_Salary
FROM employee;
```

**Output:**

![Screenshot 2025-05-04 111116](https://github.com/user-attachments/assets/4894fc57-3bfc-4e0e-a051-9546f85f729c)


**Question 8**
---
![Screenshot 2025-05-04 110632](https://github.com/user-attachments/assets/5567881c-b839-4e51-8711-8f308c8ed57f)


```sql
SELECT occupation, MIN(workhour)
FROM employee1
GROUP BY occupation
HAVING MIN(workhour) > 8;
```

**Output:**

![Screenshot 2025-05-04 111123](https://github.com/user-attachments/assets/ca30f407-42bd-455e-aa94-bf61dc41d0a7)


**Question 9**
---
![Screenshot 2025-05-04 110640](https://github.com/user-attachments/assets/0a58acc8-6c42-4b6b-b7cf-6002b796729f)


```sql
SELECT address,AVG(salary) 
FROM customer1
GROUP BY address
HAVING AVG(salary) < 15000;
```

**Output:**

![Screenshot 2025-05-04 111130](https://github.com/user-attachments/assets/dd1d5398-6d47-4fb8-be8c-0e02bd2e73f8)


**Question 10**
---
![Screenshot 2025-05-04 110731](https://github.com/user-attachments/assets/b4ed5738-55d8-426b-9716-d846253a47ea)


```sql
SELECT jdate, SUM(workhour)
FROM employee1
GROUP BY jdate
HAVING SUM(workhour) > 40;
```

**Output:**

![Screenshot 2025-05-04 111137](https://github.com/user-attachments/assets/e995ae36-2db8-493e-8eb2-b40ee88b0629)


![Screenshot 2025-05-04 111218](https://github.com/user-attachments/assets/5f875443-d853-4e22-bfa4-7d12bc3118b2)

## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
