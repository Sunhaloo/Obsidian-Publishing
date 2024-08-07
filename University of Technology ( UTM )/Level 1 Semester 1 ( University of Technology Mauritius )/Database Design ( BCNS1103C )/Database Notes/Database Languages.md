---
Alias: Database Design ( Database Languages ) - Week 1
Tag: uni, db
Module: BCNS1103C / DBT1103C
Author: S.Sunhaloo
Date: 2024-05-18
Status: Completed
---

## List of Contents

 - [[Database Languages#Database Languages | Database Languages]]
	 - [[Database Languages#Structured Query Language ( SQL ) | Structured Query Language ( SQL )]]
		 - [[Database Languages#Data Definition Language ( DDL ) | Data Definition Language ( DDL )]]
		 - [[Database Languages#Data Manipulation Language ( DML ) | Data Manipulation Language ( DML )]]
		 - [[Database Languages#Data Control Language ( DCL ) | Data Control Language ( DCL )]]
		 - [[Database Languages#Data Query Language ( DQL ) | Data Query Language ( DQL )]]
		 - [[Database Languages#Transact-SQL ( T-SQL ) | Transact-SQL ( T-SQL )]]
---

### My Links

- [[Database Languages#Socials | Link to Social]]

---

# Database Languages

## Structured Query Language ( SQL )

The language used to **manage** and **manipulating** data in databases; especially in **Relational Database Management System** ( RDBMS )

It provides a set of commands and syntax for performing various operations on databases

>These *commands* and *syntax* are found below $\downarrow$

>[!info]
>These below $\downarrow$ are all part of / subset of Structured Query Language ( SQL ).

There a different types of database languages

>Things like DDL and DML which we learnt in HSC, but now we have more... we always have more!

## Data Definition Language ( DDL )

>Just remember this is one that create the database while Data Manipulation Language ( *MaNIpuLatIoN* )... fucking manipulates the data.

This "*language*" is responsible for **creating** and **modifying** database objects such as *tables*, *indices* and *users*.

Common statements of DDL are:

- `CREATE`
- `ALTER`
- `DROP`
- `TRUNCATE` $\Rightarrow$ Used to delete **all** data from table; much faster than `DELETE`.

## Data Manipulation Language ( DML )

>Again, things we did learn how to do in HSC; like search, update, delete things.

Complementary of Data Definition Language. Used for adding, deleting and modifying data in a database.

Common statements of DML are:

- `SELECT ... FROM ... WHERE` $\rightarrow$ related to Data Query Language ( *so I think it is a <ins>subset</ins>?* )
- `INSERT INTO ... VALUES ...`
- `UPDATE ... WHERE ...`
- `DELETE FROM ... WHERE ...`

>As from now $\downarrow$, I have **not** done this in HSC!

## Data Control Language ( DCL )

This "*programming language*" is used to control access to data stored in a database. It is a component of Structured Query Language ( SQL )

- Standard language in DBMS
- Command involves:
	- `GRANT` $=$ Allows specified users to perform specified tasks.
		- `GRANT SELECT, INSERT, UPDATE, DELETE, on Employee to User1`
	- `REVOKE` $=$ Removes user accessibility to database object.
		- `REVOKE DELETE, UPDATE on Employee TO User1`
	- `DENY` $=$ Bans certain permissions from groups / users.
		- `DENY INSERT on Employee to User1`

## Data Query Language ( DQL )

>This one is small... *that's what she said* 🙃.

Simply used to make queries in databases and information systems. Also a subject of SQL.

>Most, if not all of them are a subset of SQL. Just checked; YES!
>*After this comment; I added the little 'info' above*.

## Transact-SQL ( T-SQL )

This is Microsoft's and [Sybase](https://en.wikipedia.org/wiki/Sybase)'s proprietary extension of SQL used to interact with relational databases.

It includes: 

- Procedural Programming
- Local Variables
- String and Data Processing
- Mathematics

Its syntax is somewhat different from normal, *vanilla* SQL

```SQL

DECLARE @var1 NVARCHAR(30);
SET @var1 = 'Some Name';
SELECT @var1 = Name;
	FROM Sales.Store
	WHERE CustomerID = 100;

```

We also have things like normal procedural programming like:

```SQL

IF DATEPART(dw, GETDATE()) = 7 OR DATEPART(dw, GETDATE()) = 1
   PRINT 'It is the weekend.';
ELSE
   PRINT 'It is a weekday.';

```

---

# Socials

- [**Instagram**](https://www.instagram.com/s.sunhaloo/)
- [**YouTube**](https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg)
- [**GitHub**](https://www.github.com/Sunhaloo)

---

S.Sunhaloo
Thank You!