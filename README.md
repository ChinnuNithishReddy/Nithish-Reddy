create table city (
  2  cid int not null,
  3  cityname varchar(20),
  4  primary key (cid));

Table created.


SQL>  insert into city (cid,cityname)
  2   values
  3    (1,'hyderabad');

1 row created.

SQL>  insert into city (cid,cityname)
  2   values
  3    (2,'mumbai');

1 row created.

SQL>  insert into city (cid,cityname)
  2   values
  3    (3,'delhi');

1 row created.

SQL>  insert into city (cid,cityname)
  2   values
  3    (4,'kolkata');

1 row created.

SQL>  insert into city (cid,cityname)
  2   values
  3    (5,'bangalore');

1 row created. 

SQL>  insert into city (cid,cityname)
  2   values
  3    (6,'chennai');

1 row created.

SQL> select * from city;

       CID		 CITYNAME
    ---------- 	--------------------
         1		 hyderabad
         2 		mumbai
         3 		delhi
         4 		kolkata
         5 		bangalore
         6 		chennai

6 rows selected.

SQL> create table customer (id int not null,
  2  fristname varchar (20),
  3  lastname varchar (20),
  4  city int not null,
  5  primary key (id),
  6  foreign key (city) references city (cid));

Table created.
SQL> insert into customer (id, fristname, lastname, city)
  2  values
  3  (101,'chinnu','reddy',1);
  
  1 row created.
  
  SQL> insert into customer (id, fristname, lastname, city) 
  2 values 
  3 (102,'hari','reddy',2);
  
1 row created.

SQL> insert into customer (id, fristname, lastname, city)
  2  values
  3  (103,'ajay','rathore',6);

1 row created.

SQL> insert into customer (id, fristname, lastname, city)
  2  values
  3    (104,'Rohit','Sinha',6);

1 row created.

SQL> insert into customer (id, fristname, lastname, city)
  2  values
  3    (105,'Akash','Verma',1);

1 row created.

SQL> insert into customer (id, fristname, lastname, city)
  2  values
  3    (106,'Abhishek','Gupta',3);

1 row created.

SQL> insert into customer (id, fristname, lastname, city)
  2  values
  3    (107,'Rishav','Pal',5);

1 row created.

SQL> insert into customer (id, fristname, lastname, city)
  2  values
  3    (108,'Sakshi','Sinha',2);

1 row created.

SQL> insert into customer (id, fristname, lastname, city)
  2  values
  3    (109,'john','doe',4);

1 row created.

SQL> select * from customer;

        ID              FRISTNAME              LASTNAME                   CITY
   ----------      --------------------        --------------------             ------------
       101	 chinnu              	 reddy                         1
       102	 hari                 		reddy                          2
       103	 ajay                 		rathore                       6
       104	 Rohit                		Sinha                          6
       105 	Akash                	Verma                         1
       106 	Abhishek          		   Gupta                       3
       107 	Rishav               		Pal                                5
       108 	Sakshi               		Sinha                           2
       109 	john                 		doe                             4

9 rows selected.

SQL>


SQL> UPDATE City
  2  SET CityName = 'New Kolkata'
  3  WHERE CID = 4;

1 row updated.

SQL> UPDATE City
  2  SET CityName = 'Chennai Central'
  3  WHERE CityName = 'chennai';

1 row updated 

SQL> select * from city;

       CID CITYNAME
---------- --------------------
         1 hyderabad
         2 mumbai
         3 delhi
         4 New Kolkata
         5 bangalore
         6 Chennai Central

6 rows selected.
SQL> UPDATE Customer
  2  SET City = 4
  3  WHERE ID = 104;

1 row updated.
SQL> select * from customer;

        ID FRISTNAME            LASTNAME                   CITY
---------- -------------------- -------------------- ----------
       101 chinnu               reddy                         1
       102 hari                 reddy                         2
       103 ajay                 rathore                       6
       104 Rohit                Sinha                         4
       105 Akash                Verma                         1
       106 Abhishek             Gupta                         3
       107 Rishav               Pal                           5
       108 Sakshi               Sinha                         2
       109 john                 doe                           4

9 rows selected.

SQL>

SQL> SELECT * FROM Customer
  2  WHERE City = 1;

        ID FRISTNAME            LASTNAME                   CITY
---------- -------------------- -------------------- ----------
       105 Akash                Verma                         1
       101 chinnu               reddy                         1
       SQL> select * from customer where city = 2;

        ID FRISTNAME            LASTNAME                   CITY
---------- -------------------- -------------------- ----------
       108 Sakshi               Sinha                         2
       102 hari                 reddy                         2

SQL> select * from customer where city = 5;

        ID FRISTNAME            LASTNAME                   CITY
---------- -------------------- -------------------- ----------
       107 Rishav               Pal                           5

SQL> select * from customer where city = 6;

        ID FRISTNAME            LASTNAME                   CITY
---------- -------------------- -------------------- ----------
       104 Rohit                Sinha                         6
       103 ajay                 rathore                       6

