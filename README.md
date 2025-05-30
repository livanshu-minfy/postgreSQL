# postgreSQL


Microsoft Windows [Version 10.0.22631.5189]
(c) Microsoft Corporation. All rights reserved.

C:\Program Files\PostgreSQL\17\pgAdmin 4\runtime>"C:\Program Files\PostgreSQL\17\pg
Admin 4\runtime\psql.exe" "host=localhost port=5432 dbname=postgres user=postgres s
slmode=prefer connect_timeout=10" 2>>&1
psql (17.5)
WARNING: Console code page (437) differs from Windows code page (1252)
         8-bit characters might not work correctly. See psql reference
         page "Notes for Windows users" for details.
Type "help" for help.

postgres=# CREATE DATABASE university_db OWNER livanshu;
CREATE DATABASE
postgres=# GRANT ALL PRIVILIGES ON DATABSE university_db TO livanshu;
ERROR:  syntax error at or near "PRIVILIGES"
LINE 1: GRANT ALL PRIVILIGES ON DATABSE university_db TO livanshu;
                  ^
postgres=# GRANT ALL PRIVILEGES ON DATABSE university_db TO livanshu;
ERROR:  syntax error at or near "university_db"
LINE 1: GRANT ALL PRIVILEGES ON DATABSE university_db TO livanshu;
                                        ^
postgres=# GRANT ALL PRIVILEGES ON DATABASE university_db TO livanshu;
GRANT
postgres=# \q

C:\Program Files\PostgreSQL\17\pgAdmin 4\runtime>psql -U livanshu -d university_db
psql (17.5)
WARNING: Console code page (437) differs from Windows code page (1252)
         8-bit characters might not work correctly. See psql reference
         page "Notes for Windows users" for details.
Type "help" for help.

university_db=> \1
invalid command \1
Try \? for help.
university_db=> \
invalid command \
Try \? for help.
university_db=> \?
General
  \bind [PARAM]...       set query parameters
  \copyright             show PostgreSQL usage and distribution terms
  \crosstabview [COLUMNS] execute query and display result in crosstab
  \errverbose            show most recent error message at maximum verbosity
  \g [(OPTIONS)] [FILE]  execute query (and send result to file or |pipe);
                         \g with no arguments is equivalent to a semicolon
  \gdesc                 describe result of query, without executing it
  \gexec                 execute query, then execute each value in its result
  \gset [PREFIX]         execute query and store result in psql variables
  \gx [(OPTIONS)] [FILE] as \g, but forces expanded output mode
  \q                     quit psql
  \watch [[i=]SEC] [c=N] [m=MIN]
                         execute query every SEC seconds, up to N times,
                         stop if less than MIN rows are returned

Help
  \? [commands]          show help on backslash commands
  \? options             show help on psql command-line options
  \? variables           show help on special variables
  \h [NAME]              help on syntax of SQL commands, * for all commands

Query Buffer
  \e [FILE] [LINE]       edit the query buffer (or file) with external editor
  \ef [FUNCNAME [LINE]]  edit function definition with external editor
  \ev [VIEWNAME [LINE]]  edit view definition with external editor
  \p                     show the contents of the query buffer
  \r                     reset (clear) the query buffer
  \w FILE                write query buffer to file

Input/Output
  \copy ...              perform SQL COPY with data stream to the client host
  \echo [-n] [STRING]    write string to standard output (-n for no newline)
  \i FILE                execute commands from file
  \ir FILE               as \i, but relative to location of current script
  \o [FILE]              send all query results to file or |pipe
  \qecho [-n] [STRING]   write string to \o output stream (-n for no newline)
  \warn [-n] [STRING]    write string to standard error (-n for no newline)

Conditional
  \if EXPR               begin conditional block
  \elif EXPR             alternative within current conditional block
  \else                  final alternative within current conditional block
  \endif                 end conditional block

