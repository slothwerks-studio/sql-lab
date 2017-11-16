# SQL Lab Q&A

1. Select all the records from the "Customers" table.

SELECT * FROM customers;

2. Get distinct countries from the Customers table.

SELECT * FROM customers
   WHERE country='Mexico';

SELECT * FROM customers
   WHERE country='France';

3. Get all the records from the table Customers where the Customer’s ID starts with “BL”.

SELECT * FROM customers WHERE customerid LIKE '%BL%';

4. Get the first 100 records of the orders table.

SELECT * FROM orders LIMIT 100;

5. Get all customers that live in the postal codes 1010, 3012, 12209, and 05023.

SELECT * FROM customers WHERE postalcode='1010' OR postalcode='3012' OR postalcode='12209' OR postalcode='05023';

6. Get all orders where the ShipRegion is not equal to NULL.

SELECT * FROM orders WHERE shipregion <> 'null';

7. Get all customers ordered by the country, then by the city.

SELECT * FROM customers ORDER BY country, city;

8. Add a new customer to the customers table. You can use whatever values/

INSERT INTO customers (customerid, companyname, contactname, contacttitle, address, city, region, postalcode, country, phone) values ('SLOTH', 'SlothWerks', 'Sloth I', 'Owner/Operator', '1814 Orville SE', 'Grand Rapids', 'Michigan', '49506', 'USA', '616.258.6179');

9. Update all ShipRegion to the value ‘EuroZone’ in the Orders table, where the
ShipCountry is equal to France.

UPDATE orders SET shipregion='EuroZone' WHERE shipcountry='France';

10. Delete all orders from `order_details` that have quantity of 1.

DELETE FROM order_details WHERE quantity='1';

11. Calculate the average, max, and min of the quantity at the `order details` table.

SELECT AVG(quantity) FROM order_details; (23.9943872778297474)
SELECT MIN(quantity) FROM order_details;
(2)
SELECT MAX(quantity) FROM order_details;
(130)

12. Calculate the average, max, and min of the quantity at the `order details` table,
grouped by the orderid.

SELECT orderid, MIN(quantity), MAX(quantity), AVG(quantity) FROM order_details GROUP BY orderid;

13. Find the CustomerID that placed order 10290 (orders table)

SELECT customerid FROM orders WHERE orderid='10290';

BONUS:

14. Do an inner join, left join, right join on orders and customers tables.

SELECT * FROM orders
INNER JOIN customers ON orders.customerid = customers.customerid;

SELECT * FROM orders
LEFT JOIN customers ON orders.customerid = customers.customerid;

SELECT * FROM orders
RIGHT JOIN customers ON orders.customerid = customers.customerid;

15. Get employees’ firstname for all employees who report to no one.

SELECT firstname FROM employees WHERE reportsto IS NULL;

16. Get employees’ firstname for all employees who report to Andrew.

SELECT employeeid FROM employees WHERE firstname = 'Andrew';
(2)
SELECT firstname FROM employees WHERE reportsto = '2';