SQL> select * from customer where city = 1;

        ID FRISTNAME            LASTNAME                   CITY
---------- -------------------- -------------------- ----------
       105 Akash                Verma                         1
       101 chinnu               reddy                         1

SQL>

SQL> SELECT * FROM Customer
  2  WHERE City = 1 AND LastName = 'reddy';

        ID FRISTNAME            LASTNAME                   CITY
---------- -------------------- -------------------- ----------
       101 chinnu               reddy                         1
       SQL> select * from customer where city = 2 and lastname = 'reddy';

        ID FRISTNAME            LASTNAME                   CITY
---------- -------------------- -------------------- ----------
       102 hari                 reddy                         2
       
SQL> select * from customer where city = 5 and lastname = 'Pal';

        ID FRISTNAME            LASTNAME                   CITY
---------- -------------------- -------------------- ----------
       107 Rishav               Pal                           5


SQL> SELECT * FROM Customer
  2  WHERE City = 1 OR City = 2;

        ID FRISTNAME            LASTNAME                   CITY
---------- -------------------- -------------------- ----------
       105 Akash                Verma                         1
       108 Sakshi               Sinha                         2
       101 chinnu               reddy                         1
       102 hari                 reddy                         2

       
SQL> select * from customer where city =3 or city = 5;

        ID FRISTNAME            LASTNAME                   CITY
---------- -------------------- -------------------- ----------
       106 Abhishek             Gupta                         3
       107 Rishav               Pal                           5

SQL> select * from customer where city =2 or city = 6;
se
        ID FRISTNAME            LASTNAME                   CITY
---------- -------------------- -------------------- ----------
       104 Rohit                Sinha                         6
       108 Sakshi               Sinha                         2
       103 ajay                 rathore                       6
       102 hari                 reddy                         2

SQL> select * from customer where city =1 or city = 4;

        ID FRISTNAME            LASTNAME                   CITY
---------- -------------------- -------------------- ----------
       105 Akash                Verma                         1
       109 john                 doe                           4
       101 chinnu               reddy                         1

SQL> SELECT * FROM Customer
  2  WHERE ID BETWEEN 103 AND 106;

        ID FRISTNAME            LASTNAME                   CITY
---------- -------------------- -------------------- ----------
       104 Rohit                Sinha                         6
       105 Akash                Verma                         1
       106 Abhishek             Gupta                         3
       103 ajay                 rathore                       6

SQL> SELECT * FROM Customer
  2  WHERE ID BETWEEN 101 AND 106;

        ID FRISTNAME            LASTNAME                   CITY
---------- -------------------- -------------------- ----------
       104 Rohit                Sinha                         6
       105 Akash                Verma                         1
       106 Abhishek             Gupta                         3
       101 chinnu               reddy                         1
       103 ajay                 rathore                       6
       102 hari                 reddy                         2

6 rows selected.


SQL> select * from customer;

        ID FRISTNAME            LASTNAME                   CITY
---------- -------------------- -------------------- ----------
       101 chinnu               reddy                         1
       102 hari                 reddy                         2
       103 ajay                 rathore                       6
       104 Rohit                Sinha                         6
       105 Akash                Verma                         1
       106 Abhishek             Gupta                         3
       107 Rishav               Pal                           5
       108 Sakshi               Sinha                         2
       109 john                 doe                           4

9 rows selected.

SQL> select * from city;

       CID CITYNAME
---------- --------------------
         1 hyderabad
         2 mumbai
         3 delhi
         4 New Kolkata
         5 bangalore
         6 chennai central

6 rows selected.

SQL> SELECT c.CITYNAME, COUNT(*) AS num_customers
  2  FROM customer cu
  3  JOIN city c ON cu.CITY = c.CID
  4  GROUP BY c.CITYNAME;

CITYNAME             NUM_CUSTOMERS
-------------------- -------------
chennai central                  2
delhi                            1
New Kolkata                      1
mumbai                           2
hyderabad                        2
bangalore                        1

6 rows selected.

SQL> SELECT c.CITYNAME, SUM(cu.ID) AS total_id_sum
  2  FROM customer cu
  3  JOIN city c ON cu.CITY = c.CID
  4  GROUP BY c.CITYNAME;

CITYNAME             TOTAL_ID_SUM
-------------------- ------------
chennai central               207
delhi                         106
New Kolkata                   109
mumbai                        210
hyderabad                     206
bangalore                     107

6 rows selected.

SQL> SELECT c.CITYNAME, AVG(cu.ID) AS avg_id
  2  FROM customer cu
  3  JOIN city c ON cu.CITY = c.CID
  4  GROUP BY c.CITYNAME;

CITYNAME                 AVG_ID
-------------------- ----------
chennai central           103.5
delhi                       106
New Kolkata                 109
mumbai                      105
hyderabad                   103
bangalore                   107

6 rows selected.

