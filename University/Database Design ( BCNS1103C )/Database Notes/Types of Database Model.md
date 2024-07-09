---
Alias: Database Design ( Database Model )
Tag: uni, db
Module: BCNS1103C / DBTS1103C
Author: S.Sunhaloo
Date: 2024-05-18
Status: Completed
---

## List of Contents

- [[Types of Database Model#Database Models| Database Models]]
	- [[Types of Database Model#What is a Database Model| What is a Database Model]]
		- [[Types of Database Model#Relational Model| Relational Model]]
		- [[Types of Database Model#Hierarchical Model| Hierarchical Model]]
		- [[Types of Database Model#Network Model| Network Model]]

---

### My Links

- [[Types of Database Model#Socials| Link to Social]]

---

# Database Models

>I cannot seem to find this in the <span style="color: red;">lecturer</span>'s slides. So, I will be using trusty Wikipedia alongside other websites to make these notes below $\downarrow$.

## What is a Database Model

A database model shows logical **structure** of a database, including *relationships* and *constraints* that determined how **data** can be *stored* and *accessed*.

There are 3 common types of database models, namely:

- Relational
- Hierarchical
- Network

### Relational Model

>Most popular to this day.

An approach to managing data using a structured and language consistent with the [first order predicate](https://en.wikipedia.org/wiki/First-order_logic).

Data is represented in terms of **tuples**, grouped into **relations**.

A database organised in terms of relational model is called a **relational database**.
For example [[Microsoft Access ( 2007 ) | Microsoft Access]] is a relational database software ( *RDMS / RDBMS* ).

What is the purpose of Relational Database Model?

To provide *declarative* ( *like the programming thing* ) method for specifying data and queries.
Users will just ask what information the database contains and what information they want from it; then just let the Database Management Software take care of describing, storing and retrieval procedures for answering queries.

#### Use Cases of Relational Model

- Tracking Inventory / Inventory Management
- Transactional / Financial Data
- Application Logging

#### Structure of Relational Model

Here is a look on how relational database model looks like:

![[Relational Database Model.png | 400]]

- My Version

![[Relational Database Model - My Version.png | 600]]

>[!warning] MISTAKE / Misinterpretation
>As you know the *field* is the **attribute**, but in the image you will see that I wrote `Attributes / Columns`, technically correct. But normally, the attributes will be stuff like: `CusomterID`, etc.

>[!tip]- Definitions
>Structural Part
>- Types of structures from which the database is constructed
>	- How data is physically stored
>
>Manipulative Part
>- What are the operations that are used to **retrieve** and **update** data in the *database*
>
>Integrity Part
>- Rules that all *valid* database must follow
>	- Verification / Validation, etc
>
>*Degree* of a Relation
>- It refers to the number of **attributes** / columns in the given table
>
>*Cardinality* of a Relation
>- It refers to the number of **unique values** in a relational table column relative to the total number of rows in the table
>	- Refers to the number of **tuples** / records / rows


---

### Hierarchical Model

Instead of using tuples and fields to organise data. We are now going to use a **tree**-like structure ( *see, "Hierarchical"* ).

Data are stored as **records** which are *connected* to one another through **links**

A **record** <span style="color: green;">collection of fields</span> with each **field** containing a single value only.

The **type** of a record defines which <span style="color: green;">fields the record contains</span>.

>This model has many records, each having 1 **parent** record and **many** children records.
>Check the structure section below $\downarrow$
>This is here so that in *network model*; I can make a comparison.

>[!tip]- What is a Record?
>A record is a collection of fields with each field containing a single value.

>[!tip]- What is a Type?
>A type of a record defines which fields the record contains.

#### Use Cases of Hierarchical Model

- Management of Teams, Departments and Employees
- Storing Geographic Information

>Amazon also uses the hierarchical model

#### Structure of Hierarchical Model

"*Here lies a diagram... to fucking show you how it looks like obviously*"

![[Hierarchical Database Model.png | 600]]

---

### Network Model

Database model formed to represent objects and their relationships as a flexible way. Its "*main*" feature is that the schema, viewed as a **graph** in which **object** types nodes ( *basically entities* ) are relationship types are arcs, is not restricted to being a hierarchy or lattice.

Compared to *hierarchical model*; **network** models have **multiple** *parent* and *child* records

#### Use Cases of Network Model

- Oracle CODASYL DBMS
- Integrated Data Store ( IDS )
- Integrated Database Management Systems ( IDMS )

#### Structure of Network Model

I think you get the point of what will come after this text...

![[Network Database Model.png | 600]]

---

# Socials

- [**Instagram**](https://www.instagram.com/s.sunhaloo/)
- [**YouTube**](https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg)
- [**GitHub**](https://www.github.com/Sunhaloo)

---

S.Sunhaloo
Thank You!