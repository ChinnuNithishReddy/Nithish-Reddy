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