SQL> SELECT c.CITYNAME,
  2         COUNT(*) AS num_customers,
  3         SUM(cu.ID) AS total_id_sum,
  4         AVG(cu.ID) AS avg_id
  5  FROM customer cu
  6  JOIN city c ON cu.CITY = c.CID
  7  GROUP BY c.CITYNAME;

CITYNAME             NUM_CUSTOMERS TOTAL_ID_SUM     AVG_ID
-------------------- ------------- ------------ ----------
chennai central                  2          207      103.5
delhi                            1          106        106
New Kolkata                      1          109        109
mumbai                           2          210        105
hyderabad                        2          206        103
bangalore                        1          107        107

6 rows selected.

SQL> SELECT LASTNAME, COUNT(*) AS num_customers
  2  FROM customer
  3  GROUP BY LASTNAME;

LASTNAME             NUM_CUSTOMERS
-------------------- -------------
Gupta                            1
Pal                              1
doe                              1
rathore                          1
Verma                            1
Sinha                            2
reddy                            2

7 rows selected.

SQL> SELECT cu.ID, cu.FRISTNAME, cu.LASTNAME, c.CITYNAME
  2  FROM customer cu
  3  LEFT OUTER JOIN city c
  4  ON cu.CITY = c.CID;

        ID FRISTNAME            LASTNAME             CITYNAME
---------- -------------------- -------------------- --------------------
       101 chinnu               reddy                hyderabad
       105 Akash                Verma                hyderabad
       102 hari                 reddy                mumbai
       108 Sakshi               Sinha                mumbai
       106 Abhishek             Gupta                delhi
       109 john                 doe                  New Kolkata
       107 Rishav               Pal                  bangalore
       103 ajay                 rathore              chennai central
       104 Rohit                Sinha                chennai central

9 rows selected.

SQL> SELECT cu.ID, cu.FRISTNAME, cu.LASTNAME, c.CITYNAME
  2  FROM customer cu
  3  RIGHT OUTER JOIN city c
  4  ON cu.CITY = c.CID;

        ID FRISTNAME            LASTNAME             CITYNAME
---------- -------------------- -------------------- --------------------
       101 chinnu               reddy                hyderabad
       102 hari                 reddy                mumbai
       103 ajay                 rathore              chennai central
       104 Rohit                Sinha                chennai central
       105 Akash                Verma                hyderabad
       106 Abhishek             Gupta                delhi
       107 Rishav               Pal                  bangalore
       108 Sakshi               Sinha                mumbai
       109 john                 doe                  New Kolkata

9 rows selected.

SQL> SELECT cu.ID, cu.FRISTNAME, cu.LASTNAME, c.CITYNAME
  2  FROM customer cu
  3  FULL OUTER JOIN city c
  4  ON cu.CITY = c.CID;

        ID FRISTNAME            LASTNAME             CITYNAME
---------- -------------------- -------------------- --------------------
       101 chinnu               reddy                hyderabad
       102 hari                 reddy                mumbai
       103 ajay                 rathore              chennai central
       104 Rohit                Sinha                chennai central
       105 Akash                Verma                hyderabad
       106 Abhishek             Gupta                delhi
       107 Rishav               Pal                  bangalore
       108 Sakshi               Sinha                mumbai
       109 john                 doe                  New Kolkata

9 rows selected.

SQL> SELECT cu.ID, cu.FRISTNAME, cu.LASTNAME, c.CITYNAME
  2  FROM customer cu
  3  CROSS JOIN city c;

        ID FRISTNAME            LASTNAME             CITYNAME
---------- -------------------- -------------------- --------------------
       101 chinnu               reddy                hyderabad
       102 hari                 reddy                hyderabad
       103 ajay                 rathore              hyderabad
       104 Rohit                Sinha                hyderabad
       105 Akash                Verma                hyderabad
       106 Abhishek             Gupta                hyderabad
       107 Rishav               Pal                  hyderabad
       108 Sakshi               Sinha                hyderabad
       109 john                 doe                  hyderabad
       101 chinnu               reddy                mumbai
       102 hari                 reddy                mumbai

        ID FRISTNAME            LASTNAME             CITYNAME
---------- -------------------- -------------------- --------------------
       103 ajay                 rathore              mumbai
       104 Rohit                Sinha                mumbai
       105 Akash                Verma                mumbai
       106 Abhishek             Gupta                mumbai
       107 Rishav               Pal                  mumbai
       108 Sakshi               Sinha                mumbai
       109 john                 doe                  mumbai
       101 chinnu               reddy                delhi
       102 hari                 reddy                delhi
       103 ajay                 rathore              delhi
       104 Rohit                Sinha                delhi

        ID FRISTNAME            LASTNAME             CITYNAME
---------- -------------------- -------------------- --------------------
       105 Akash                Verma                delhi
       106 Abhishek             Gupta                delhi
       107 Rishav               Pal                  delhi
       108 Sakshi               Sinha                delhi
       109 john                 doe                  delhi
       101 chinnu               reddy                New Kolkata
       102 hari                 reddy                New Kolkata
       103 ajay                 rathore              New Kolkata
       104 Rohit                Sinha                New Kolkata
       105 Akash                Verma                New Kolkata
       106 Abhishek             Gupta                New Kolkata

        ID FRISTNAME            LASTNAME             CITYNAME
