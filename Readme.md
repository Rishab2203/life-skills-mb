# SQL Overview

This document provides an overview of Structured Query Language (SQL), covering its basic operations, various types of joins, and aggregation functions, accompanied by practical code examples.

## Introduction

Structured Query Language (SQL) is a standard language used to communicate with relational databases. It enables users to create, manipulate, and retrieve data efficiently. Understanding SQL is fundamental for database management and data analysis.

## SQL Basics

### Creating a Table

To define a new table and its columns, use the `CREATE TABLE` statement:

```sql
CREATE TABLE Employees (
    EmployeeID INT PRIMARY KEY,
    FirstName VARCHAR(50),
    LastName VARCHAR(50),
    DepartmentID INT
);
```


### Inserting a Data

```sql
INSERT INTO Employees (EmployeeID, FirstName, LastName, DepartmentID)
VALUES (1, 'John', 'Doe', 101);
```

### Selecting Data
```sql
SELECT * FROM Employees;
```

### Updating Data
```sql
UPDATE Employees
SET DepartmentID = 102
WHERE EmployeeID = 1;
```
### Deleting Data

```sql
DELETE FROM Employees
WHERE EmployeeID = 1;
```

## SQL Joins

Joins are used to combine rows from two or more tables based on related columns. Common types of joins include:

### INNER JOIN
Returns records with matching values in both tables.

```sql
SELECT Employees.FirstName, Departments.DepartmentName
FROM Employees
INNER JOIN Departments ON Employees.DepartmentID = Departments.DepartmentID;
```

### LEFT JOIN
Returns all records from the left table and matched records from the right table.

```sql
SELECT Employees.FirstName, Departments.DepartmentName
FROM Employees
LEFT JOIN Departments ON Employees.DepartmentID = Departments.DepartmentID;
```

### RIGHT JOIN
Returns all records from the right table and matched records from the left table.

```sql
SELECT Employees.FirstName, Departments.DepartmentName
FROM Employees
RIGHT JOIN Departments ON Employees.DepartmentID = Departments.DepartmentID;
```

### FULL JOIN
Returns all records when there is a match in either left or right table.

```sql
SELECT Employees.FirstName, Departments.DepartmentName
FROM Employees
FULL JOIN Departments ON Employees.DepartmentID = Departments.DepartmentID;
```

## SQL Aggregations

Aggregation functions perform calculations on multiple rows to return a single value. Common aggregate functions include:

### COUNT()

Counts the number of rows.

```sql
SELECT COUNT(*) AS TotalEmployees
FROM Employees;
```

### SUM()

Calculates the total sum of a numeric column.

```sql
SELECT SUM(Salary) AS TotalSalaries
FROM Employees;
```
### AVG()

Calculates the average value of a numeric column.

```sql
SELECT AVG(Salary) AS AverageSalary
FROM Employees;
```
### MIN() and MAX()

Find the minimum and maximum values.

```sql
SELECT MIN(Salary) AS LowestSalary, MAX(Salary) AS HighestSalary
FROM Employees;
```
## Conclusion

Understanding SQL basics, joins, and aggregations is essential for effective database management and getting the desired/relevant data. By mastering these concepts, one can perform complex queries to extract meaningful insights from your data.

