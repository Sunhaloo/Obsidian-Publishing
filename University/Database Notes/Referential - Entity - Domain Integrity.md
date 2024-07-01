---
Alias: Database Design ( Referential / Entity Integrity ) - Week 2
Tag: uni, db
Module: BCNS1103C / DBT1103C
Author: S.Sunhaloo
Date: 2024-05-26
Status: Completed
---

## List of Contents

- [[Referential - Entity - Domain Integrity#What is Referential Integrity?| What is Referential Integrity?]]
- [[Referential - Entity - Domain Integrity#What is Entity Integrity?| What is Entity Integrity?]]
- [[Referential - Entity - Domain Integrity#What is Domain Integrity? | What is Domain Integrity?]]

---

### My Links

- [[Referential - Entity - Domain Integrity#Socials| Link to Social]]

---

# What is Referential Integrity?

>I have already made notes for this $\uparrow$ in [[Microsoft Access ( 2007 )]] note.
>I will just be linking the file

![[Microsoft Access ( 2007 )#Referential Integrity]]

>[!note] Summary
>In short, *Referential Integrity* is a system of rules that ensure relationships between **tables** and **records** are <span style="color: green;">valid</span>.
>To do that, we need to have our Primary and Foreign key!
>Because it is the [[ANSI - SPARC Model#Conceptual Level / Logical Level | logical]] dependency of a **foreign** key on a **primary** key.

# What is Entity Integrity?

**Entity Integrity** is concerned with ensuring that all the rows of a table has a unique key identifier; and what / who is the unique record / key identifier... ( *drum roll* ) The **Primary Key**!!!

>Each row in a table *represents* a single **instance** of the entity type modelled by the table.

The [[Types of Database Model#Relational Model | relational model]] states that every relation ( *Degree of Relation* ) / table **must** have an identifier; The Primary Key.
Hence, now every row of the same relation be identifiable by its contents, i.e, by a unique and minimal value.

# What is Domain Integrity?

It is a concept in [[Database Management System ( DBMS )]] that ensures the **accuracy**, **consistency**, and **validity** of *data* within in a database.
Set of rules and constraints applied to the values of a particular column / attribute in a database table.

>[!tip] Teacher's Notes
>Concerned with the values that may be contained within a particular attribute column
>Domain integrity rules states that:
>	"*Every attribute is required to satisfy the constraint that its values are drawn from the relevant domain*"

>[!note]
>My shitty notes from his notes
>
>---
>Lets say that you have 2 attributes / columns; `Salary` and `Mobile` each can have a maximum characters of 7 digits
>Even if both are "*numeric*" and each "*7*" digits. They have different **domain**
>That is, they have distinct ( *different* ) operations that can be performed on them ( *queries*, *calculations* )

---

# Socials

- [**Instagram**](https://www.instagram.com/s.sunhaloo/)
- [**YouTube**](https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg)
- [**GitHub**](https://www.github.com/Sunhaloo)

---

S.Sunhaloo
Thank You!