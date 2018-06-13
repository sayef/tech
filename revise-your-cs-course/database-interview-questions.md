# Database Interview Questions        

**1.  What is database or database management systems (DBMS)? and – What’s  the  difference between file and database? Can files qualify as a  database?**

**Answer :**  Database provides a systematic and organized way of storing, managing  and retrieving from 1 collection of logically related information.
  Secondly the information has to be  persistent, that means even after the application is closed the  information should be persisted.

Finally it  should provide an independent way of accessing data and should not be  dependent on the application to access the information.

Main  difference between a simple file and database that database has  independent way (SQL) of accessing information while simple files do not  File meets the storing, managing and retrieving part of a database but  not the independent way of accessing data. Many experienced programmers  think that the main difference is that file can not provide multi-user  capabilities which a DBMS provides. But if we look at some old COBOL and  C programs where file where the only means of storing data, we can see  functionalities like locking, multi-user etc provided very efficiently.  So it’s a matter of debate if some interviewers think this as a main  difference between files and database accept it… going in to debate is  probably loosing a job.

**2.** **What is SQL ?**

**Answer :**  SQL stands for Structured Query Language.SQL is an ANSI (American  National Standards Institute) standard computer language for accessing  and manipulating database systems. SQL statements are used to retrieve  and update data in a database.

**3.** **What’s difference between DBMS and RDBMS ?**

**Answer :**  DBMS provides a systematic and organized way of storing, managing and  retrieving from  collection of logically related information. RDBMS also  provides what DBMS provides but above that it provides relationship  integrity. So in short we can say

RDBMS = DBMS + REFERENTIAL INTEGRITY

These  relations are defined by using “Foreign Keys” in any RDBMS.Many DBMS  companies claimed there DBMS product was a RDBMS compliant, but  according to industry rules and regulations if the DBMS fulfills the  twelve CODD rules it’s truly a RDBMS. Almost all DBMS (SQL SERVER,  ORACLE etc) fulfills all the twelve CODD rules and are considered as  truly RDBMS.

**5. What are E-R diagrams?**

**Answer:**  E-R diagram also termed as Entity-Relationship diagram shows relationship between various tables in the database. .

**6.  How many types of relationship exist in database designing?**

**Answer:** There are three major relationship models:-
  One-to-one
  One-to-many
  Many-to-many

**7. What are DML and DDL statements?**

**Answer :** DML stands for Data Manipulation Statements. They update data values in table. Below are the most important DDL statements:-

=>SELECT – gets data from a database table

=> UPDATE – updates data in a table

=> DELETE – deletes data from a database table

=> INSERT INTO – inserts new data into a database table

DDL stands  for Data definition Language. They change structure of the database  objects like table, index etc. Most important DDL statements are as  shown below:-
  =>CREATE TABLE – creates a new table in the database.

=>ALTER TABLE – changes table structure in database. =>DROP TABLE – deletes a table from database

=> CREATE INDEX – creates an index => DROP INDEX – deletes an index

**8. How do we select distinct values from a table?**

**Answer :** DISTINCT keyword is used to return only distinct values. Below is syntax:- Column age and Table pcdsEmp

SELECT DISTINCT age FROM pcdsEmp

**9.  What is Like operator for and what are wild cards?**

**Answer :**  LIKE operator is used to match patterns. A “%” sign is used to define  the pattern. Below SQL statement will return all words with letter “S”

SELECT * FROM pcdsEmployee WHERE EmpName LIKE ‘S%’

Below SQL statement will return all words which end with letter “S” SELECT * FROM pcdsEmployee WHERE EmpName LIKE ‘%S’

Below SQL statement will return all words having letter “S” in between SELECT * FROM pcdsEmployee WHERE EmpName LIKE ‘%S%’

“_”  operator (we can read as “Underscore Operator”). “_” operator is the  character defined at that point. In the below sample fired a query  Select name from pcdsEmployee where name like ‘_s%’ So all name where  second letter is “s” is returned.

**10.**  **Can you explain Insert, Update and Delete query?**

**Answers :**  Insert statement is used to insert new rows in to table. Update to  update existing data in the table. Delete statement to delete a record  from the table. Below code snippet for Insert, Update and Delete :-

INSERT INTO pcdsEmployee SET name=’rohit’,age=’24’;

UPDATE pcdsEmployee SET age=’25’ where name=’rohit’;

DELETE FROM pcdsEmployee WHERE name = ‘sonia’;

**11. What is order by clause?**

**Answer** : ORDER BY clause helps to sort the data in either ascending order to descending order.

Ascending order sort query

SELECT name,age FROM pcdsEmployee ORDER BY age ASC

