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

Table created. SQL> insert into customer (id, fristname, lastname, city)
  2  values
  3  (101,'chinnu','reddy',1);

1 row created. SQL> insert into customer (id, fristname, lastname, city)
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