---------- -------------------- -------------------- --------------------
       107 Rishav               Pal                  New Kolkata
       108 Sakshi               Sinha                New Kolkata
       109 john                 doe                  New Kolkata
       101 chinnu               reddy                bangalore
       102 hari                 reddy                bangalore
       103 ajay                 rathore              bangalore
       104 Rohit                Sinha                bangalore
       105 Akash                Verma                bangalore
       106 Abhishek             Gupta                bangalore
       107 Rishav               Pal                  bangalore
       108 Sakshi               Sinha                bangalore

        ID FRISTNAME            LASTNAME             CITYNAME
---------- -------------------- -------------------- --------------------
       109 john                 doe                  bangalore
       101 chinnu               reddy                chennai central
       102 hari                 reddy                chennai central
       103 ajay                 rathore              chennai central
       104 Rohit                Sinha                chennai central
       105 Akash                Verma                chennai central
       106 Abhishek             Gupta                chennai central
       107 Rishav               Pal                  chennai central
       108 Sakshi               Sinha                chennai central
       109 john                 doe                  chennai central

54 rows selected.

SQL> SELECT A.FRISTNAME AS Customer1, B.FRISTNAME AS Customer2, c.CITYNAME
  2  FROM customer A
  3  JOIN customer B
  4  ON A.CITY = B.CITY
  5  JOIN city c
  6  ON A.CITY = c.CID
  7  WHERE A.ID < B.ID;

CUSTOMER1            CUSTOMER2            CITYNAME
-------------------- -------------------- --------------------
ajay                 Rohit                chennai central
chinnu               Akash                hyderabad
hari                 Sakshi               mumbai
SQL> select * from customer;

        ID FRISTNAME            LASTNAME                   CITY
---------- -------------------- -------------------- ----------
       101 chinnu               reddy                         1
       102 hari                 reddy                         2
       103 ajay                 rathore                       6
       104 Rohit                Sinha                         6
       105 Akash                Verma                         1
       106 Abhishek             Gupta                         3
       107 Rishav               Pal                           5
       108 Sakshi               Sinha                         2
       109 john                 doe                           4

9 rows selected.

SQL> select * from city;

       CID CITYNAME
---------- --------------------
         1 hyderabad
         2 mumbai
         3 delhi
         4 New Kolkata
         5 bangalore
         6 chennai central

6 rows selected.

SQL> SELECT *
  2  FROM customer
  3  WHERE CITY IN (
  4      SELECT CITY
  5      FROM customer
  6      GROUP BY CITY
  7      HAVING COUNT(*) > 1
  8  );

        ID FRISTNAME            LASTNAME                   CITY
---------- -------------------- -------------------- ----------
       101 chinnu               reddy                         1
       102 hari                 reddy                         2
       103 ajay                 rathore                       6
       104 Rohit                Sinha                         6
       105 Akash                Verma                         1
       108 Sakshi               Sinha                         2

6 rows selected.

SQL> SELECT *
  2  FROM customer
  3  WHERE ID > (
  4      SELECT AVG(ID)
  5      FROM customer
  6  );

        ID FRISTNAME            LASTNAME                   CITY
---------- -------------------- -------------------- ----------
       106 Abhishek             Gupta                         3
       107 Rishav               Pal                           5
       108 Sakshi               Sinha                         2
       109 john                 doe                           4

SQL> SELECT *
  2  FROM city
  3  WHERE CID NOT IN (
  4      SELECT DISTINCT CITY
  5      FROM customer
  6  );

no rows selected

SQL> SELECT *
  2  FROM customer
  3  WHERE CITY = (
  4      SELECT CID
  5      FROM city
  6      WHERE CITYNAME = 'mumbai'
  7  );

        ID FRISTNAME            LASTNAME                   CITY
---------- -------------------- -------------------- ----------
       102 hari                 reddy                         2
       108 Sakshi               Sinha                         2




       SQL> CREATE TABLE Customers (
  2       CustomerID INTEGER PRIMARY KEY,
  3       FirstName varchar(20),
  4       LastName varchar(20),
  5       City varchar(20)
  6  );

Table created.

SQL> INSERT INTO Customers VALUES (1, 'John', 'Doe', 'New York');

1 row created.

SQL> INSERT INTO Customers VALUES (2, 'Jane', 'Smith', 'Los Angeles');

1 row created.

SQL> INSERT INTO Customers VALUES (3, 'Mike', 'Brown', 'Chicago');

1 row created.
SQL> INSERT INTO Customers VALUES (4, 'Sara', 'Wilson', 'Houston');

1 row created.

SQL> INSERT INTO Customers VALUES (5, 'David', 'Lee', 'San Francisco');

1 row created.

SQL> INSERT INTO Customers VALUES (6, 'Emily', 'Clark', 'Seattle');

1 row created.

