---
Alias: Database Systems ( Database Keys ) - Week 2
Tag: uni, db, uom
Module: ICDT 1202Y
Author: S.Sunhaloo
Date:  2024-07-30
Status: Completed
---

## List of Contents

- [[Database Keys#Super Keys | Super Keys]]
	- [[Database Keys#Example of Super Key | Example of Super Key]]
- [[Database Keys#Candidate Keys | Candidate Keys]]
	- [[Database Keys#Example of Candidate Key | Example of Candidate Key]]
- [[Database Keys#Primary Keys | Primary Keys]]
	- [[Database Keys#Primary Key v/s Candidate Key | Primary Key v/s Candidate Key]]
	- [[Database Keys#Example of Primary Key | Example of Primary Key]]
- [[Database Keys#Foreign Keys | Foreign Keys]]
	- [[Database Keys#Example of Foreign Key | Example of Foreign Key]]

---

### My Links

- [[Database Keys#Socials | Links to Socials]]

---

# Super Keys

>[!tip]- Definition
>It is a set of one or more **attributes** ( *or field or columns* ) that can **uniquely** identify a *row* ( *or record* ) in a table.

## Characteristics of Super Key

- Uniqueness
	- As it can uniquely identify each record in a table.
	- No 2 rows can have the same combination of values for the attributes in the super key
- Minimality
	- It does *not* need to be minimal
	- Hence, it can contain additional attributes in that are not necessary for uniqueness.
	- If a Super Key has no extraneous attributes $\Rightarrow$ It is said to be a **Candidate Key**

### Example of Super Key

Consider the following table below $\downarrow$:

Table: Employee

| EmployeeID | Name | Email | PhoneNumber |
| ---------- | ---- | ----- | ----------- |

In this case:

- `EmployeeID` is a super key; because it can uniquely identify each employee
- `Email` $\rightarrow$ this one is also a super key; because all the employees are going to have *unique* email addresses
- `EmployeeID, Name` $\rightarrow$ again this is a super key that is **not** minimal; because `Name` alone cannot uniquely identify our employees ( *because some employee can have the same name* ).

>The last example shows that the Super Key can be "*not*" minimal.

>[!info] Summary
>Super Keys are essential in [[Types of Database Model#Relational Model | relational]] databases to maintain [[Data Integrity | data integrity]] and ensure that each row can be uniquely identified.

# Candidate Keys

>[!tip]- Definition
>It is a set of one or more attributes / columns in a database table that can uniquely identify any row in that table.

It's basically like [[Database Keys#Super Keys | Super Keys]] $\uparrow$ but this time; it has not unnecessary attributes $\Rightarrow$ It is a <span style="color: green;">minimal</span> set of columns that can uniquely identify a record.

## Characteristics of Candidate Key

- Uniqueness
	- Each value in the candidate key must be unique **across all** rows in the table
	- Ensuring that no 2 rows have the same values for all attributes in the candidate key
- Minimality
	- The Candidate Key will only contains the **required** *attributes* to ensure **uniqueness**
	- No subset of the candidate key can uniquely identify a row in a table.

>[!warning]
>A Super Key *can* be minimal while a Candidate Key <span style="color: red;"><strong>needs</strong></span> to be minimal!!!
>>If the Candidate Key includes extra attributes; it is **not** minimal and hence **not** a Candidate Key!

### Example of Candidate Key

Take a look at the following table below $\downarrow$:

Table: Students

| StudentID | Name | Email | Phone Number |
| --------- | ---- | ----- | ------------ |

Hence, we have the following statements:

- `StudentID` can be a Candidate Key because it can uniquely identify **each** student and is minimal ( *by itself* )
- `Email` is also a Candidate Key as all students will have unique email addresses
- `StudentID, Name` is <span style="color: red;">not</span> a Candidate Key as it is **not** *alone*!

>Compare the last bullet point to the last bullet point in the [[Database Keys#Example of Super Key | 'Example of Super Key']].

>[!note] [Gentlemen, A Short View Back to the Past](https://www.youtube.com/watch?v=FlFt_W4664M)
>In HSC, we learned that the Primary Key comes from a Candidate Key.
>Meaning that we can have **many** Candidate Keys but then again, we can only have **1** Primary Key ( *just forget about Composite Primary Key for a second mate* )
>What I am trying to say that the **Properties** / **Characteristic** of a Candidate Key is the **same** ( *more or less* ) as a Primary Key
>>Our short view back to the past has finished!

>[!tip] Summary
>It is a crucial concept in design and normalisation of relational database ensuring Data Integrity and Consistency

# Primary Keys

>I have already made a "*note*" on Primary Key in the file / note [[Microsoft Access ( 2007 )#Primary Key | Microsoft Access ( 2007 )]]
>But I have going to remake it just so that it is in the format of other headers in this file.
>I know that I am going against the Conceptual Note taking method and Obsidian linking philosophy.

>[!tip]- Definition
>It is a specific choice of **minimal** set of attributes ( *fields / columns* ) in a database table that uniquely identifies each record / row in that table.
>>It is basically a unique record identifier.

## Characteristics of Primary Key

- Uniqueness
	- Each value in Primary Key column(s) ( *why the 's' because of Composite Primary Key* ) must be unique across **all** rows in that table.
	- Meaning that we can guarantee that no 2 rows have the **same** Primary Key value
- Not Null
	- It should <span style="color: red;">not</span> contain `NULL` values.
	- Primary Key column should **have** a value each record to be able to enforce uniqueness
- Immutability
	- The **values** of the Primary Key *column* should **not** change over time
	- If so; it can / could lead to data inconsistencies
- Single or Composite
	- Primary Key can consist of a single attribute or multiple attributes $\Rightarrow$ Composite Primary Key

It also enforces [[Data Integrity#What is Entity Integrity? | Entity Integrity]].

>Hence, we can say that "*A Composite Primary Key is made up of 2 or more Primary Keys*"
>But it's normally referred to as "*consists of multiple attributes / fields*"

## Primary Key v/s Candidate Key

All Primary Keys *are* Candidate Keys, but **not** all Candidate Keys are Primary Keys!

>Ohhh!!!

- A Candidate Key is any set of columns that could server as the Primary Key
- The Primary Key is the **specific** Candidate Key chosen to uniquely identify rows in the table.

### Example of Primary Key

Consider this table $\downarrow$

Table: Customers

| CustomerID | FirstName | LastName | Email | PhoneNumber |
| ---------- | --------- | -------- | ----- | ----------- |

- If `CustomerID` is used as *Primary Key*, it must:
	- contain Unique values for each customer
	- `NOT NULL`
	- Uniquely identifies each row in the Customers table

>[!info]
>In cases where no single column can uniquely identify a row.
>A Composite Primary Key can be created using 2 or more columns.
>Example for table `Orders` with columns `OrderID`, `ProductID` and `CustomerID`; We might have `OrderID` and `ProductID` as the Composite Primary Key

>[!tip] Alternate Keys
>They are [[Database Keys#Candidate Keys | Candidate Keys]] that are not selected to be Primary Keys.

# Foreign Keys

>[!tip]- Definition
>It is an attribute or set of attributes in one table that establishes a **link** between the data in two tables
>>Basically, *It is a Primary Key in its table and a Foreign Key in another*; It is used to create [[Entity Relationship Diagram ( ERD ) and Relationships#Relationships | Relationships]]

## Characteristics of Foreign Key

>There we go; what did I just say? $\updownarrow$

- Relationship Establishment
	- It creates a relationship between 2 tables
- [[Data Integrity#What is Referential Integrity? | Referential Integrity]]
	- It ensures that the data in the Foreign Key column(s) matches data in the Primary Key column(s) of the referenced table
	- Prevents invalid data entry and ensures that the relationship between tables remains consistent
- `NULL` Values
	- Foreign Key **can** allow `NULL` depending on the design
	- If Foreign Key in `NULL` then it implies that the relationship between tables does not exist for that particular record
- Cascade Operations
	- Actions like `DELETE` or `UPDATE` of a Primary Key record can *cascade* to referencing table
	- This will **automatically** delete / update corresponding foreign key records

### Example of Foreign Key

>We already know this from O-Level!!!

Table: Customers

| CustomerID | FirstName | LastName | Email | PhoneNumber |
| ---------- | --------- | -------- | ----- | ----------- |

Table: Orders

| OrderID | CustomerID | Product |
| ------- | ---------- | ------- |

As you can see we have the Primary Key of Customers table `CustomerID` in our Orders table; making it a Foreign Key!

>[!tip] Summary
>It is critical component in relational database design.
>It defines the relationships between tables, enforces referential integrity and helps to organise data in a consistent and meaningful way.

---

# Socials

- **Instagram**: https://www.instagram.com/s.sunhaloo
- **YouTube**: https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg
- **GitHub**: https://www.github.com/Sunhaloo

---

S.Sunhaloo
Thank You!