Informational
  (options: S = show system objects, + = additional detail)
  \d[S+]                 list tables, views, and sequences
  \d[S+]  NAME           describe table, view, sequence, or index
  \da[S]  [PATTERN]      list aggregates
  \dA[+]  [PATTERN]      list access methods
  \dAc[+] [AMPTRN [TYPEPTRN]]  list operator classes
  \dAf[+] [AMPTRN [TYPEPTRN]]  list operator families
  \dAo[+] [AMPTRN [OPFPTRN]]   list operators of operator families
  \dAp[+] [AMPTRN [OPFPTRN]]   list support functions of operator families
  \db[+]  [PATTERN]      list tablespaces
  \dc[S+] [PATTERN]      list conversions
  \dconfig[+] [PATTERN]  list configuration parameters
  \dC[+]  [PATTERN]      list casts
  \dd[S]  [PATTERN]      show object descriptions not displayed elsewhere
  \dD[S+] [PATTERN]      list domains
  \ddp    [PATTERN]      list default privileges
  \dE[S+] [PATTERN]      list foreign tables
  \des[+] [PATTERN]      list foreign servers
  \det[+] [PATTERN]      list foreign tables
  \deu[+] [PATTERN]      list user mappings
  \dew[+] [PATTERN]      list foreign-data wrappers
  \df[anptw][S+] [FUNCPTRN [TYPEPTRN ...]]
                         list [only agg/normal/procedure/trigger/window] functions
  \dF[+]  [PATTERN]      list text search configurations
  \dFd[+] [PATTERN]      list text search dictionaries
  \dFp[+] [PATTERN]      list text search parsers
  \dFt[+] [PATTERN]      list text search templates
  \dg[S+] [PATTERN]      list roles
  \di[S+] [PATTERN]      list indexes
  \dl[+]                 list large objects, same as \lo_list
  \dL[S+] [PATTERN]      list procedural languages
  \dm[S+] [PATTERN]      list materialized views
  \dn[S+] [PATTERN]      list schemas
  \do[S+] [OPPTRN [TYPEPTRN [TYPEPTRN]]]
                         list operators
  \dO[S+] [PATTERN]      list collations
  \dp[S]  [PATTERN]      list table, view, and sequence access privileges
  \dP[itn+] [PATTERN]    list [only index/table] partitioned relations [n=nested]
  \drds [ROLEPTRN [DBPTRN]] list per-database role settings
  \drg[S] [PATTERN]      list role grants
  \dRp[+] [PATTERN]      list replication publications
  \dRs[+] [PATTERN]      list replication subscriptions
  \ds[S+] [PATTERN]      list sequences
  \dt[S+] [PATTERN]      list tables
  \dT[S+] [PATTERN]      list data types
  \du[S+] [PATTERN]      list roles
  \dv[S+] [PATTERN]      list views
  \dx[+]  [PATTERN]      list extensions
  \dX     [PATTERN]      list extended statistics
  \dy[+]  [PATTERN]      list event triggers
  \l[+]   [PATTERN]      list databases
  \sf[+]  FUNCNAME       show a function's definition
  \sv[+]  VIEWNAME       show a view's definition
  \z[S]   [PATTERN]      same as \dp

Large Objects
  \lo_export LOBOID FILE write large object to file
  \lo_import FILE [COMMENT]
                         read large object from file
  \lo_list[+]            list large objects
  \lo_unlink LOBOID      delete a large object

Formatting
  \a                     toggle between unaligned and aligned output mode
  \C [STRING]            set table title, or unset if none
  \f [STRING]            show or set field separator for unaligned query output
  \H                     toggle HTML output mode (currently off)
  \pset [NAME [VALUE]]   set table output option
                         (border|columns|csv_fieldsep|expanded|fieldsep|
                         fieldsep_zero|footer|format|linestyle|null|
                         numericlocale|pager|pager_min_lines|recordsep|
                         recordsep_zero|tableattr|title|tuples_only|
                         unicode_border_linestyle|unicode_column_linestyle|
                         unicode_header_linestyle|xheader_width)
  \t [on|off]            show only rows (currently off)
  \T [STRING]            set HTML <table> tag attributes, or unset if none
  \x [on|off|auto]       toggle expanded output (currently off)

Connection
  \c[onnect] {[DBNAME|- USER|- HOST|- PORT|-] | conninfo}
                         connect to new database (currently "university_db")
  \conninfo              display information about current connection
  \encoding [ENCODING]   show or set client encoding
  \password [USERNAME]   securely change the password for a user

