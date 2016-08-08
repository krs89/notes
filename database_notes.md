# Databases

I have a huge mess in my head about databases in general, but let me summarize the information I came across (mostly on Wikipedia) in the last few hours. Some parts are just copy-pasted others are rephrased by me, please notify me in some way in case it is imprecise.

## Database engine / Storage engine (physical structure)

- This stores the data itself on a storage space (disk, flash drive, magnetic tape).
- The data is structured in some way (*ordered/unordered flat files, heaps, hash tables, B+ trees,* etc.).
- The database can be indexed.
- Some brand names include *Aria, Falcon, InnoDB, MyISAM*

## Database model (logical structure)

A database model is a type of data model that determines the logical structure of a database and fundamentally determines in which manner data can be stored, organized, and manipulated. A given database management system may provide one or more models, such as *hierarchical, network, relational, object, object-relational,* etc.

## Database server

A computer program which provides database services to other computer programs or computers, as defined by the client–server model. The term may also refer to a computer dedicated to running such a program.

Most of the Database servers work with the base of Query language. Each Database understands its query language and converts it to Server readable form and executes it to retrieve the results.

Some examples of database servers are *Oracle, DB2, Informix, Microsoft SQL Server, Ingres and MySQL.*

## Database languages / Query language

**Data Description/Definition Language (DDL)** defines data structures, database schema,(CREATE, DROP, ALTER, RENAME);

**Data Manipulation Language (DML)** is used for selecting, inserting, deleting and updating data in a database;

**Data Control Language (DCL)** is used to control access to data stored in a database (authorization) (GRANT, REVOKE).

It might feature **extra functionalities**:
- configuration & storage engine management
- compute/modify results (sum, avg, sort, group, etc.)
- constraint enforcement
- application programming interface (API)

Database languages are specific to a particular data model. For example __*SQL*__ combines the roles of data definition, data manipulation, and query in a single language based on the relational model. By default it is an **imperative** programming language, but it might have **procedural extensions** such as *SQL/PSM* for MySQL, *PL/SQL* for Oracle, *PL/pgSQL* for PostgresQL.

There are other query languages apart from SQL: *OQL* is an object model language, *XQuery* is a standard XML query language implemented by XML database systems, *SQL/XML* combines XQuery with SQL.

## Database Management System (DBMS)

A computer software application that interacts with the user, other applications, and the database itself to capture and analyze data. Their underlying software component is the database engine, might provide database server functionality, and uses a database language to manage the database (CRUD -- create, read, update and delete).

DBMSs can be categorized according to the database model(s) that they support (such as relational or XML), the type(s) of computer they run on (from a server cluster to a mobile phone), the query language(s) used to access the database (such as SQL or XQuery), and their internal engineering, which affects performance, scalability, resilience, and security.

Well-known DBMSs include *MySQL* (relational -- RDBMS), *PostgreSQL* (object-relational -- ORDBMS), *Microsoft SQL Server*, *Oracle* (relational), etc.


