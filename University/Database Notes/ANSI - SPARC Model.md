---
Alias: Tree-Tier Architecture Model
Tag: uni, db
Module: BCNS1103C / DBT1103C
Author: S.Sunhaloo
Date: 2024-05-19
Status: Completed
---

## List of Contents

- [[ANSI - SPARC Model#ANSI / SPARC Architecture | ANSI / SPARC Architecture]]
- [[ANSI - SPARC Model#Three-Level Architecture | Three-Tier Architecture]]
	- [[ANSI - SPARC Model#"Levels" | Levels of Three-Tier Architecture]]
		- [[ANSI - SPARC Model#External Level / View Level | External Level]]
		- [[ANSI - SPARC Model#Conceptual Level / Logical Level | Conceptual Level]]
		- [[ANSI - SPARC Model#Internal Level / Physical Level | Physical Level]]
	- [[ANSI - SPARC Model#Mapping | Mapping]]

---

### My Links

- [[ANSI - SPARC Model#Socials | Link to Social]]

---

# ANSI / SPARC Architecture

>[!tip] ANSI / SPARC
>[American National Standards Institute](https://en.wikipedia.org/wiki/American_National_Standards_Institute) - Standards Planning and Requirements Committee.

## What is the ANSI / SPARC Model?

Abstract design standard for a Database Management System ( DBMS ) first proposed in 1975.

<span style="color: red;">Never</span> became formal standard... No mainstream DBMS system are fully based on it; but the **idea** of [logical data independence](https://en.wikipedia.org/wiki/Data_independence) is **widely** adopted.

## Three-Level Architecture

![[Three-Level Architecture diagram.png | 555]]

The main *objective* of the this $\uparrow$ architecture is to **separate** the user's views

- Allows for independent customised user views
	- Each user should be able to access the **same** data but with *their* **own** view.
	- These should be independent changes to one view should **not** affect others
- Hides physical storage details from users:
	- Users should have not to deal with physical database storage details
- [[Overview of Database Management System 1#Database Administrator ( DBA )| DBA]] should be able to change the database storage structures without affecting user's views
- Internal structure of database should be unaffected by changes to the physical aspects of the storage
	- Moving data to a new disk should **not** affect anything

### "Levels"

>[!note]
>The "*levels*" below are in order!
>Each "*level*" are considered as a layer of [**abstraction**](https://en.wikipedia.org/wiki/Abstraction_(computer_science)).

#### External Level / View Level

This level represents the user **views** ( *external schemas* )

- Defines how the user perceive and interact with the data. Also, provides **customised** views for each user tailored to his specific needs / applications.
- It will **exclude** irrelevant data as well as data that is **not** authorised to access by the user ( *kinda a <span style="color: yellow;">security</span> thing also* )

#### Conceptual Level / Logical Level

Represents the logical outline of the entire database and shows how the data is inter-related.

>[!note]
>It does **<span style="color: red;">not</span>** specify how data is physically stored.
>That comes in the Internal / Physical Level $\downarrow$.

It provides unified and abstract view of the entire database, implementation details or physical storage considerations.

- Defines structure of database
	- Entities
	- Relationships
	- Constraints
	- Integrity Rules

>[!tip]- Important Facts
>1. Only [[Overview of Database Management System 1#Database Administrator ( DBA )| Database Administrator]] who defines and work at this level
>	- But they do work in **other** level; in addition, they work with data modelers and database designers to create the conceptual schema
>2. Describes structure for all users
>3. Offers a global view of whole database
>4. Independent of hardware and software

>[!tip] Database / Data Modelling
>Conceptual / Logical Level is *related* with [[Data Modelling - Conceptual - Logical Level Modelling]] and [[Entity Relationship Diagram ( ERD ) and Relationships]].
>>Please go to these link for more information about them.

#### Internal Level / Physical Level

This level represents the actual physical storage and implementation details of database.

- Defines how data is actually stored, organised and accessed.
	- Hard drives, disks
- Internal schema describes
	- Data structures
	- Storage formats
	- Indexing methods
	- Optimisation techniques

>[!note]
>With this level of *separation*, the DBA can change the database **without** affecting the user's views.

>[!info]- What is a schema?
>The representation of a plan in the form outline / model

### Mapping

It refers to the **connections** and **relationships** made between the 3 different levels / tiers; i.e *external, logical, internal*

- Defines how the data and functionality flows between these levels.

---

# Socials

- [**Instagram**](https://www.instagram.com/s.sunhaloo/)
- [**YouTube**](https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg)
- [**GitHub**](https://www.github.com/Sunhaloo)

---

S.Sunhaloo
Thank You!