# Excercise 1 - user privileges

## Inserting users

	CREATE USER 'Inventory'@'localhost' IDENTIFIED BY 'inv123';
	CREATE USER 'Bookkeeping'@'localhost' IDENTIFIED BY 'book123';
	CREATE USER 'hr'@'localhost' IDENTIFIED BY 'hr123';
	CREATE USER 'Sales'@'localhost' IDENTIFIED BY 'sales123';
	CREATE USER 'IT'@'localhost' IDENTIFIED BY 'it123';

## Granting privileges

	GRANT SELECT, UPDATE, INSERT  ON classicmodels.products TO 'Inventory'@'localhost';
	GRANT SELECT, UPDATE, INSERT  ON classicmodels.productlines TO 'Inventory'@'localhost';

	GRANT SELECT ON classicmodels.orders TO 'Bookkeeping'@'localhost';
	GRANT SELECT ON classicmodels.orderdetails TO 'Bookkeeping'@'localhost';

	GRANT SELECT, UPDATE, INSERT ON classicmodels.employees TO 'hr'@'localhost';
	GRANT SELECT, UPDATE, INSERT ON classicmodels.employees TO 'hr'@'localhost';

	GRANT SELECT, UPDATE, INSERT ON classicmodels.orders TO 'Sales'@'localhost';
	GRANT SELECT, UPDATE, INSERT ON classicmodels.orderdetails TO 'Sales'@'localhost';

	GRANT ALL ON classicmodels.* TO 'IT'@'localhost';
	
	FLUSH PRIVILEGES;


### Why theses privileges?
* Inventory - needs to manage products and product lines
* Bookkeeping - just needs to be able to view oders & details
* HR - they are managing employees and offices
* Sales - in theory only needs to create orders but they should also be able to correct their mistakes in orders wihtout having to contact IT
* IT - needs all access because they are IT

# Exercise 2 - logging





