# SQL
## Join
* (INNER) JOIN: Returns records that have matching values in both tables
* LEFT (OUTER) JOIN: Returns all records from the left table, and the matched records from the right table
* RIGHT (OUTER) JOIN: Returns all records from the right table, and the matched records from the left table
* FULL (OUTER) JOIN: Returns all records when there is a match in either left or right table
## Union
The UNION operator is used to combine the result-set of two or more SELECT statements.
## Group By
The GROUP BY statement groups rows that have the same values into summary rows, like "find the number of customers in each country".  
The GROUP BY statement is often used with aggregate functions (COUNT(), MAX(), MIN(), SUM(), AVG()) to group the result-set by one or more columns.
## Having
The HAVING clause was added to SQL because the WHERE keyword cannot be used with aggregate functions.
## Wildcard
A wildcard character is used to substitute one or more characters in a string. 
Wildcard characters are used with the LIKE operator. The LIKE operator is used in a WHERE clause to search for a specified pattern in a column. 
## Constraints
SQL constraints are used to specify rules for the data in a table. 
	* NOT NULL - Ensures that a column cannot have a NULL value
	* UNIQUE - Ensures that all values in a column are different
	* PRIMARY KEY - A combination of a NOT NULL and UNIQUE. Uniquely identifies each row in a table
	* FOREIGN KEY - Prevents actions that would destroy links between tables
	* CHECK - Ensures that the values in a column satisfies a specific condition
	* DEFAULT - Sets a default value for a column if no value is specified
## Views
In SQL, a view is a virtual table based on the result-set of an SQL statement. 
A view contains rows and columns, just like a real table. The fields in a view are fields from one or more real tables in the database. 
You can add SQL statements and functions to a view and present the data as if the data were coming from one single table. 
A view is created with the CREATE VIEW statement.
## Normalization
Normalization is a way by which we can organize this data and also reduce the redundant data. 
It is the processes of reducing the redundancy of data in the table and also improving the data integrity.
	* 1st Normal Form (1NF): a single cell cannot hold multiple values. For example, if we have a person table and there is a person that have 2 phone numbers. We should create two rows with same columns’ data and 2 different phone numbers.
	* 2nd Normal Form: Single Column Primary Key that does not functionally dependent on any subset of candidate key relation
	* 3rd Normal Form: Has no transitive functional dependencies
## Transaction
Transaction is a way to provide data integrity for your application.
Transaction has 4 features which are called ACID
	* A: Atomicity
	* C: Consistency
	* I: Isolation
	* D: Durability
There may have 3 problems in transaction
	* Dirty read  
	> User1         begin select * 10rows                    select *  15rows  
	> time line ——————————————————————————————————  
	> User2         begin              insert(5 rows)                             delete  commit  
	* Unrepeatable read  
	> User1         begin select * 10rows            !=             select *    
	> time line ——————————————————————————————————  
	> User2         begin                  update/ delete  commit  
	* Phantom read  
	> User1         begin select * 10rows            !=             select *    
	> time line ——————————————————————————————————  
	> User2         begin                      insert  commit      
	>       
	> problems (va 10 milk, tx 0 milk)  
	> User1         begin select milk 10 VA                                    select * 0   
	> time line ——————————————————————————————————  
	> User2         begin         delete 10 milk, insert 10 milk into TX commit  
There are 4 different levels of isolation to avoid those problem:
	* READ_UNCOMMITED   
	✅unrepeatable read, Phantom read, dirty read  
	* READ_COMMITED  
	✅unrepeatable read, Phantom read  
	❎dirty read  
	* REPEATABLE  
	✅Phantom read  
	❎unrepeatable read, dirty read  
	* SERIALIZABLE  
	❎all  