Descending order sort query

SELECT name FROM pcdsEmployee ORDER BY age DESC

**12. What is the SQL ” IN ” clause?**

**Answer :**  SQL IN operator is used to see if the value exists in a group of  values. For instance the below SQL checks if the Name is either ‘rohit’  or ‘Anuradha’

SELECT * FROM pcdsEmployee WHERE name IN (‘Rohit’,’Anuradha’)

Also you can specify a not clause with the same.

SELECT * FROM pcdsEmployee WHERE age NOT IN (17,16)

**13. Can you explain the between clause?**

**Answer :** Below SQL selects employees born between ’01/01/1975′ AND ’01/01/1978′ as per mysql

SELECT * FROM pcdsEmployee WHERE DOB BETWEEN ‘1975-01-01’ AND ‘2011-09-28’

**14.  we have an employee salary table how do we find the second highest from it?**

**Answer :** below Sql Query find the second highest salary

SELECT *  FROM pcdsEmployeeSalary a WHERE (2=(SELECT COUNT(DISTINCT(b.salary))  FROM pcdsEmployeeSalary b WHERE b.salary>=a.salary))

**15**. **What are different types of joins in SQL?**

**Answer :** INNER JOIN:  Inner join shows matches only when they exist in both tables. Example in  the below SQL there are two tables Customers and Orders and the inner  join in made on Customers.Customerid and Orders.Customerid. So this SQL  will only give you result with customers who have orders. If the  customer does not have order it will not display that record.

SELECT Customers.*, Orders.* FROM Customers INNER JOIN Orders ON Customers.CustomerID =Orders.CustomerID

LEFT OUTER  JOIN: Left join will display all records in left table of the SQL  statement. In SQL below customers with or without orders will be  displayed. Order data for customers without orders appears as NULL  values. For example, you want to determine the amount ordered by each  customer and you need to see who has not ordered anything as well. You  can also see the LEFT OUTER JOIN as a mirror image of the RIGHT OUTER  JOIN (Is covered in the next section) if you switch the side of each  table.

SELECT Customers.*, Orders.* FROM Customers LEFT OUTER JOIN Orders ON Customers.CustomerID =Orders.CustomerID

RIGHT  OUTER JOIN: Right join will display all records in right table of the  SQL statement. In SQL below all orders with or without matching customer  records will be displayed. Customer data for orders without customers  appears as NULL values. For example, you want to determine if there are  any orders in the data with undefined CustomerID values (say, after a  conversion or something like it). You can also see the RIGHT OUTER JOIN  as a mirror image of the LEFT OUTER JOIN if you switch
  the side of each table.

SELECT Customers.*, Orders.* FROM Customers RIGHT OUTER JOIN Orders ON Customers.CustomerID =Orders.CustomerID

**16.**  **What is “CROSS JOIN”? or What is Cartesian product?**

**Answer :**  “CROSS JOIN” or “CARTESIAN PRODUCT” combines all rows from both tables.  Number of rows will be product of the number of rows in each table. In  real life scenario I can not imagine where we will want to use a  Cartesian product. But there are scenarios where we would like  permutation and combination probably Cartesian would be the easiest way  to achieve it.

**17. How to select the first record in a given set of rows?**

**Answer :** Select top 1 * from sales.salesperson

**18. What is the default “-SORT ” order for a SQL?**

**Answer  :** ASCENDING

**19.** **What is a self-join?**

**Answer :** If we want to join two instances of the same table we can use self-join.

**20.** **What’s the difference between DELETE and TRUNCATE ?**

**Answer :** Following are difference between them:

=>>DELETE  TABLE syntax logs the deletes thus making the delete operations low.  TRUNCATE table does not log any information but it logs information  about deallocation of data page of the table. So TRUNCATE table is  faster as compared to delete table.

=>>DELETE table can have criteria while TRUNCATE can not.

=>> TRUNCATE table can not have triggers.

**21. What’s the difference between “UNION” and “UNION ALL” ?**

**Answer :**   UNION SQL syntax is used to select information from two tables. But it  selects only distinct records from both the table. , while UNION ALL  selects all records from both the tables.

**22. What is ” Group by ” clause?**

**Answer :** “Group by” clause group similar data so that aggregate values can be derived.

**23. What is the difference between “HAVING” and “WHERE” clause?**

**Answer:** “HAVING” clause is used to specify filtering criteria for “GROUP BY”, while “WHERE” clause applies on normal SQL.

**24. What is a Sub-Query?**