SQL> INSERT INTO Customers VALUES (7, 'Robert', 'Taylor', 'Miami');

1 row created.

SQL> INSERT INTO Customers VALUES (8, 'Sophia', 'Anderson', 'Boston');

1 row created.
SQL> select * from Customers;

CUSTOMERID FIRSTNAME            LASTNAME             CITY
---------- -------------------- -------------------- --------------------
         1 John                 Doe                  New York
         2 Jane                 Smith                Los Angeles
         3 Mike                 Brown                Chicago
         4 Sara                 Wilson               Houston
         5 David                Lee                  San Francisco
         6 Emily                Clark                Seattle
         7 Robert               Taylor               Miami
         8 Sophia               Anderson             Boston

8 rows selected.

CREATE TABLE Orders (
    OrderID INTEGER PRIMARY KEY,
    CustomerID INTEGER,
    OrderDate varchar(20),
    Amount REAL,
    FOREIGN KEY (CustomerID) REFERENCES Customers(CustomerID)
);
Table created.

SQL> INSERT INTO Orders VALUES (101, 1, '2024-01-10', 250.00);

1 row created.

SQL> INSERT INTO Orders VALUES (102, 1, '2024-03-15', 450.00);

1 row created.

SQL> INSERT INTO Orders VALUES (103, 2, '2024-02-20', 300.00);

1 row created.

SQL> INSERT INTO Orders VALUES (104, 2, '2024-03-25', 275.00);

1 row created.

SQL> INSERT INTO Orders VALUES (105, 3, '2024-04-05', 500.00);

1 row created.

SQL> INSERT INTO Orders VALUES (106, 4, '2024-04-18', 150.00);

1 row created.

SQL> INSERT INTO Orders VALUES (107, 5, '2024-05-01', 700.00);

1 row created.

SQL> INSERT INTO Orders VALUES (108, 5, '2024-05-20', 650.00);

1 row created.

SQL> select * from Orders;

   ORDERID CUSTOMERID ORDERDATE                AMOUNT
---------- ---------- -------------------- ----------
       101          1 2024-01-10                  250
       102          1 2024-03-15                  450
       103          2 2024-02-20                  300
       104          2 2024-03-25                  275
       105          3 2024-04-05                  500
       106          4 2024-04-18                  150
       107          5 2024-05-01                  700
       108          5 2024-05-20                  650

8 rows selected.
SQL> CREATE VIEW CustomerFullName AS
  2  SELECT CustomerID, FirstName || ' ' || LastName AS FullName, City
  3  FROM Customers;

View created.

SQL> CREATE VIEW OrderDetails AS
  2  SELECT
  3      Orders.OrderID,
  4      Customers.FirstName || ' ' || Customers.LastName AS CustomerName,
  5      Orders.OrderDate,
  6      Orders.Amount
  7  FROM Orders
  8  JOIN Customers ON Orders.CustomerID = Customers.CustomerID;

View created.

SQL> SELECT * FROM CustomerFullName;

CUSTOMERID FULLNAME                                  CITY
---------- ----------------------------------------- --------------------
         1 John Doe                                  New York
         2 Jane Smith                                Los Angeles
         3 Mike Brown                                Chicago
         4 Sara Wilson                               Houston
         5 David Lee                                 San Francisco
         6 Emily Clark                               Seattle
         7 Robert Taylor                             Miami
         8 Sophia Anderson                           Boston

8 rows selected.

SQL> SELECT * FROM OrderDetails WHERE Amount > 300;

   ORDERID CUSTOMERNAME                              ORDERDATE
---------- ----------------------------------------- --------------------
    AMOUNT
----------
       102 John Doe                                  2024-03-15
       450

       105 Mike Brown                                2024-04-05
       500

       107 David Lee                                 2024-05-01
       700


   ORDERID CUSTOMERNAME                              ORDERDATE
---------- ----------------------------------------- --------------------
    AMOUNT
----------
       108 David Lee                                 2024-05-20
       650

SQL> CREATE VIEW SimpleCustomerView AS
  2  SELECT CustomerID, City
  3  FROM Customers;

View created.

SQL> UPDATE SimpleCustomerView
  2  SET City = 'San Francisco'
  3  WHERE CustomerID = 2;

1 row updated.

SQL> DROP VIEW OrderDetails;

View dropped.


SQL> DROP VIEW CustomerFullName;

View dropped.

ALL PROGRAMS 


SQL> CREATE TABLE customers1 (
    CustomerID INT PRIMARY KEY,
    FirstName VARCHAR(50),
    LastName VARCHAR(50),
    Email VARCHAR(100),
    Phone VARCHAR(20),
    Address VARCHAR(255)
);

Table created.

SQL> INSERT INTO customers1 (CustomerID, FirstName, LastName, Email, Phone, Address) VALUES(1, 'John', 'Doe', 'john@gmail.com', '1234567890', '123 Main St'),

1 row created.

SQL> INSERT INTO customers1 (CustomerID, FirstName, LastName, Email, Phone, Address) VALUES(2, 'Alice', 'Smith', 'alice@gmai.com', '2345678901', '456 Elm St');
1 row created.

