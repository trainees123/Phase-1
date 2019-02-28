# SQL

**SQL** is a structured query language used for Storing,Manipulating, and Retrieving data in Database

**SQL SELECT**:

SELECT statement is used to select data from database

**Example**:

Lets say we have **Customers Table**

|Customer_id|CustomerName|City|Postalcode|Country|
|----|-----|----|----|----|
|1|Abhishek|Delhi|505213|India|
|2|Rakesh|Noida|505217|India|
|3|Nandan|Ambala|505210|India|
|4|kalyan|New York|003695|United States|

The following SQL query selects the "CustomerName" and "City" columns from the "Customers" table

SELECT CustomerName, City from Customers

And output of that query would be 

|CustomerName| City| 
|------|-----|
|Abhishek|Delhi|
|Rakesh|Noida|
|Nandan|Ambala|
|kalyan|New York| 

To select all columns we have to write 

SELECT * FROM Customers 

**SQL WHERE**:

The WHERE clause is used to extract only those records that fulfill a specified condition.

The following SQL statement selects all the Customers from the country "United States", in the "Customers" table:

SELECT * FROM Customers

WHERE Country=”United States” 

We get the following Output 

|Cutomer_id|Customername|City|Postalcode|Country|
|----|-----|----|----|----|
|4|kalyan|New York|003695|United States|

 **SQL JOIN**:
 
A JOIN clause is used to combine rows from two or more tables, based on a related column between them.

There are Different types of joins 

+ **INNER JOIN**: The INNER JOIN keyword selects records that have matching values in both tables

Lets create **Orders table**

|Order_id|Customer_id|Order_date|Shipper_id|
|---------|-----|-------|-----|
|1003|4|1996-09-18|6|
|2003|3|1996-03-21|3|
|3006|2|1996-08-19|4|
|4006|6|1996-03-16|7|

And we have **Customers table**

|Customer_id|Customername|City|Postalcode|Country|
|----|-----|----|----|----|
|1|Abhishek|Delhi|505213|India|
|2|Rakesh|Noida|505217|India|
|3|Nandan|Ambala|505210|India|
|4|kalyan|New York|003695|United States|

The following SQL Query selects all orders with Customer information:  

SELECT Orders.OrderID, Customers.CustomerName
FROM Orders 
INNER JOIN Customers ON 
Orders.CustomerID = Customers.CustomerID;

The output would be 

|Orders_id|CustomerName|
|--------------|---------|
|1003|Kalyan|
|2003|Nandan|
|3006|Rakesh|


+ **LEFT JOIN**: The LEFT JOIN keyword returns all records from the left table (table1), and the matched records from the right table (table2). The result is NULL from the right side, if there is no match.

**Example**:

We use Customers and Orders table 

The following SQL Query will select all customers, and any orders they might have

SELECT Customers.CustomerName, Orders.OrderID
FROM Customers 
LEFT JOIN Orders ON Customers.CustomerID = Orders.CustomerID 

We would get the following Output 

|CustomerName|Orders_id|
|----|-----|
|Abhishek|NULL|
|Rakesh| 3006|
|Nandan|2003 |
|kalyan| 1003|

+ **RIGHT JOIN**: The RIGHT JOIN keyword returns all records from the right table (table2), and the matched records from the left table (table1). The result is NULL from the left side, when there is no match.

Example:

SELECT Customers.CustomerName, Orders.OrderID
FROM Customers 
RIGHT JOIN Orders ON Customers.CustomerID = Orders.CustomerID 

 We would get the following Output 
 
|CustomerName|Orders_id|
|----|-----|
|Kalyan|1003|
|Nandan|2006|
|Rakesh|3006|
|NULL|4006|

**SQL UNION** : The UNION operator is used to combine the result-set of two or more SELECT statements.

+ Each SELECT statement within UNION must have the same number of columns

+ The columns must also have similar data types

+ The columns in each SELECT statement must also be in the same order 

**SQL INSERT** : The INSERT INTO statement is used to insert new records in a table.

**Example**: We Have Customers table 

|Customer_id|CustomerName|City|Postalcode|Country|
|----|-----|----|----|----|
|1|Abhishek|Delhi|505213|India|
|2|Rakesh|Noida|505217|India|
|3|Nandan|Ambala|505210|India|
|4|kalyan|New York|003695|United States|

To insert New Rows we write the following Query

INSERT INTO Customers(Customer_id,CustomerName,City,Postalcode,Country)
Values(5,Deva,Mumbai,569879,India) 

The output of the Given Query would be 

|Customer_id|CustomerName|City|Postalcode|Country|
|----|-----|----|----|----|
|1|Abhishek|Delhi|505213|India|
|2|Rakesh|Noida|505217|India|
|3|Nandan|Ambala|505210|India|
|4|kalyan|New York|003695|United States|
|5|Deva|Mumbai|569879|India| 

**SQL UPDATE**: The UPDATE statement is used to modify the existing records in a table 

Example:

|Customer_id|CustomerName|City|Postalcode|Country|
|----|-----|----|----|----|
|1|Abhishek|Delhi|505213|India|
|2|Rakesh|Noida|505217|India|
|3|Nandan|Ambala|505210|India|
|4|kalyan|New York|003695|United States|

The following SQL statement updates the first customer (CustomerID = 1) with a new contact person and a new city.

UPDATE Customers
SET Contactname=”Ravi” ,City=”Rome”
WHERE Customer_id=1 

The following would be the output of Customers table

|Customer_id|CustomerName|City|Postalcode|Country|
|----|-----|----|----|----|
|1|Ravi|Rome|505213|India|
|2|Rakesh|Noida|505217|India|
|3|Nandan|Ambala|505210|India|
|4|kalyan|New York|003695|United States|