**Answer :**  A query nested inside a SELECT statement is known as a subquery and is  an alternative to complex join statements. A subquery combines data from  multiple tables and returns results that are inserted into the WHERE  condition of the main query. A subquery is always enclosed within  parentheses and returns a column. A subquery can also be referred to as  an inner query and the main query as an outer query. JOIN gives better  performance than a subquery when you have to check for the existence of  records.

For  example, to retrieve all EmployeeID and CustomerID records from the  ORDERS table that have the EmployeeID greater than the average of the  EmployeeID field, you can create a nested query, as shown:

SELECT DISTINCT EmployeeID, CustomerID FROM ORDERS WHERE EmployeeID > (SELECT AVG(EmployeeID) FROM ORDERS)

**25. What are Aggregate and Scalar Functions?**

**Answer :**  Aggregate and Scalar functions are in built function for counting and  calculations.  Aggregate functions operate against a group of values but  returns only one value.

AVG(column) :- Returns the average value of a column
  COUNT(column) :- Returns the number of rows (without a NULL value) of a column

COUNT(*) :- Returns the number of selected rows
  MAX(column) :- Returns the highest value of a column

MIN(column) :- Returns the lowest value of a column

Scalar functions operate against a single value and return value on basis of the single value.

UCASE(c) :- Converts a field to upper case

LCASE(c) :- Converts a field to lower case
  MID(c,start[,end]) :- Extract characters from a text field
  LEN(c) :- Returns the length of a text

**26. Can you explain the SELECT INTO Statement?** 

**Answer :**  SELECT INTO statement is used mostly to create backups. The below SQL  backsup the  Employee table in to the EmployeeBackUp table. One point to  be noted is that the structure of pcdsEmployeeBackup and pcdsEmployee  table should be same.

SELECT * INTO pcdsEmployeeBackup FROM pcdsEmployee

**27.**  **What is a View?**

**Answer :** View is a virtual table which is created on the basis of the result set returned by the select statement.
  CREATE VIEW [MyView] AS SELECT * from pcdsEmployee where LastName = ‘singh’

In order to query the view SELECT * FROM [MyView]

**28.  What is SQL injection ?**

**Answer :**  It is a Form of attack on a database-driven Web site in which the  attacker executes unauthorized SQL commands by taking advantage of  insecure code on a system connected to the Internet, bypassing the  firewall. SQL injection attacks are used to steal information from a  database from which the data would normally not be available and/or to  gain access to an organization’s host computers through the computer  that is hosting the database.

SQL injection attacks typically are easy to avoid by ensuring that a system has strong input validation.
  As name suggest we inject SQL which can be relatively dangerous for the database. Example this is a simple SQL
  SELECT email, passwd, login_id, full_name FROM members WHERE email = ‘x’

Now somebody does not put “x” as the input but puts “x ; DROP TABLE members;”. So the actual SQL which will execute is :-
  SELECT email, passwd, login_id, full_name FROM members WHERE email = ‘x’ ; DROP TABLE members;
  Think what will happen to your database.

**29.** **What is Data Warehousing ?**

**Answer :**  Data Warehousing is a process in which the data is stored and accessed  from central location and is meant to support some strategic decisions.  Data Warehousing is not a requirement for Data mining. But just makes  your Data mining process more efficient.

Data  warehouse is a collection of integrated, subject-oriented databases  designed to support the decision-support functions (DSF), where each  unit of data is relevant to some moment in time.

**30. What are Data Marts?**

**Answer :**  Data Marts are smaller section of Data Warehouses. They help data  warehouses collect data. For example your company has lot of branches  which are spanned across the globe. Head-office of the company decides  to collect data from all these branches for anticipating market. So to  achieve this IT department can setup data mart in all branch offices and  a central data warehouse where all data will finally reside.

**31. What is Data mining ?**

**Answer :**  Data mining is a concept by which we can analyze the current data from  different perspectives and summarize the information in more useful  manner. It’s mostly used either to derive some valuable  information  from the existing data or to predict sales to increase customer market.  There are two basic aims of Data mining:-

**32. What are indexes? What are B Trees?**

**Answer :**  Index makes your search faster. So defining indexes to your database  will make your search faster.Most of the indexing fundamentals use  “B-Tree” or “Balanced-Tree” principle. It’s not a principle that is  something is created by SQL Server or ORACLE but is a mathematical  derived fundamental.In order that “B-tree” fundamental work properly  both of the sides should be balanced.

**33.  What are the two types of indexes and explain them in detail? or What’s  the difference between clustered and non-clustered indexes?**

**Answer :** There are basically two types of indexes:- Clustered Indexes. Non-Clustered Indexes.

In  clustered index the non-leaf level actually points to the actual data.In  Non-Clustered index the leaf nodes point to pointers which then point  to actual data.