SQL> INSERT INTO customers1 (CustomerID, FirstName, LastName, Email, Phone, Address) VALUES (3, 'Michael', 'Johnson', 'michael@gmai.com', '3456789012', '789 Pine St');

1 row created.

SQL> INSERT INTO customers1 (CustomerID, FirstName, LastName, Email, Phone, Address) VALUES (4, 'Emma', 'Brown', 'emma@gmai.com', '4567890123', '321 Oak St');

1 row created.

SQL> INSERT INTO customers1 (CustomerID, FirstName, LastName, Email, Phone, Address) VALUES (5, 'David', 'Lee', 'david@gmai.com', '5678901234', '654 Maple St');

1 row created.

SQL> select * from customers1;

CUSTOMERID       FIRSTNAME          LASTNAME              EMAIL                    PHONE                            ADDRESS
----------     -------------    ---------------   -----------------------     --------------------          --------------------
     1            John               Doe             john@gmail.com            9234567890                      123 Main St

     2            Alice              Smith           alice@gmail.com           9345678901                      456 Elm St

     3            Michael            Johnson         michael@gmail.com         9456789012                      789 Pine St

     4            Emma               Brown           emma@gmail.com            9567890123                      321 Oak St

     5            David              Lee             david@gmail.com           9678901234                      654 Maple St


SQL> CREATE TABLE products1 (
    ProductID INT PRIMARY KEY,
    ProductName VARCHAR(100),
    Category VARCHAR(50),
    Price DECIMAL(10,2),
    StockQuantity INT
);

Table created.

SQL> INSERT INTO products1 (ProductID, ProductName, Category, Price, StockQuantity) VALUES (1, 'Laptop', 'Electronics', 75000, 20);

1 row created.

SQL> INSERT INTO products1 (ProductID, ProductName, Category, Price, StockQuantity) VALUES (2, 'Mouse', 'Electronics', 500, 100);

1 row created.

SQL> INSERT INTO products1 (ProductID, ProductName, Category, Price, StockQuantity) VALUES (3, 'Speaker', 'Electronic', 2500, 300);

1 row created.

SQL> INSERT INTO products1 (ProductID, ProductName, Category, Price, StockQuantity) VALUES (4, 'Desk', 'Furniture', 5500, 30);

1 row created.

SQL> INSERT INTO products1 (ProductID, ProductName, Category, Price, StockQuantity) VALUES (5, 'Monitor', 'Electronics', 15000, 25);

1 row created.

SQL> INSERT INTO products1 (ProductID, ProductName, Category, Price, StockQuantity) VALUES (6, 'Keyboard', 'Electronics', 1500, 70);

1 row created.

SQL> select * from products1;

     PRODUCTID     PRODUCTNAME                     CATEGORY              PRICE         STOCKQUANTITY
    ----------    -------------------     --------------------------- ------------     ----------------
         1         Laptop                      Electronics              75000            20
         2         Mouse                       Electronics              500              100
         3         speaker                     Electronics              2500             300
         4         Desk                        Furniture                5500             30
         5         Monitor                     Electronics              15000            25
         6         Keyboard                    Electronics              1500             70
  
6 rows selected.


SQL> CREATE TABLE orders1 (
    OrderID INT PRIMARY KEYT,
    OrderDate DATE,
    CustomerID INT,
    FOREIGN KEY (CustomerID) REFERENCES customers1(CustomerID)
);

Table created.

SQL> INSERT INTO orders1 (OrderID, OrderDate, CustomerID) VALUES (1, TO_DATE('2025-07-01', 'YYYY-MM-DD'), 1);

1 row created.

SQL> INSERT INTO orders1 (OrderID, OrderDate, CustomerID) VALUES (2, TO_DATE('2025-07-02', 'YYYY-MM-DD'), 2);

1 row created.

SQL> INSERT INTO orders1 (OrderID, OrderDate, CustomerID) VALUES (3, TO_DATE('2025-07-03', 'YYYY-MM-DD'), 3);

1 row created.

SQL>  INTO orders1 (OrderID, OrderDate, CustomerID) VALUES (4, TO_DATE('2025-07-04', 'YYYY-MM-DD'), 4);

1 row created.

SQL> INSERT INTO orders1 (OrderID, OrderDate, CustomerID) VALUES (5, TO_DATE('2025-07-05', 'YYYY-MM-DD'), 5);

1 row created.

SQL> select * from orders1;

   ORDERID       ORDERDATE   CUSTOMERID
----------     -----------  ------------
    1           01-JUL-25        1
    2           02-JUL-25        2
    3           03-JUL-25        3
    4           04-JUL-25        4
    5           05-JUL-25        5


SQL> CREATE TABLE payments (
    PaymentID INT PRIMARY KEY,
    OrderID INT,
    PaymentDate DATE,
    Amount DECIMAL(10,2),
    PaymentMethod VARCHAR(50),
    FOREIGN KEY (OrderID) REFERENCES orders1(OrderID)
);

