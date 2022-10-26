•	What Is a Database?


Database is an organize collection of info/data stored electronically. It’s normally controlled by DBMS. 


•	What is Structured Query Language (SQL)?


SQL is a programming language	used by relational databases to define data and give control. 


•	What’s the difference between a database and a spreadsheet?


They are both use to store information. But they differ by how you store and manipulate the data, who can access it and the amount of data that can be stored. Spreadsheets are best for singular user while databases are made to hold bigger collections of information. Databases let multiple users, simultaneously and securely, access the query using a complex language and logic.


•	Types of databases


Relational databases
Object-oreiented databases
Distributed databases 
Data warehouses 
NoSQL databases
Graph databases 
Open source databases
Cloud databases
Multimodal databases
Document/JSON database
Self-driven databases



•	What is database software?


It is a use to create, manipulate, and maintain files and record. It makes handling and creating large records easier. It has multi-access control and security. Sometimes it’s referred to as DBMS


•	What is a database management system (DBMS)?


DBMS stands for database management system. Examples include MySQL, Microsoft Access, Oracle Database, FileMaker Pro, and more.



•	What is a MySQL database?


It’s an DBMS designed for web apps and run on any platform. Used for ecommerce businesses that have to handle a lot of money transactions. 


•	Database challenges


Absorbing significant increases in data volume, ensuring data security, keeping up with demand, managing and maintain database and infrastructure, removing limits on scalability, ensuring data residency


SQL- manipulates sets of data-once you know SQL, other queries are easy.



Ansi and ISO standards



SQL COMMANDS


SELECT-get data, be more explicit is best-good practice is to qualify column name with table name(ex select person.first_name, person.last_name FROM person); 
You can Aliasing the table(best practice) name with doing it like (select p.first_name, p.last_name FROM person p); 


INSERT- add one or more rows into a table

UPDATES-modifies one or more row in table

DELETE-removes one or more rows from one table 

FROM clause defines the table you want to query 


Ways to Constrain the Number of Results-

WHERE Clause - constrains the result set, comes after the FROM clause, contains boolean expresion

Distinct qualifier (SELECT DISTINCT p.first_name FROM person p);will take all the values and wont show duplicates 
cant be used for DISTINCT country names so it's not a repeated list

