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