Operating System
  \cd [DIR]              change the current working directory
  \getenv PSQLVAR ENVVAR fetch environment variable
  \setenv NAME [VALUE]   set or unset environment variable
  \timing [on|off]       toggle timing of commands (currently off)
  \! [COMMAND]           execute command in shell or start interactive shell

Variables
  \prompt [TEXT] NAME    prompt user to set internal variable
  \set [NAME [VALUE]]    set internal variable, or list all if no parameters
  \unset NAME            unset (delete) internal variable

university_db=>

university_db=>
university_db=> CREATE TABLE students (
university_db(>     student_id INTEGER,
university_db(>     first_name VARCHAR(50),
university_db(>     last_name VARCHAR(50),
university_db(>     email VARCHAR(100),
university_db(>     date_of_birth DATE
university_db(> );
CREATE TABLE
university_db=> \d
          List of relations
 Schema |   Name   | Type  |  Owner
--------+----------+-------+----------
 public | students | table | livanshu
(1 row)


university_db=> ALTER TABLE students ADD COLUMN enrollment_date DATE;
ALTER TABLE
university_db=> \d
          List of relations
 Schema |   Name   | Type  |  Owner
--------+----------+-------+----------
 public | students | table | livanshu
(1 row)


university_db=> ALTER TABLE students DROP COLUMN enrollment_date;
ALTER TABLE
university_db=> \d
          List of relations
 Schema |   Name   | Type  |  Owner
--------+----------+-------+----------
 public | students | table | livanshu
(1 row)


university_db=> ALTER TABLE students ALTER COLUMN email TYPE VARCHAR(150);
ALTER TABLE
university_db=> ALTER TABLE students RENAME COLUMN date_of_birth TO dob;
ALTER TABLE
university_db=> ALTER TABLE students ADD CONSTRAINT unique_email UNIQUE (email);
ALTER TABLE
university_db=> ALTER TABLE students RENAME TO learners;
ALTER TABLE
university_db=> ALTER TABLE learners RENAME TO students; -- Change it back
ALTER TABLE
university_db=> ALTER TABLE students
university_db-> ADD COLUMN phone_number VARCHAR(20);
ALTER TABLE
university_db=> ALTER TABLE students
university_db-> DROP COLUMN phone_number;
ALTER TABLE
university_db=> INSERT INTO students (student_id, first_name, last_name, email, dob
)
university_db-> VALUES (1, 'Alice', 'Smith', 'alice.smith@example.com', '2003-05-15
');
INSERT 0 1
university_db=> INSERT INTO students (student_id, first_name, last_name, email, dob
)
university_db-> VALUES (2, 'Bob', 'Johnson', 'bob.johnson@example.com', '2002-08-22
'),
university_db->        (3, 'Charlie', 'Brown', 'charlie.brown@example.com', '2003-0
1-10');
INSERT 0 2
university_db=> \d
          List of relations
 Schema |   Name   | Type  |  Owner
--------+----------+-------+----------
 public | students | table | livanshu
(1 row)


university_db=> \db
       List of tablespaces
    Name    |  Owner   | Location
------------+----------+----------
 pg_default | postgres |
 pg_global  | postgres |
(2 rows)


university_db=> INSERT INTO students (student_id, first_name, last_name, email, dob
)
university_db-> VALUES (4, 'Livanshu', 'Saini', 'livanshu.saini@example.com', '2003
-10-12');
INSERT 0 1
university_db=> VALUES (5, 'Konark', 'Sharma', 'konark.sharma@example.com', '2003-1
1-14');
 column1 | column2 | column3 |          column4          |  column5
---------+---------+---------+---------------------------+------------
       5 | Konark  | Sharma  | konark.sharma@example.com | 2003-11-14
(1 row)


university_db=> SELECT * FROM students;
 student_id | first_name | last_name |           email            |    dob
------------+------------+-----------+----------------------------+------------
          1 | Alice      | Smith     | alice.smith@example.com    | 2003-05-15
          2 | Bob        | Johnson   | bob.johnson@example.com    | 2002-08-22
          3 | Charlie    | Brown     | charlie.brown@example.com  | 2003-01-10
          4 | Livanshu   | Saini     | livanshu.saini@example.com | 2003-10-12
(4 rows)


university_db=> INSERT INTO students (student_id, first_name, last_name, email, dob
)
university_db-> VALUES (5, 'Konark', 'Sharma', 'konark.sharma@example.com', '2003-1
1-14'),
university_db-> SELECT * FROM students;
ERROR:  syntax error at or near "SELECT"
LINE 3: SELECT * FROM students;
        ^
university_db=> VALUES (5, 'Konark', 'Sharma', 'konark.sharma@example.com', '2003-1
1-14');
 column1 | column2 | column3 |          column4          |  column5
---------+---------+---------+---------------------------+------------
       5 | Konark  | Sharma  | konark.sharma@example.com | 2003-11-14
(1 row)


university_db=> SELECT * FROM students;
 student_id | first_name | last_name |           email            |    dob
------------+------------+-----------+----------------------------+------------
          1 | Alice      | Smith     | alice.smith@example.com    | 2003-05-15
          2 | Bob        | Johnson   | bob.johnson@example.com    | 2002-08-22
          3 | Charlie    | Brown     | charlie.brown@example.com  | 2003-01-10
          4 | Livanshu   | Saini     | livanshu.saini@example.com | 2003-10-12
(4 rows)


university_db=> INSERT INTO students (student_id, first_name, last_name, email, dob
)
university_db-> VALUES (5, 'Konark', 'Sharma', 'konark.sharma@example.com', '2003-1
1-14');
INSERT 0 1
university_db=> SELECT * FROM students;
 student_id | first_name | last_name |           email            |    dob
------------+------------+-----------+----------------------------+------------
          1 | Alice      | Smith     | alice.smith@example.com    | 2003-05-15
          2 | Bob        | Johnson   | bob.johnson@example.com    | 2002-08-22
          3 | Charlie    | Brown     | charlie.brown@example.com  | 2003-01-10
          4 | Livanshu   | Saini     | livanshu.saini@example.com | 2003-10-12
          5 | Konark     | Sharma    | konark.sharma@example.com  | 2003-11-14
(5 rows)


university_db=> SELECT first_name, last_name, email FROM students;
 first_name | last_name |           email
------------+-----------+----------------------------
 Alice      | Smith     | alice.smith@example.com
 Bob        | Johnson   | bob.johnson@example.com
 Charlie    | Brown     | charlie.brown@example.com
 Livanshu   | Saini     | livanshu.saini@example.com
 Konark     | Sharma    | konark.sharma@example.com
(5 rows)


university_db=> SELECT * FROM students;
 student_id | first_name | last_name |           email            |    dob
------------+------------+-----------+----------------------------+------------
          1 | Alice      | Smith     | alice.smith@example.com    | 2003-05-15
          2 | Bob        | Johnson   | bob.johnson@example.com    | 2002-08-22
          3 | Charlie    | Brown     | charlie.brown@example.com  | 2003-01-10
          4 | Livanshu   | Saini     | livanshu.saini@example.com | 2003-10-12
          5 | Konark     | Sharma    | konark.sharma@example.com  | 2003-11-14
(5 rows)


university_db=> SELECT * FROM students WHERE student_id = 1;
 student_id | first_name | last_name |          email          |    dob
------------+------------+-----------+-------------------------+------------
          1 | Alice      | Smith     | alice.smith@example.com | 2003-05-15
(1 row)


university_db=> SELECT * FROM students WHERE student_id = 2;
 student_id | first_name | last_name |          email          |    dob
------------+------------+-----------+-------------------------+------------
          2 | Bob        | Johnson   | bob.johnson@example.com | 2002-08-22
(1 row)


university_db=> SELECT * FROM students WHERE dob < '2003-01-01';
 student_id | first_name | last_name |          email          |    dob
------------+------------+-----------+-------------------------+------------
          2 | Bob        | Johnson   | bob.johnson@example.com | 2002-08-22
(1 row)


university_db=> SELECT *
university_db-> FROM students
university_db-> WHERE first_name LIKE 'B%' OR first_name LIKE 'C%';
 student_id | first_name | last_name |           email           |    dob
------------+------------+-----------+---------------------------+------------
          2 | Bob        | Johnson   | bob.johnson@example.com   | 2002-08-22
          3 | Charlie    | Brown     | charlie.brown@example.com | 2003-01-10
(2 rows)


university_db=> SELECT * FROM STUDENTS WHERE first_name LIKE 'B%' OR LIKE 'C%';
ERROR:  type "like" does not exist
LINE 1: ...ECT * FROM STUDENTS WHERE first_name LIKE 'B%' OR LIKE 'C%';
                                                             ^
university_db=> SELECT * FROM students WHERE first_name LIKE 'B%' OR LIKE 'C%';
ERROR:  type "like" does not exist
LINE 1: ...ECT * FROM students WHERE first_name LIKE 'B%' OR LIKE 'C%';
                                                             ^
university_db=> SELECT * FROM students WHERE first_name LIKE 'B%' OR first_nam  LIK
E 'C%';
ERROR:  column "first_nam" does not exist
LINE 1: ...ECT * FROM students WHERE first_name LIKE 'B%' OR first_nam ...
                                                             ^
HINT:  Perhaps you meant to reference the column "students.first_name".
university_db=> SELECT * FROM students WHERE first_name LIKE 'B%' OR first_name LIK
E 'C%';
 student_id | first_name | last_name |           email           |    dob
------------+------------+-----------+---------------------------+------------
          2 | Bob        | Johnson   | bob.johnson@example.com   | 2002-08-22
          3 | Charlie    | Brown     | charlie.brown@example.com | 2003-01-10
(2 rows)


university_db=> SELECT * FROM students WHERE email like '%@example.com';
 student_id | first_name | last_name |           email            |    dob
------------+------------+-----------+----------------------------+------------
          1 | Alice      | Smith     | alice.smith@example.com    | 2003-05-15
          2 | Bob        | Johnson   | bob.johnson@example.com    | 2002-08-22
          3 | Charlie    | Brown     | charlie.brown@example.com  | 2003-01-10
          4 | Livanshu   | Saini     | livanshu.saini@example.com | 2003-10-12
          5 | Konark     | Sharma    | konark.sharma@example.com  | 2003-11-14
(5 rows)


university_db=> SELECT * FROM students WHERE email IS NULL;
 student_id | first_name | last_name | email | dob
------------+------------+-----------+-------+-----
(0 rows)


university_db=> UPDATE students
university_db-> SET email = 'alices@example.net'
university_db-> WHERE student_id = 1;
UPDATE 1
university_db=> UPDATE students SET dob = '2003-02-15' WHERE first_name = 'Charlie'
 AND last_name = 'Brown';
UPDATE 1


university_db=# SELECT * FROM students ORDER BY last_name ASC;
 student_id | first_name | last_name |           email            |    dob
------------+------------+-----------+----------------------------+------------
          3 | Charlie    | Brown     | charlie.brown@example.com  | 2003-02-15
          2 | Bob        | Johnson   | bob.johnson@example.com    | 2002-08-22
          4 | Livanshu   | Saini     | livanshu.saini@example.com | 2003-10-12
          5 | Konark     | Sharma    | konark.sharma@example.com  | 2003-11-14
          1 | Alice      | Smith     | alices@example.net         | 2003-05-15
(5 rows)


university_db=# GRANT ALL PRIVILEGES ON DATABASE university_db TO livanshu;
GRANT
university_db=# SELECT * FROM students ORDER BY dob DESC LIMIT 3;
 student_id | first_name | last_name |           email            |    dob
------------+------------+-----------+----------------------------+------------
          5 | Konark     | Sharma    | konark.sharma@example.com  | 2003-11-14
          4 | Livanshu   | Saini     | livanshu.saini@example.com | 2003-10-12
          1 | Alice      | Smith     | alices@example.net         | 2003-05-15
(3 rows)


university_db=# SELECT * from students ORDER BY dob ASC LIMIT 2;
 student_id | first_name | last_name |           email           |    dob
------------+------------+-----------+---------------------------+------------
          2 | Bob        | Johnson   | bob.johnson@example.com   | 2002-08-22
          3 | Charlie    | Brown     | charlie.brown@example.com | 2003-02-15
(2 rows)


university_db=# SELECT * FROM students ORDER BY student_id LIMIT 2 OFFSET 1;
 student_id | first_name | last_name |           email           |    dob
------------+------------+-----------+---------------------------+------------
          2 | Bob        | Johnson   | bob.johnson@example.com   | 2002-08-22
          3 | Charlie    | Brown     | charlie.brown@example.com | 2003-02-15
(2 rows)


university_db=# SELECT COUNT(*) AS total_students FROM students;
 total_students
----------------
              5
(1 row)


university_db=# SELECT COUNT(*) AS total_students FROM students;
 total_students
----------------
              5
(1 row)


university_db=# SELECT min(dob) AS minimum FROM students;
  minimum
------------
 2002-08-22
(1 row)


university_db=# SELECT (DISTINCT last_name) AS dln FROM students;
ERROR:  syntax error at or near "DISTINCT"
LINE 1: SELECT (DISTINCT last_name) AS dln FROM students;
                ^
university_db=# SELECT COUNT(DISTINCT last_name) AS dln FROM students;
 dln
-----
   5
(1 row)


university_db=# DROP TABLE IF EXISTS students; -- Start fresh
DROP TABLE
university_db=#
university_db=# CREATE TABLE students (
university_db(#     student_id SERIAL PRIMARY KEY,  -- student_id is now PK, auto-incrementing, NOT NULL

university_db(#     first_name VARCHAR(50) NOT NULL,
university_db(#     last_name VARCHAR(50) NOT NULL,
university_db(#     email VARCHAR(100) UNIQUE,      -- Email should be unique; can be NULL unless NOT NU
LL is added
university_db(#     dob DATE,
university_db(#     enrollment_status VARCHAR(20) CHECK (enrollment_status IN ('enrolled', 'graduated',
'dropped', 'pending'))
university_db(# );
CREATE TABLE
university_db=#
university_db=# -- Insert data (student_id will be auto-generated)
university_db=# INSERT INTO students (first_name, last_name, email, dob, enrollment_status)
university_db-# VALUES ('Alice', 'Smith', 'alice.smith@example.com', '2003-05-15', 'enrolled');
INSERT 0 1
university_db=# INSERT INTO students (first_name, last_name, email, dob, enrollment_status)
university_db-# VALUES ('Robert', 'Johnson', 'robert.j@example.com', '2002-08-22', 'enrolled');
INSERT 0 1
university_db=# INSERT INTO students (first_name, last_name, email, dob, enrollment_status)
university_db-# VALUES ('Charlie', 'Brown', 'charlie.brown@example.com', '2003-01-10', 'pending');
INSERT 0 1
university_db=#
university_db=# SELECT * FROM students; -- Note the student_id values (1, 2, 3...)
 student_id | first_name | last_name |           email           |    dob     | enrollment_status
------------+------------+-----------+---------------------------+------------+-------------------
          1 | Alice      | Smith     | alice.smith@example.com   | 2003-05-15 | enrolled
          2 | Robert     | Johnson   | robert.j@example.com      | 2002-08-22 | enrolled
          3 | Charlie    | Brown     | charlie.brown@example.com | 2003-01-10 | pending
(3 rows)


university_db=# CREATE TABLE courses (
university_db(#     course_id SERIAL PRIMRY KEY,
university_db(#     course_name VARCHAR(100) NOT NULL UNIQUE,
university_db(#     credits INTEGER CHECK (credits > 0 AND credits < 10) -- Example of CHECK
university_db(# );
ERROR:  syntax error at or near "PRIMRY"
LINE 2:     course_id SERIAL PRIMRY KEY,
                             ^
university_db=#
university_db=# INSERT INTO courses (course_name, credits) VALUES ('Introduction to SQL', 3);
ERROR:  relation "courses" does not exist
LINE 1: INSERT INTO courses (course_name, credits) VALUES ('Introduc...
                    ^
university_db=# INSERT INTO courses (course_name, credits) VALUES ('Database Design', 4);
ERROR:  relation "courses" does not exist
LINE 1: INSERT INTO courses (course_name, credits) VALUES ('Database...
                    ^
university_db=# INSERT INTO courses (course_name, credits) VALUES ('Web Development', 3);
ERROR:  relation "courses" does not exist
LINE 1: INSERT INTO courses (course_name, credits) VALUES ('Web Deve...
                    ^
university_db=# INSERT INTO courses (course_name, credits) VALUES ('Data Structures', 4);
ERROR:  relation "courses" does not exist
LINE 1: INSERT INTO courses (course_name, credits) VALUES ('Data Str...
                    ^
university_db=# CREATE TABLE courses (
university_db(#     course_id SERIAL PRIMRY KEY,
university_db(#     course_name VARCHAR(100) NOT NULL UNIQUE,
university_db(#     credits INTEGER CHECK (credits > 0 AND credits < 10) -- Example of CHECK
university_db(# );
ERROR:  syntax error at or near "PRIMRY"
LINE 2:     course_id SERIAL PRIMRY KEY,
                             ^
university_db=#
university_db=# INSERT INTO courses (course_name, credits) VALUES ('Introduction to SQL', 3);
ERROR:  relation "courses" does not exist
LINE 1: INSERT INTO courses (course_name, credits) VALUES ('Introduc...
                    ^
university_db=# INSERT INTO courses (course_name, credits) VALUES ('Database Design', 4);
ERROR:  relation "courses" does not exist
LINE 1: INSERT INTO courses (course_name, credits) VALUES ('Database...
                    ^
university_db=# INSERT INTO courses (course_name, credits) VALUES ('Web Development', 3);
ERROR:  relation "courses" does not exist
LINE 1: INSERT INTO courses (course_name, credits) VALUES ('Web Deve...
                    ^
university_db=# INSERT INTO courses (course_name, credits) VALUES ('Data Structures', 4);
ERROR:  relation "courses" does not exist
LINE 1: INSERT INTO courses (course_name, credits) VALUES ('Data Str...
                    ^
university_db=# CREATE TABLE courses (
university_db(#     course_id SERIAL PRIMRY KEY,
university_db(#     course_name VARCHAR(100) NOT NULL UNIQUE,
university_db(#     credits INTEGER CHECK (credits > 0 AND credits < 10) -- Example of CHECK
university_db(# );
ERROR:  syntax error at or near "PRIMRY"
LINE 2:     course_id SERIAL PRIMRY KEY,
                             ^
university_db=#
university_db=# INSERT INTO courses (course_name, credits) VALUES ('Introduction to SQL', 3);
ERROR:  relation "courses" does not exist
LINE 1: INSERT INTO courses (course_name, credits) VALUES ('Introduc...
                    ^
university_db=# INSERT INTO courses (course_name, credits) VALUES ('Database Design', 4);
ERROR:  relation "courses" does not exist
LINE 1: INSERT INTO courses (course_name, credits) VALUES ('Database...
                    ^
university_db=# INSERT INTO courses (course_name, credits) VALUES ('Web Development', 3);
ERROR:  relation "courses" does not exist
LINE 1: INSERT INTO courses (course_name, credits) VALUES ('Web Deve...
                    ^
university_db=# INSERT INTO courses (course_name, credits) VALUES ('Data Structures', 4);
ERROR:  relation "courses" does not exist
LINE 1: INSERT INTO courses (course_name, credits) VALUES ('Data Str...
                    ^
university_db=# CREATE TABLE courses (
university_db(#     course_id SERIAL PRIMRY KEY,
university_db(#     course_name VARCHAR(100) NOT NULL UNIQUE,
university_db(#     credits INTEGER CHECK (credits > 0 AND credits < 10) -- Example of CHECK
university_db(# );
ERROR:  syntax error at or near "PRIMRY"
LINE 2:     course_id SERIAL PRIMRY KEY,
                             ^
university_db=#
university_db=# INSERT INTO courses (course_name, credits) VALUES ('Introduction to SQL', 3);
ERROR:  relation "courses" does not exist
LINE 1: INSERT INTO courses (course_name, credits) VALUES ('Introduc...
                    ^
university_db=# INSERT INTO courses (course_name, credits) VALUES ('Database Design', 4);
ERROR:  relation "courses" does not exist
LINE 1: INSERT INTO courses (course_name, credits) VALUES ('Database...
                    ^
university_db=# INSERT INTO courses (course_name, credits) VALUES ('Web Development', 3);
ERROR:  relation "courses" does not exist
LINE 1: INSERT INTO courses (course_name, credits) VALUES ('Web Deve...
                    ^
university_db=# INSERT INTO courses (course_name, credits) VALUES ('Data Structures', 4);
ERROR:  relation "courses" does not exist
LINE 1: INSERT INTO courses (course_name, credits) VALUES ('Data Str...
                    ^
university_db=# CREATE TABLE cources{}
university_db-# sva
university_db-#
university_db-# fa
university_db-# df
university_db-# daf
university_db-# a
university_db-# ga
university_db-# g
university_db-# ag
university_db-# g
university_db-# \q

C:\Program Files\PostgreSQL\17\pgAdmin 4\runtime>"C:\Program Files\PostgreSQL\17\pgAdmin 4\runtime\psql.
exe" "host=localhost port=5432 dbname=university_db user=postgres sslmode=prefer connect_timeout=10" 2>>
&1
psql (17.5)
WARNING: Console code page (437) differs from Windows code page (1252)
         8-bit characters might not work correctly. See psql reference
         page "Notes for Windows users" for details.
Type "help" for help.

university_db=# CREATE TABLE courses (
university_db(#     course_id SERIAL PRIMARY KEY,     course_name VARCHAR(100) NOT NULL UNIQUE,
university_db(#     credits INTEGER CHECK (credits > 0 AND credits < 10) -- Example of CHECK
university_db(# );
CREATE TABLE
university_db=#
university_db=# INSERT INTO courses (course_name, credits) VALUES ('Introduction to SQL', 3);
INSERT 0 1
university_db=# INSERT INTO courses (course_name, credits) VALUES ('Database Design', 4);
INSERT 0 1
university_db=# INSERT INTO courses (course_name, credits) VALUES ('Web Development', 3);
INSERT 0 1
university_db=# INSERT INTO courses (course_name, credits) VALUES ('Data Structures', 4);
INSERT 0 1
university_db=# CREATE TABLE enrollments (
university_db(#     enrollment_id SERIAL PRIMARY KEY,
university_db(#     student_id INTEGER NOT NULL,
university_db(#     course_id INTEGER NOT NULL,
university_db(#     enrollment_date DATE DEFAULT CURRENT_DATE, -- Sets default if not specified
university_db(#     grade CHAR(1) CHECK (grade IN ('A', 'B', 'C', 'D', 'F', 'W', NULL)), -- W for withdr
aw, NULL if not graded
university_db(#
university_db(#     -- Foreign Key constraint for student_id
university_db(#     CONSTRAINT fk_student
university_db(#         FOREIGN KEY (student_id)
university_db(#         REFERENCES students(student_id)
university_db(#         ON DELETE CASCADE, -- If a student is deleted, their enrollments are also delete
d.
university_db(#                            -- Other options: ON DELETE RESTRICT, ON DELETE SET NULL, ON
DELETE SET DEFAULT
university_db(#
university_db(#     -- Foreign Key constraint for course_id
university_db(#     CONSTRAINT fk_course
university_db(#         FOREIGN KEY (course_id)
university_db(#         REFERENCES courses(course_id)
university_db(#         ON DELETE RESTRICT, -- (Default if not specified) Prevent deleting a course if s
tudents are enrolled.
university_db(#
university_db(#     -- Ensure a student cannot enroll in the same course multiple times (if semester isn
't a factor)
university_db(#     UNIQUE (student_id, course_id)
university_db(# );
CREATE TABLE
university_db=# INSERT INTO enrollments (student_id, course_id, grade) VALUES (1, 1, 'A');
INSERT 0 1
university_db=# INSERT INTO enrollments (student_id, course_id) VALUES (1, 2); -- Grade will be NULL
INSERT 0 1
university_db=# INSERT INTO enrollments (student_id, course_id, grade) VALUES (2, 1, 'B');
INSERT 0 1
university_db=# INSERT INTO enrollments (student_id, course_id, grade) VALUES (2, 1, 'B');
ERROR:  duplicate key value violates unique constraint "enrollments_student_id_course_id_key"
DETAIL:  Key (student_id, course_id)=(2, 1) already exists.
university_db=#