Table created.

SQL> INSERT INTO payments (PaymentID, OrderID, PaymentDate, Amount, PaymentMethod) VALUES (1, 1, TO_DATE('2025-07-01', 'YYYY-MM-DD'), 76000, 'Credit Card');

1 row created.

SQL> INSERT INTO payments (PaymentID, OrderID, PaymentDate, Amount, PaymentMethod) VALUES (2, 2, TO_DATE('2025-07-02', 'YYYY-MM-DD'), 3500, 'UPI');

1 row created.

SQL> INSERT INTO payments (PaymentID, OrderID, PaymentDate, Amount, PaymentMethod) VALUES (3, 3, TO_DATE('2025-07-03', 'YYYY-MM-DD'), 16500, 'Debit Card');

1 row created.

SQL> INSERT INTO payments (PaymentID, OrderID, PaymentDate, Amount, PaymentMethod) VALUES (4, 4, TO_DATE('2025-07-04', 'YYYY-MM-DD'), 6000, 'UPI');

1 row created.

SQL> INSERT INTO payments (PaymentID, OrderID, PaymentDate, Amount, PaymentMethod) VALUES (5, 5, TO_DATE('2025-07-05', 'YYYY-MM-DD'), 90000, 'Credit Card');

1 row created.

SQL> select * from payments;

 PAYMENTID    ORDERID     PAYMENTDA         AMOUNT       PAYMENTMETHOD
---------- ----------   -------------   ------------- ---------------------
    1          1         01-JUL-25        76000         Credit Card
    2          2         02-JUL-25        3500          UPI
    3          3         03-JUL-25        16500         Debit Card
    4          4         04-JUL-25        6000          UPI
    5          5         05-JUL-25        90000         Credit Card


SQL> CREATE TABLE order_details (
    OrderID INT,
    ProductID INT,
    Quantity INT,
    Subtotal DECIMAL(10,2),
    PRIMARY KEY (OrderID, ProductID),
    FOREIGN KEY (OrderID) REFERENCES orders(OrderID),
    FOREIGN KEY (ProductID) REFERENCES products(ProductID)
);

Table created.

SQL> INSERT INTO order_details (OrderID, ProductID, Quantity, Subtotal) VALUES (1, 1, 1, 75000);

1 row created.

SQL> INSERT INTO order_details (OrderID, ProductID, Quantity, Subtotal) VALUES (1, 2, 2, 1000);

1 row created.

SQL> INSERT INTO order_details (OrderID, ProductID, Quantity, Subtotal) VALUES (2, 5, 1, 15000);

1 row created.

SQL> INSERT INTO order_details (OrderID, ProductID, Quantity, Subtotal) VALUES (3, 6, 1, 1500);

1 row created.

SQL> INSERT INTO order_details (OrderID, ProductID, Quantity, Subtotal) VALUES (4, 4, 1, 5500);

1 row created.

SQL> INSERT INTO order_details (OrderID, ProductID, Quantity, Subtotal) VALUES (4, 2, 1, 500);

1 row created.

SQL> INSERT INTO order_details (OrderID, ProductID, Quantity, Subtotal) VALUES (5, 1, 1, 75000);

1 row created.

SQL> INSERT INTO order_details (OrderID, ProductID, Quantity, Subtotal) VALUES (5, 5, 1, 15000);

1 row created.

SQL> select * from order_details;

   ORDERID  PRODUCTID   QUANTITY   SUBTOTAL
---------- ---------- ---------- ----------
         1          1          1      75000
         1          2          2       1000
         2          5          1      15000
         3          6          1       1500
         4          4          1       5500
         4          2          1        500
         5          1          1      75000
         5          5          1      15000

8 rows selected.

SQL> SELECT 
    o.OrderID,
    c.FirstName,
    c.LastName,
    o.OrderDate,
    SUM(od.Subtotal) AS TotalAmount,
    p.PaymentMethod,
    p.PaymentDate
FROM orders1 o
JOIN customers1 c ON o.CustomerID = c.CustomerID
JOIN order_details od ON o.OrderID = od.OrderID
JOIN payments p ON o.OrderID = p.OrderID
GROUP BY o.OrderID, c.FirstName, c.LastName, o.OrderDate, p.PaymentMethod, p.PaymentDate;

SQL> CREATE VIEW sales_report AS
SELECT 
    o.OrderID,
    c.FirstName,
    c.LastName,
    o.OrderDate,
    pr.ProductName,
    od.Quantity,
    od.Subtotal,
    p.PaymentMethod,
    p.PaymentDate
FROM orders1 o
JOIN customers1 c ON o.CustomerID = c.CustomerID
JOIN order_details od ON o.OrderID = od.OrderID
JOIN products1 pr ON od.ProductID = pr.ProductID
JOIN payments p ON o.OrderID = p.OrderID;

View created.




