---
Alias: Database Design ( Data Modelling ) - Week 1
Tag: uni, db
Module: BCNS1103C / DBT1103C
Author: S.Sunhaloo
Date: 2024-05-18
Status: Completed
---

## List of Contents

- [[Data Modelling - Conceptual - Logical Level Modelling#Data Modelling| Data Modelling]]
- [[Data Modelling - Conceptual - Logical Level Modelling#Database Design| Database Design]]

---

### My Links

- [[Data Modelling - Conceptual - Logical Level Modelling#Socials| Link to Social]]

---

# Data Modelling

What is Data Modelling?

This forms parts of the **conceptual** ( *logical* ) design process.

It is the first step in the database development process; involves:
	- Collection of Information
	- Analysing those data / information gathered
	- Diagramming / Entity Relationship Diagram

>We have Data Model but we also have [*Function Model*](https://en.wikipedia.org/wiki/Function_model#:~:text=In%20systems%20engineering%2C%20software%20engineering,modeled%20system%20or%20subject%20area.)

The [data model](https://en.wikipedia.org/wiki/Data_model) focuses on *what* data should be **stored** in the database while the function model deals with how data should be processed.

>[!info] Summary
>- Data Model $\rightarrow$  Deals with how data is **stored**
>	- Used to Design Relational Databases
>- Functional Model $\rightarrow$ Deals with how data is being **processed**
>	- Used to Design Queries ( which access and perform operations on those tables )

# Database Design

There are 4 stages / steps to design a database.

1. Requirements Collection and Analysis
2. Conceptual Design
3. Logical Design
4. Physical Design

Below $\downarrow$ you are going to find more about each of these *stages*.

## Requirements Collection and Analysis

First stage / phase of designing a database ( *of any software* ).
It involves:

- Identifying user groups
- Analysing processing needs
- Collecting requirements

through **interviews** and **documentation** reviews to understand how the database will be used.

>[Here](https://online.visual-paradigm.com/knowledge/visual-modeling/conceptual-vs-logical-vs-physical-data-model#:~:text=The%20conceptual%20model%20is%20to,set%20the%20relationships%20between%20them.) is a website talking about Conceptual and Logical Data Modelling

### Data Analysis

- Provides a way of structuring data, testing its uses before detailed design
- Removing inconsistencies
- Planning confidentiality and validity control
- Relationships between data items ( *entities* ) are established as part of data analysis

## Conceptual Design

>[!tip] Teacher's Notes
>- Form a concise description of the data requirements using a high-level data model.
>- This description will be independent of storage requirements
>>Does "*storage*" here means the *[[ANSI - SPARC Model#Internal Level / Physical Level | Phyiscal Level]]*?
>
>Includes the **identification** of important *entities*, *relationships* and *attributes*.

>[!tip]- What is the Conceptual Model?
>- It is to establish the entities, their attributes and relationships.

>[!info]
>We **can** draw many-to-many ( `m:n` ) relationships in *Conceptual* [[Entity Relationship Diagram ( ERD ) and Relationships#What is an Entity Relationship Diagram? | ERD]].

## Logical Design

>[!tip] Teacher's Notes
>Any good conceptual design techniques will specify the mapping from conceptual model to variety of implementation models.
>**Translates** *conceptual* representation $\rightarrow$ the *logical* structure of the database which includes designing the **relations**.

>[!tip]- What is Logical Model?
>It defines the **structure** of data elements and set **relationships** between them.

>[!info]
>We **cannot** draw many-to-many ( `m:n` ) relationships in *Conceptual* ERD!

## Physical Design

>[!tip] Teacher's Notes
>Some database systems allow the [[Database Administrator]] to make decisions about physical storage.
>These are driven by performance considerations
>- Decides how the logical structure is to be **physically** implemented ( *as relations* ) in the target [[Database Management System ( DBMS )]].

>[!tip]- What is Physical Model?
>It describes the database-specific implementation of the data model

![[Database Modelling - Database Process.png | 500]]

---

# Socials

- [**Instagram**](https://www.instagram.com/s.sunhaloo/)
- [**YouTube**](https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg)
- [**GitHub**](https://www.github.com/Sunhaloo)

---

S.Sunhaloo
Thank You!