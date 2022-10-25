# SQLEXAM

mysql> create table movie(
    -> ID int(10) unsigned NOT NULL AUTO_INCREMENT,
    -> Title varchar(50) NOT NULL DEFAULT '',
    -> Runtime int UNSIGNED NOT NULL DEFAULT 0,
    -> Genre varchar (30) NOT NULL DEFAULT '',
    -> IMBDScore decimal (7,2) NOT NULL DEFAULT 99999.99,
    -> Rating char (10) NOT NULL DEFAULT '',
    -> PRIMARY KEY(ID)
    -> );
Query OK, 0 rows affected, 1 warning (0.06 sec)

mysql> insert into movies VALUES (1, 'Howard the Duck', '110', 'Sci-Fi', 4.6, 'PG');Query OK, 1 row affected (0.00 sec);
ERROR 1136 (21S01): Column count doesn't match value count at row 1
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'Query OK, 1 row affected (0.00 sec)' at line 1
mysql> insert into movie VALUES (1, 'Howard the Duck', '110', 'Sci-Fi', 4.6, 'PG');
Query OK, 1 row affected (0.01 sec)

mysql> insert into movie Values (2, 'Lavalantula', '83', 'Horror', 4.7,'TV-14');
Query OK, 1 row affected (0.01 sec)

mysql> insert into movie VALUES (3, 'Starship Troopers', '129', 'Sci-Fi', 7.2, 'PG-13');
Query OK, 1 row affected (0.01 sec)

mysql>  insert into movie Values (4, 'Waltz With Bashir', '90', 'Documentary', 8.0, 'R');
Query OK, 1 row affected (0.00 sec)

mysql> insert into movie VALUES (5, 'Spaceballs', 96, 'Comedy', 7.1, 'PG');
Query OK, 1 row affected (0.01 sec)

mysql> insert into movie VALUES (6, 'Monster Inc.', 92, 'Animation', 8.1, 'G');
Query OK, 1 row affected (0.00 sec)

mysql> insert into movie VALUES (7, 'Paid In Full', 100, 'Drama', 9.1, 'R');
Query OK, 1 row affected (0.01 sec)

mysql> insert into movie VALUES (8, 'A Bronx Tale', 110, 'Crime', 9.2, 'R');
Query OK, 1 row affected (0.01 sec)

mysql> select titles from movie where Genre LIKE '%i';
ERROR 1054 (42S22): Unknown column 'titles' in 'field list'
mysql> select * from movie;
\\\
+----+-------------------+---------+-------------+-----------+--------+
| ID | Title             | Runtime | Genre       | IMBDScore | Rating |
+----+-------------------+---------+-------------+-----------+--------+
|  1 | Howard the Duck   |     110 | Sci-Fi      |      4.60 | PG     |
|  2 | Lavalantula       |      83 | Horror      |      4.70 | TV-14  |
|  3 | Starship Troopers |     129 | Sci-Fi      |      7.20 | PG-13  |
|  4 | Waltz With Bashir |      90 | Documentary |      8.00 | R      |
|  5 | Spaceballs        |      96 | Comedy      |      7.10 | PG     |
|  6 | Monster Inc.      |      92 | Animation   |      8.10 | G      |
|  7 | Paid In Full      |     100 | Drama       |      9.10 | R      |
|  8 | A Bronx Tale      |     110 | Crime       |      9.20 | R      |
+----+-------------------+---------+-------------+-----------+--------+
8 rows in set (0.00 sec)
\\\

mysql> select Title from movie where Genre LIKE '%i';
+-------------------+
| Title             |
+-------------------+
| Howard the Duck   |
| Starship Troopers |
+-------------------+
2 rows in set (0.00 sec)

mysql> select from movie where IMDBScore <6.5;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'from movie where IMDBScore <6.5' at line 1
mysql> select Title from movie where IMDBScore <6.5;
ERROR 1054 (42S22): Unknown column 'IMDBScore' in 'where clause'
mysql> select Titles from movie where IMBDScore <6.5;
ERROR 1054 (42S22): Unknown column 'Titles' in 'field list'
mysql> select Title from movie where IMBDScore < 6.5;
+-----------------+
| Title           |
+-----------------+
| Howard the Duck |
| Lavalantula     |
+-----------------+
2 rows in set (0.00 sec)

mysql> select * from movie where Rating LIKE '%G' AND Runtime <100;
+----+--------------+---------+-----------+-----------+--------+
| ID | Title        | Runtime | Genre     | IMBDScore | Rating |
+----+--------------+---------+-----------+-----------+--------+
|  5 | Spaceballs   |      96 | Comedy    |      7.10 | PG     |
|  6 | Monster Inc. |      92 | Animation |      8.10 | G      |
+----+--------------+---------+-----------+-----------+--------+
2 rows in set (0.00 sec)

mysql> select AVG(Runtime)
    -> from movie
    -> where IMBDScore <7.5
    -> GROUP BY Genre;
+--------------+
| AVG(Runtime) |
+--------------+
|     119.5000 |
|      83.0000 |
|      96.0000 |
+--------------+
3 rows in set (0.00 sec)

mysql> UPDATE movie
    -> SET Rating = 'R'
    -> where Title= 'Starship Troopers';
Query OK, 1 row affected (0.00 sec)
Rows matched: 1  Changed: 1  Warnings: 0

mysql> select * from movie where Genre Like '%r'AND Genre '%y';
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near ''%y'' at line 1
mysql> SELECT * FROM movie
    -> WHERE Title= 'Horror' OR Title= 'Documentary';
Empty set (0.00 sec)

mysql> Select * from movie
    -> where Genre ='Horror' OR Genre= 'Documentary';
+----+-------------------+---------+-------------+-----------+--------+
| ID | Title             | Runtime | Genre       | IMBDScore | Rating |
+----+-------------------+---------+-------------+-----------+--------+
|  2 | Lavalantula       |      83 | Horror      |      4.70 | TV-14  |
|  4 | Waltz With Bashir |      90 | Documentary |      8.00 | R      |
+----+-------------------+---------+-------------+-----------+--------+
2 rows in set (0.00 sec)

mysql> Select Min(IMBDScore)
    -> From movie
    -> ;
+----------------+
| Min(IMBDScore) |
+----------------+
|           4.60 |
+----------------+
1 row in set (0.00 sec)

mysql> Select MAX(IMBDScore)
    -> from movie;
+----------------+
| MAX(IMBDScore) |
+----------------+
|           9.20 |
+----------------+
1 row in set (0.00 sec)
///