SQL> CREATE TABLE Students (
    StudentID NUMBER PRIMARY KEY,
    FirstName VARCHAR2(50),
    LastName VARCHAR2(50),
    Gender CHAR(1),
    DOB DATE,
    Department VARCHAR2(50),
    AdmissionYear NUMBER
);

Table created.


SQL> INSERT INTO Students VALUES (101, 'John', 'Doe', 'M', TO_DATE('2002-05-12','YYYY-MM-DD'), 'CSE', 2021);

1 row created.

SQL> INSERT INTO Students VALUES (102, 'Alice', 'Smith', 'F', TO_DATE('2003-03-15','YYYY-MM-DD'), 'ECE', 2021);

1 row created.

SQL> INSERT INTO Students VALUES (103, 'Ravi', 'Kumar', 'M', TO_DATE('2002-08-21','YYYY-MM-DD'), 'EEE', 2021);

1 row created.

SQL> INSERT INTO Students VALUES (104, 'Priya', 'Sharma', 'F', TO_DATE('2003-11-05','YYYY-MM-DD'), 'MECH', 2021);

1 row created.

SQL> INSERT INTO Students VALUES (105, 'Aman', 'Verma', 'M', TO_DATE('2002-07-19','YYYY-MM-DD'), 'CSE', 2021);

1 row created.

SQL> INSERT INTO Students VALUES (106, 'Sneha', 'Reddy', 'F', TO_DATE('2003-04-12','YYYY-MM-DD'), 'ECE', 2021);

1 row created.



SQL> CREATE TABLE Courses (
    CourseID NUMBER PRIMARY KEY,
    CourseCode VARCHAR2(10),
    CourseName VARCHAR2(100),
    Credits NUMBER,
    Department VARCHAR2(50)
);

Table created.



SQL> INSERT INTO Courses VALUES (201, 'CS101', 'Data Structures', 4, 'CSE');

1 row created.

SQL> INSERT INTO Courses VALUES (202, 'CS102', 'DBMS', 4, 'CSE');

1 row created.

SQL> INSERT INTO Courses VALUES (203, 'CS103', 'Operating Systems', 4, 'CSE');

1 row created.

SQL> INSERT INTO Courses VALUES (204, 'EE101', 'Basic Electrical', 3, 'EEE');

1 row created.

SQL> INSERT INTO Courses VALUES (205, 'ME101', 'Thermodynamics', 3, 'MECH');

1 row created.

SQL> INSERT INTO Courses VALUES (206, 'EC101', 'Digital Electronics', 3, 'ECE');

1 row created.



SQL> CREATE TABLE Semesters (
    SemesterID NUMBER PRIMARY KEY,
    SemesterName VARCHAR2(20),
    StartDate DATE,
    EndDate DATE
);

Table created.


SQL> INSERT INTO Semesters VALUES (301, 'Sem1-2024', TO_DATE('2024-01-01','YYYY-MM-DD'), TO_DATE('2023-06-01','YYYY-MM-DD'));

1 row created.

SQL> INSERT INTO Semesters VALUES (302, 'Sem2-2024', TO_DATE('2024-07-01','YYYY-MM-DD'), TO_DATE('2023-06-01','YYYY-MM-DD'));

1 row created.

SQL> INSERT INTO Semesters VALUES (303, 'Sem1-2023', TO_DATE('2023-01-01','YYYY-MM-DD'), TO_DATE('2023-06-01','YYYY-MM-DD'));

1 row created.

SQL> INSERT INTO Semesters VALUES (304, 'Sem2-2023', TO_DATE('2023-07-01','YYYY-MM-DD'), TO_DATE('2023-12-01','YYYY-MM-DD'));

1 row created.

SQL> INSERT INTO Semesters VALUES (305, 'Sem1-2025', TO_DATE('2025-01-01','YYYY-MM-DD'), TO_DATE('2025-06-01','YYYY-MM-DD'));

1 row created.

SQL> INSERT INTO Semesters VALUES (306, 'Sem2-2025', TO_DATE('2025-07-01','YYYY-MM-DD'), TO_DATE('2025-12-01','YYYY-MM-DD'));

1 row created.

SQL> INSERT INTO Semesters VALUES (307, 'Sem1-2022', TO_DATE('2022-01-01','YYYY-MM-DD'), TO_DATE('2022-06-01','YYYY-MM-DD'));

1 row created.

SQL> INSERT INTO Semesters VALUES (308, 'Sem2-2022', TO_DATE('2022-07-01','YYYY-MM-DD'), TO_DATE('2022-12-01','YYYY-MM-DD'));

1 row created.



SQL> CREATE TABLE Grades (
    GradeID NUMBER PRIMARY KEY,
    StudentID NUMBER,
    CourseID NUMBER,
    SemesterID NUMBER,
    Marks NUMBER,
    Grade CHAR(2),
    GPA NUMBER(3,1),
    FOREIGN KEY (StudentID) REFERENCES Students(StudentID),
    FOREIGN KEY (CourseID) REFERENCES Courses(CourseID),
    FOREIGN KEY (SemesterID) REFERENCES Semesters(SemesterID)
);  

Table created.


