---
Alias: Database Design ( Logical / Phyiscal Data Independence ) - Week 1
Tag: uni, db, utm
Module: BCNS1103C / DBT1103C
Author: S.Sunhaloo
Date: 2024-05-18
Status: Completed
---

## List of Contents

- [[Data Independence#Data Independence | Data Independence]]
	- [[Data Independence#What is Data Independence? | What is Data Independence?]]
		- [[Data Independence#Logical Data Independence | Logical Data Independence]]
		- [[Data Independence#Physical Data Independence | Physical Data Independence]]

---

### My Links

- [[Data Independence#Socials | Link to Social]]

---

# Data Independence

>[!note]
>This part of the notes: "*Data Independence*" is related to the [[ANSI - SPARC Model#Three-Level Architecture | Three-Tier Architecure]].

## What is Data Independence?

It is the type of **data transparency** that matters for a centralised Database Management System.

We know that user *applications* should ideally, **not** be exposed to details of data representation and storage. Hence, data independence provides immunity to the user's applications.

>The DBMS provides such abstraction view of the data and hides such details.

## Logical Data Independence

>Found between External and Conceptual Level

>[!tip]- Definition
>Ability to modify the **logical _( conceptual )_ schema** *without* needing to rewrite the user application / front-end applications.
>
>Change the logical schema without changing the External schema / User / External View / Logical Structure $=$ "*Logical Data Independence*"
>>"*logical schema*"

The *logical structure* of the data is known as the **schema definition**.

The user application operates on a **subset** of *attributes* and *relations*. The application should **not** be affected when new attributes are added to the same relation.

In simpler words: The **logical** data independence ensures that the underlying database structure ( *adding / modifying entities, relationships, constraints* ) do not affect how users or applications view and interact with the data.

---

## Physical Data Independence

>Found between Conceptual and Physical Level

>[!tip]- Definition
>Ability to modify the **physical _( internal )_ schema** *without* needing to rewrite the physical structure / user application
>>"*physical schema*"

The physical structure of the data is referred to "**physical data description**"

Deals with hiding the details of the **storage structure** from the user applications.

In simpler words: It allows for changes in internal schema / physical view ( *reorganising data storage, adding indexes, changing storage devices* ) without requiring changes to the conceptual / logical or external / view schema.

---

# Socials

- [**Instagram**](https://www.instagram.com/s.sunhaloo/)
- [**YouTube**](https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg)
- [**GitHub**](https://www.github.com/Sunhaloo)

---

S.Sunhaloo
Thank You!