---
Alias: Database Systems ( Relational Model ) - Week 2
Tag: uni, db, uom
Module: ICDT 1202Y
Author: S.Sunhaloo
Date: 2024-07-30
Status: Completed
---

## List of Contents

- [[Database Relational Model#Data Models | Data Models]]
- [[Database Relational Model#Categories of Data Models | Categories of Data Models]]
- [[Database Relational Model#Entity Relationship Model | Entity Relationship Model]]
- [[Database Relational Model#Referential Integrity | Referential Integrity]]
- [[Database Relational Model#Database Schema | Database Schema]]
- [[Database Relational Model#Tree Tier Architecture | Three Tier Architecture]]
- [[Database Relational Model#Data Independence | Data Independence]]
- [[Database Relational Model#Overall System Architecture | Overall System Architecture]]
	- [[Database Relational Model#Storage Manager | Storage Manager]]
	- [[Database Relational Model#Query Processor | Query Processor]]

---

### My Links

- [[Database Relational Model#Socials | Link to Socials]]

---

# Data Models

>Please, please and please! Refer to the file / note [[Types of Database Model]] $\leftarrow$
>What I am going to say in here is basically a dumb down version ( *"digestible" version* ) of **my** own notes above $\uparrow$

>[!tip] What is a Data Model?
>It is a collection of high-level description concepts for **describing** data.
>It hides the low-level storage details
>
>>Hence, we can say that it is some type of *abstraction*.
>
>It is a set of concepts to **describe** the *structure* of a database, in addition to *relationships* and *constraints* that the database should obey

>[!tip] What is Schema?
>It is the **description** of a particular *collection of data*, using the given data model.

---

# Categories of Data Models

>In this part of the notes; if you look at the lecture slides. You are going to see that the lecturer is talking about:
>- Conceptual Data Model
>- Physical Data Model
>- Implementation
>
>Apart of from the "*implementation*"; I have **already** made notes on this and I have also drawn out diagrams using Excalidraw... So do yourself a favour and head over to [[Data Modelling - Conceptual - Logical Level Modelling]]
>Don't worry; there is also the *Physical* part there.
>But I am going to write somethings.

>[!tip] What is the "Implementation ( representational )" Data Model?
>It provides concepts that fall between the above 2 ( *meaning Conceptual and Physical* ); balancing user views with some computer storage details.

>Again, head over to [[Types of Database Model]]; to see the *Relational*, *Hierarchical* and *Network* model.
>Go see it; I have made diagrams... by myself like not by myself, but in Excalidraw.

---

I found this cool image showing the definitions of things; check if out $\downarrow$

![[Definitions - Informal and Formal.png | 650]]

---

# Entity Relationship Model

>More like [[Entity Relationship Diagram ( ERD ) and Relationships]]

---

# Referential Integrity

>Sooooo... [[Data Integrity#What is Referential Integrity? | Referential Integrity]].
>That now above that I just mentioned has another link where I explained the Referential Integrity for the first time and that very note which is found in the above $\uparrow$ mentioned link is originally found in [[Microsoft Access ( 2007 )#Referential Integrity | Microsoft Access ( 2007 )]]

---

# Database Schema

>Okay time to write somethings from the [[Database Systems – Relational Model.pdf]]

>[!tip] What is Database Schema?
>>The whole thing!
>
>The **description** of a database.
>This includes the description of the database **structure** and **constraints** that should hold on the database
>This can be represented using *Schema Diagrams*

>[!tip] What is a Schema Diagram?
>A diagrammatic display of a database schema:
>- Includes names of record types and data items of some types of constraints

This is an example of a **Schema Diagram**

![[Database Schema Diagram Example.png | 850]]

>[!tip] What is a Schema Construct?
>A component of the schema or an object within the schema.
>For Example: STUDENT, COURSE

This can be represented like $\downarrow$:

STUDENT

| Name | StudentID | Course |
| ---- | --------- | ------ |

Module

| ModuleName | StudentID | CreditHours | Department |
| ---- | --------- | ------ | ---------- |

Grade-Report

| StudentID | CourseID | Grade |
| --------- | -------- | ----- |

>Just wanted to add this here also; from the file / note [[Database and Flat Files]]

>[!tip] What is Schema Mapping?
>Process of establishing relationships between the elements of 2 different database schemas.

>[!tip] What is a Database Instance / State?
>It is actual **data** stored in a database ( *contents of the database* ) at a particular moment in time.
>For new databases we **no** data; we say that it is in an *empty state*.

>[!tip] What is the Initial Database State?
>Refers to the database when it is loaded with initial data.

>[!tip] What is the Valid State?
>A state that satisfies the structure and constraints of the database.

>[!note]
>- The **Database Schema** changes *very infrequently*
>- The **Database State** changes *every time* that database is **updated**
>
>**Schema** also referred to as *intension* ( Schema $\rightarrow$ Intension )
>**State** also referred to as *extension* ( State $\rightarrow$ Extension )

---

# Two Tier Client Architecture

From what I can understand is that its a bit like a **Client-Server** model.

Where the **Client**:

- Manages the user interfaces and runs the applications

And where the **Server**:

- Holds the database and database management system ( DBMS )

Advantages are:

1. Wider access to existing databases
2. Increased Performance
3. Possible reduction in Hardware Costs
4. Reduction in Communication Costs
5. Increased Consistency

---

# Tree Tier Architecture

>As you know this is kind-of a derivation of the ANSI-SPARC Model... How do I know this.
>[[ANSI - SPARC Model]] $\leftarrow$ You will find most things in there!

---

# Data Independence

>I also have already made some notes for that... Here you go [[Data Independence]]

---

# Overall System Architecture

A database system is partitioned into modules that deal with each of the responsibilities of the system and is broadly divided into the **Storage Manager** and **Query Processor**

Here $\downarrow$ is a little image:

![[Overall Database System Architecture Diagram.jpg | 700]]

## Storage Manager

The Storage Manager provides the interface between the low-level data stored in the database and the app.
Programs and Queries are submitted to the system

- Responsible for interaction with File Manager
- Translates various [[Database Languages#Data Manipulation Language ( DML ) | Database Manipulation Language ( DML )]] statements into low-level file commands ( *hence, I think it can be also called a "Translator" like in programming languages* )
- Responsible for:
	- Storing Data
	- Retrieving Data
	- Updating Data

### Storage Manager Sub-Structures

It also implements several data structures as part of the physical systems implementation. They are:

1. Data Files
	- Stores the data itself
2. Data Dictionary
	- Stores the metadata about the **structure** of the database
3. Indices
	- Provides fast access to data items that hold particular values

## Query Processor

>[!tip] What is the Data Definition Language ( DDL ) Intepreter?
>It interprets DDL statements and records into the definitions in the Data Dictionary.

>[!tip] What is the Data Manipulation Language ( DML ) Compiler?
>Translates DML statements in a query language into an evaluation plan consisting of low-level instructions that query evaluation engine understands.

>[!tip] What is the Query Evaluation Engine?
>It is the one that executes low-level instructions generated by the DML compiler.

---

# Socials

- **Instagram**: https://www.instagram.com/s.sunhaloo
- **YouTube**: https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg
- **GitHub**: https://www.github.com/Sunhaloo

---

S.Sunhaloo
Thank You!