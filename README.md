# 🧠 SQL Project – Database Concepts, Querying & Practical Analysis
This repository contains my SQL work from Week 3 of the Data Technician programme.
## 🚀 Project Overview

The project demonstrates how SQL can be used to manage, query, and analyze business data efficiently. Using real relational databases such as **Northwind Traders** and **World DB**, the work involved writing and executing SQL queries to explore customer demographics, product performance, and global trends.

---

## 🛠️ Core Skills Demonstrated
### ✔️ Understanding Database Fundamentals
- Primary keys & foreign keys
- One‑to‑one, one‑to‑many, many‑to‑many relationships
- Relational vs non‑relational databases
- Identifying structured vs unstructured data

### ✔️ SQL Schema Design
- Designing entity relationships (ERD)
- Creating structured tables to store:
  - Customers
  - Suppliers
  - Inventory / products
  - Sales & transactions
  - Loyalty programme data
- Identifying fact tables vs dimension tables
- Snowflake schema design

### ✔️ SQL Querying
Includes a wide range of practical SQL operations, such as:

- Filtering records (WHERE, LIKE, BETWEEN)
- Sorting (ORDER BY)
- Aggregations (COUNT, AVG, MAX, MIN)
- Grouping (GROUP BY, HAVING)
- JOIN types:
  - INNER JOIN
  - LEFT JOIN
  - RIGHT JOIN
  - FULL JOIN
  - CROSS JOIN
  - SELF JOIN

### ✔️ Practical Real‑World Scenarios
Using the World_db dataset, I completed analysis tasks such as:
- Finding total cities in the USA
- Identifying the country with highest life expectancy
- Listing cities with names containing "New"
- Displaying the top 10 most populous cities
- Filtering cities by population thresholds
- Sorting cities alphabetically
- Finding the most/least populated city
- Country‑level population summaries
- Capital city lookup (e.g., capital of Spain)
- Identifying countries with low population density
- Finding countries with high GDP per capita

## 📁 Repository Contents
- SQL scripts for all workbook tasks
- Table creation scripts
- Query outputs (screenshots or .sql files)
- Example JOIN queries
- Practical demographic and geographic SQL analysis

## 🧠 Key Learning Outcomes
Through this SQL project, I developed strong competencies in:

- Building and designing relational databases
- Writing clean, effective SQL queries
- Joining tables to combine meaningful datasets
- Performing population, geography, and demographic analysis
- Thinking analytically about how to structure and query data
- Applying SQL to real‑world business scenarios
- Understanding how to support business operations through data
I also created a full retail database plan, including:
- Data requirements gathering
- Schema design with clear relationships
- SQL CREATE TABLE and INSERT statements
- Approaches for maintaining, securing, and backing up databases

## 🛠 Tools Used
- MySQL / MariaDB (or equivalent SQL engine)
- world_db dataset
- ERD tools (where applicable)
- SQL client or command line


## 📸 Northwind DB
- Retrieve Full Customer Data Your manager has asked you to export the full list of all customer details into a report. 
  ➡️ Write a SQL query to retrieve all columns from the Customers table.
   ```sql
   SELECT * 
   FROM Customers;
  
- International Customers Targeting (USA & UK) The marketing team is preparing campaigns for customers in the USA and UK.
  ➡️ Write a SQL query to retrieve all columns from the Customers table where the Country is either 'USA' or 'UK'.
   ```sql
   SELECT * 
   FROM Customers 
   WHERE Country = ‘USA’ OR Country = 'UK';

- 📘 Complete Order Overview The business team wants to see a detailed order list with customer and employee information.
  ➡️ Write a SQL query to retrieve the Order ID, Order Date, Customer Name, and Employee Name for all orders.
  ```sql
  SELECT o.orderID, o.orderDate, c.CompanyName AS CustomerName, 
  FROM orders o  
  INNER JOIN Customers c 
  ON o.customerID = c.CustomerID 
  INNER JOIN Employees e 
  ON o.EmployeeID = e.EmployeeID;
  
## 📸 World DB
- Cities with Population Larger than 2,000,000: Scenario: A real estate developer is interested in cities with substantial population sizes for potential      investment opportunities. You're tasked with identifying cities from the database with populations exceeding 2 million to focus their research efforts.
  ```sql
  SELECT  Name, Population
  FROM City
  WHERE Population>2000000
  ORDER BY Population DESC;

- Display Columns with Limit (Rows 31-40): Scenario: A market research firm requires detailed information on cities beyond the top rankings for a comprehensive analysis. You're tasked with providing data on cities ranked between 31st and 40th by population to ensure a thorough understanding of urban demographics.
  ```sql
   SELECT Name, Population
   FROM City
   ORDER BY Population DESC
   LIMIT 30,10;

- Cities in Europe: Scenario: A European cultural exchange program is seeking to connect students with cities across the continent. You're tasked with compiling a list of cities located in Europe from the database to facilitate program planning and student engagement.
  ```sql
  SELECT City.Name, Country.Name
  FROM City
  JOIN Country
  ON City.CountryCode = Country.Code
  WHERE Country.Contitent = 'Europe';
