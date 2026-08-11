select *
from customers;

Select * 
from customers;

select customername, city, country
from customers;

select country
from customers;

SELECT ProductID, ProductName FROM Products;

-- Which countries are there customers?

select country
from customers;

select distinct country
from CusTOmers;

select distinct city
from customers;

select count(country)
from customers;
-- count number of rows in country column

-- How many different country are there in customers table?
select count(distinct country)
from customers;

SELECT COUNT(DISTINCT CustomerID) 
FROM Customers;
-- How many customers?

Select firstname, lastname, birthdate 
from Employees;

select customername, address, city 
from customers;

select distinct city from suppliers;

SELECT COUNT(DISTINCT city) 
FROM Customers;

select * 
from customers
WHERE Country = 'Mexico';

SELECT * FROM Products
WHERE ProductID =1;

SELECT * FROM Customers                
Where City = 'London';

SELECT * FROM Customers                
Where City = 'London';

SELECT * FROM Products
WHERE Price > 100;

SELECT productid, productname, price FROM Products
WHERE Price > 100;

SELECT * FROM Orders
WHERE OrderDate > '1996-07-30';

Select customername, country
from customers 
where country <> 'UK';

Select customername, country
from customers 
where country != 'UK';

select * 
from customers 
where city = 'London'

select count(customerid) 
from customers 
where country = 'USA'; 

select * from customers 
where customerID >= 15;

SELECT * FROM Customers
WHERE Country = 'Germany' AND City = 'Berlin';

SELECT * FROM Suppliers
WHERE Country = 'Japan' AND City = 'Tokyo';

SELECT * FROM Customers
WHERE City = 'Berlin' OR City = 'Stuttgart';

SELECT customername, city, country FROM Customers
WHERE Country = 'Germany' OR Country = 'Spain';

Select customername, city FROM customers 
WHERE city = 'Portland' OR city= 'Kirkland'; 

SELECT * FROM orders 
WHERE orderdate < '1996-08-27' OR orderdate > '1997-02-21';

select customername, city, country from Customers 
where Country= 'UK' and City ='London';

-- city starts with a
select customername, city 
from customers
where city LIKE 'A%'; 

-- city starts with a
select customername, city 
from customers
where city LIKE '%a'; 

-- name of the product contains Choco
select * 
from products
where productname like '%choco%';

select *
from products
where lower(productname) like '%choco%';

select customername
from customers
where customername like '_r%';

SELECT contactname FROM Customers
WHERE ContactName LIKE 'A%o';

SELECT suppliername, country FROM Suppliers 
WHERE Country LIKE '%land%';

SELECT * FROM Employees 
WHERE FirstName LIKE '_n%';

SELECT *
FROM Suppliers
WHERE Country LIKE '%land';

-- German, French or British
select *
from customers
where country = 'Germany' or country = 'France' or country = 'UK';

select *
from customers
where country in ('Germany', 'UK', 'France');

SELECT customername, country FROM Customers
WHERE Country NOT IN ('Germany', 'France', 'UK');

SELECT Customername, Country FROM Customers
WHERE Country IN (SELECT Country FROM Suppliers);
-- When select statement is used inside another select statement, its called subquery.
-- Country names from suppliers table are used to filter customers table. 
-- customers that are from the same countries as the suppliers.

SELECT Country FROM Suppliers


select * from Customers 
where City IN ('Berlin', 'Paris', 'Madrid');

select * from orders 
where shipperid IN (1, 3);

-- take customerid from orders and filter the customers
Select * From customers 
Where CustomerID In (Select CustomerID From Orders);

-- take customerid from customers and filter the orders
Select * From orders 
Where CustomerID In (Select CustomerID From customers);

-- customers never placed order
Select * From customers 
Where CustomerID not In (Select CustomerID From Orders);

SELECT customerID
FROM customers
WHERE customerID IN (SELECT customerID FROM orders);

SELECT * FROM Products
WHERE Price BETWEEN 10 AND 20;

SELECT * FROM Products
WHERE Price NOT BETWEEN 10 AND 20;

SELECT * FROM Products
WHERE Price BETWEEN 10 AND 20
AND CategoryID NOT IN (1,2,3);

SELECT * FROM Products
WHERE ProductName BETWEEN 'Carnarvon Tigers' AND 'Mozzarella di Giovanni'
ORDER BY ProductName;

SELECT Customername, country FROM Customers 
ORDER BY Country;


SELECT Customername, country FROM Customers 
ORDER BY Country desc;

SELECT ProductName, Price FROM Products
ORDER BY Price DESC;

SELECT ProductName, Price FROM Products
ORDER BY Price;

SELECT Customername, country FROM Customers
ORDER BY Country, CustomerName;

SELECT customername, country FROM Customers
ORDER BY Country ASC, CustomerName DESC;
 

SELECT * FROM Customers
LIMIT 3;

SELECT * FROM Products
ORDER BY PRICE 
LIMIT 5;

SELECT * FROM Customers
WHERE Country='Germany'
LIMIT 3;

SELECT * FROM Products
WHERE CategoryID=1
LIMIT 3;

SELECT MIN(Price) AS SmallestPrice
FROM Products;

SELECT MAX(Price) AS LargestPrice
FROM Products;

select avg(price)
from products;

select sum(quantity)
from order_details;

-- how many customer from UK ?
select count(customerid)
from customers
where country = 'UK';

-- how many customer from UK ?
select count(customerid), country
from customers
where country = 'UK';

select count(customerid) as UK_Customers
from customers
where country = 'UK';


SELECT MAX(Price) AS LargestPrice
FROM Products;


select count(customerid) as "UK Customers"
from customers
where country = 'UK';
