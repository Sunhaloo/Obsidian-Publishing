---
aliases: Database Systems ( Semester 1 - Tutorial 2 ) - Week 3
Tag: uni, db, theory, uom, tutorial
Module: ICDT 1202Y
Author: S.Sunhaloo
Date: 2024-08-07
Status: In-Progress
---

### My Links

- [[Database Systems - Tutorial 2#Socials | Link to Socials]]

---

# Question 1

Describe, using appropriate examples, the constraint called Referential Integrity.

>[!tip]- Answers
>The **Referential Integrity** refers to the *relationships* between tables.
>It is the **logical** dependency of a Foreign Key on a Primary Key
>Example: We have 2 tables; 'X' and 'Y'
>The **primary** key of table 'X' is a **foreign** key in table 'Y'
>Now if we user is going to **delete** / **update** a *record* in table 'Y', its <span style="color: red;"><strong>not</strong></span> going to let the user.
>This is because it has a relationship with table 'X'

# Question 2

The main objective of for the three-level database architecture ( comprising of an *external*, *conceptual*, and an *internal* level ) is to provide data independence. Explain what is meant by data independence and its importance in a database environment.

>[!tip]- Answers
>It is a type of data transparency that hides the complex details and layers of a DBMS to a user
>- Provides some type of abstraction to hide the complexities of the DBMS software.
>
>It provides the user the ability to re-write the **logical schema** without needing to re-write the **external levels** ( *user views* / *front-end applications* )

# Question 3

Explain the difference between database schema and database state?

>[!tip]- Answers
>>Database Schema $\Rightarrow$ Its the whole entire things
>>Database State $\Rightarrow$ Data stored in the Database at a particular point in time
>
>The database *schema* is the **description** of the whole database which includes things like:
>- Description of Structure
>- Description of Constraints
>	- Like `PRIMARY KEY`, `FOREIGN KEY`, `CHECK` and more
>
>This can be represented using a *Schema Diagram* which looks something like this $\downarrow$:
>![[Database Schema Diagram Example.png | 800]]
>
>---
>
>The database *instance* / *state* ( *the word state tells you most of it* ) is the actual ( set ) of data ( *I think this can includes things like tables, indices, types, values / elements in tables* ) that is stored in a database at a particular point in time.
>>For **new** database which does not have any data, we say that its in an *Empty State*.
>

# Question 4

Super key, candidate key and primary key are used to identify tuples in a relation. Briefly explain the differences between these three types of keys.

>[!tip]- Answer
>## Super Key
>
>It is a set of 1 or more attributes ( *fields / columns* ) that can uniquely identify a **record** ( *row* ) in a table.
>
>### Example of Super Key
>
>Take a look at this employee table below $\downarrow$:
>
>| EmployeeID | Name | Email | PhoneNumber |
>| ---------- | ---- | ----- | ----------- |
>
>In this case:
>- `EmployeeID` is a super key
>- `Email` is a super key
>- `EmployeeID, Name` ( *both* ) is a super key
>	- But `Name` **alone** <span style="color: red;"><strong>not</strong></span> be a super key
>
>---
>
>## Candidate Key
>
>It is a set of 1 or more attributes in a database table that can uniquely identify **any** row in *that* table
>- Candidate Keys should be minimal $\Rightarrow$ no `EmployeeID, Name`
>
>### Example of Candidate Key
>
>Again we have this table 'Students' which has the following columns / fields
>
>| StudentID | Name | Email | Phone Number |
>| --------- | ---- | ----- | ------------ |
>
>In this case:
>- `StudentID` *can* be a Candidate Key
>	- It can identify **each** student / record uniquely
>- `Email` can also be a Candidate Key
>	- Each email is going to be `UNIQUE` $\Rightarrow$ can uniquely identify **each** record in the table
>
>---
>
>## Primary Key
>It is a specific choice of **minimal** ( *no `EmployeeID, Name`* ) set of attributes in a database that can uniquely identify each record in a table
>>[!note]
>>In HSC, we learned that Candidate Keys are the ones that move on the become the Primary Keys.
>>Hence, in a table, we could have **many** Candidate Keys but 1 Primary Key if we are not creating a *Composite Primary Key*
>
>Characteristics of Primary Key:
>- Combines both `UNIQUE` and `NOT NULL` constraints
>- Immutable
>	- Its values does not change over time
>- Again like I said can be *Single* or *Composite*
>

# Question 5

Differentiate between entity integrity and referential integrity constraints

>[!tip]- Answers
>- Entity Integrity forces all rows of a table to have unique ( *values* ) key identifier. This is basically the job of the **Primary Key**.
>	- It ensures that every values in each record in `UNIQUE` and `NOT NULL` value.
>- Referential Integrity focuses on relationships between tables. It ensures that all values in the table is valid and same in **both** tables.
>	- This is achieved using **Primary Keys** and **Foreign Keys**
>	- It is the logical dependency of a foreign key on a primary key
>

# Question 6

The ANSI-SPARC model of a database identifies three distinct levels at which data items can be described. List and explain each level.

>[!tip]- Answers
>1. External Level
>	- This level represents the user views
>	- Each user can have his / her own views tailored to his / her needs
>	- Excludes irrelevant data what the user does not need / authorised to see
>2. Logical / Conceptual Level
>	- Logical outline of entire database ( Entity Relationship Diagrams )
>	- Provides unified and abstract view of entire database, implementation details / physical storage considerations
>3. Internal / Physical Level
>	- The physical storage implementation of where data are going to be stored
>		- Think of hard drives and servers
>	- The internal schema will describe
>		- Data Structures
>		- Indexing Methods ( *I know its related to faster data search and retrieval* )

# Question 7

## Part (a)

>Used online resources for this one

>[!tip]- Answers
>1. ConsultancyName
>	- Domain: Strings Datatype
>2. FeeRate
>	- Domain: Greater than 0 Integer Numbers
>3. ConsultancyHrs
>	- Domain: Positive Integer Numbers ( *can be 0* )

## Part (b)

- Super Keys 1 or set of attributes can uniquely identify each value in **a** row / record in a table
- Candidate Key is 1 or set of attribute that can uniquely identify **any** row in a table
- Primary Key is specific choice of *minimal* set of attributes in a table that can uniquely identify each row in a record.

# How to Obtain Primary Key

- Check each column / field / attribute
- Check if they have repeating values
	- Example: `ConsultantNames`, `ConsultantCategory` **cannot** be Primary Key
- Check the functional dependency
	- Column `A` maps onto `B` and vice versa
	- Column `A, B` maps onto `X, Y` and vice versa
	- Column `A, B, C` maps onto `X, Y, Z` and vice versa

---

# Socials

- **Instagram**: https://www.instagram.com/s.sunhaloo
- **YouTube**: https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg
- **GitHub**: https://www.github.com/Sunhaloo

---

S.Sunhaloo
Thank You!