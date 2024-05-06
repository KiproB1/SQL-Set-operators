# SQL-Set-operators
CREATE DATABASE MyCompany;

USE MyCompany;

CREATE TABLE EmployeesA (
  EmployeeID INT PRIMARY KEY,
  FirstName VARCHAR(255) NOT NULL,
  LastName VARCHAR(255) NOT NULL,
  Salary DECIMAL(10,2) NOT NULL
);

CREATE TABLE EmployeesB (
  EmployeeID INT PRIMARY KEY,
  FirstName VARCHAR(255) NOT NULL,
  LastName VARCHAR(255) NOT NULL,
  Salary DECIMAL(10,2) NOT NULL
);
INSERT INTO EmployeesA (EmployeeID, FirstName, LastName, Salary)
VALUES (1, 'John', 'Doe', 75000.00),
       (2, 'Jane', 'Smith', 62000.00),
       (3, 'Alice', 'Johnson', 90000.00),
       (4, 'David', 'Williams', 58000.00);

INSERT INTO EmployeesB (EmployeeID, FirstName, LastName, Salary)
VALUES (2, 'Jane', 'Smith', 62000.00),
       (3, 'Alice', 'Johnson', 90000.00),
       (5, 'Mark', 'Jones', 80000.00),
       (6, 'Emily', 'Brown', 45000.00);
SELECT EmployeeID, FirstName, LastName, Salary
FROM EmployeesA
UNION
SELECT EmployeeID, FirstName, LastName, Salary
FROM EmployeesB;
SELECT EmployeeID, FirstName, LastName, Salary
FROM EmployeesA
INTERSECT
SELECT EmployeeID, FirstName, LastName, Salary
FROM EmployeesB;
SELECT EmployeeID, FirstName, LastName, Salary
FROM EmployeesA
EXCEPT
SELECT EmployeeID, FirstName, LastName, Salary
FROM EmployeesB;
