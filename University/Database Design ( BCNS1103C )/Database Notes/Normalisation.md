---
Alias: Database Design ( Normalisation ) - Week 6
Tag: uni, db
Module: BCNS1103C / DBT1103C
Author: S.Sunhaloo
Date: 2024-07-07
Status: Completed
---

## List of Contents

- [[Normalisation#Anomalies | Anomalies]]
	- [[Normalisation#Types of Anomalies | Types of Anomalies]]
		- [[Normalisation#Insertion Anomaly | Insertion Anomaly]]
		- [[Normalisation#Deletion Anomaly | Deletion Anomaly]]
		- [[Normalisation#Modification Anomaly | Modification / Update Anomaly]]
	- [[Normalisation#Why Avoid Anomalies? | Why Avoid Anomalies?]]

---

- [[Normalisation#Normalisation | Normalisation]]
	- [[Normalisation#Un-normalised Table | Un-normalised Table]]
	- [[Normalisation#What is Normalisation? | What is Normalisation?]]
	- [[Normalisation#Steps in Normalisation | Steps in Normalisation]]
		- [[Normalisation#First Normal Form ( 1-NF ) | First Normal Form ( 1-NF )]]
			- [[Normalisation#My Way of Seeing this Table ( 1-NF ) | My Understanding of First Normal Form ( from Example )]]
		- [[Normalisation#Second Normal Form ( 2-NF ) | Second Normal Form ( 2-NF )]]
			- [[Normalisation#My Way of Seeing this Table ( 2-NF ) | My Understanding of Second Normal Form ( from Example )]]
		- [[Normalisation#Third Normal Form ( 3-NF ) | Third Normal Form ( 3-NF )]]

---

### My Links

- [[Normalisation#Socials| Link to Socials]]

---

>[!warning]
>These normalisation note is related with [[Functional Dependency]].
>The lecturer showed us Normalisation first then we did the Functional Dependency... But I think that you cannot do one before / after the other as you need to understand functional dependency to understand normalisation and vice versa.

>When the lecturer is referring to "*Well Structured Relations*" $\Rightarrow$ A **table** that is designed to minimise *redundancy* and avoid various types of *anomalies*

# Anomalies

>[!tip]- Definition of Anomaly
>>I know in general what an Anomaly is BTW... Something that is out of the normal. But let's go find out the real definition!
>- Something that deviates from what is standard, normal, or expected

>[!note] When can Anomalies Occur?
>When data is:
>- inserted
>- updated
>- deleted
>
>>Basically, when there is a **manipulation** of *data*!

## Types of Anomalies

>This might be connected to [[Entity Relationship Diagram ( ERD ) and Relationships#Relationships | Relationships]].

### Insertion Anomaly

Insertion Anomalies occurs when certain data **cannot** be *inserted* into the database **without** the presence of other unrelated data.

#### Example: Insertion Anomaly

Suppose that you have a table that records `Student` *enrolment* in `Courses`.
If the table *structure* **forces** you to enter `Course` details even when a student is <span style="color: red;">not</span> enrolled in any `Course` yet.

This $\uparrow$ could be said that its an **Insertion Anomaly**.

>[!tip] Insertion Anomaly Avoided By
>Creating **separate** tables for `Students` and `Courses`.
>Then, we create a link with a relationship table.

### Deletion Anomaly

It occurs when deleting <span style="color: red;">a</span> **row** causes unintended loss of data that you would need for future transactions.

#### Example: Deletion Anomaly

Continuing from the example above $\uparrow$. If you delete a `Student` record from a table that also contains `Course` enrolment, you might lose the `Course` details as well.

Take a look at this table below $\downarrow$:

| Student | Course |
| ------- | ------ |
| Linus Sebastien | Computer Science |
| Linus Tarvolds | Computer Science | 
| Ramllal Akhil | Maths |
| Richard Dick | Psychology |
| Richard Dick | Accounting |
| Hardik Harshit | Psychology |

If we remove "*Ramllal Akhil*" we are also going to **lose** *Maths*.
This is because only 1 student is enrolled in Maths!

>[!tip] Deletion Anomaly Avoided By
>Separate the **data** into different tables so that deleting student record does not remove course information.

>[!info]- Its a real fucking name ( *Harshit Jain* )
>![[Real Name - Harshit.png]]
>Link: https://www.quora.com/Whats-it-like-to-have-a-swear-word-in-your-name
>Look at him!

### Modification Anomaly

Modification ( *or update* ) Anomaly occurs when **changes** to data in 1 row require changes to be made in other rows because of *data duplication*.

#### Example: Modification Anomaly

Taking my example from above $\updownarrow$:

| Student | Course | Address |
| ------- | ------ | ------- |
| Linus Sebastien | Computer Science | A |
| Linus Tarvolds | Computer Science | B |
| Ramllal Akhil | Maths | C |
| Richard Dick | Psychology | D |
| Richard Dick | Accounting | D |
| Hardik Harshit | Psychology | E |

Let's say that Mr Richard Dick will now live at "*F*". We will now also have to replace all the other places where there is the row / `Student` *Richard Dick*.

>[!tip] Modification Anomaly Avoided By
>Just normalise the fucking table!
>Normalisation ensures that each piece of data is stored only **once**, eliminating the need to update multiple records.

## Why Avoid Anomalies?

- Data Integrity
	- Anomalies leads to inconsistencies and inaccuracies in data; compromises the reliability of the database
- Efficiency
	- It make it more efficient, takes up less space on disks and retrieval operations will be faster ( *obviously as you have less data to skim through* )
- Maintenance
	- It will be easier to maintain and less prone to errors during data operations.

## How to Avoid Anomalies?

>Again, **Normalise** the shit of out it!

>[!tip] ChatGPT's Definition of Normalisation
>Process of organising the fields and tables of a relational database to minimize redundancy and dependency.
>Normal forms (1NF, 2NF, 3NF, etc.) provide guidelines for this organization.

>[!tip]- Fuck the Lecturer's Notes
>This is what this note ( *that slide* ) looks like:
>![[Ajit's Shitty Note - Slide: Anomalies in Database.png | 300]]
>And this is what [ChatGPT](https://chat.openai.com) gave me:
>![[ChatGPT Note: Anomalies in Database.png | 100]]
>>God Bless You OpenAI

---

# Normalisation

## Un-normalised Table

Look at the table below $\downarrow$:

![[Un-normalised Table Example.png]]

Do you notice something wrong in the above $\uparrow$ table? Is there something wrong in the above table?

Yes, yes there is something wrong it the above table.
**There are repeating groups of attributes** $\Rightarrow$ `Name` field has duplicate attributes, i.e, *Susan Martin*, *Margaret Simpson* and *Chris Lucero* appears **twice**.
In addition to `Name` appearing twice, we also have `Dept_Name` appearing twice as that values are connected with `Name`

>Hence, we need to find a way, to break down the database table into other tables that are *atomic*

### Other Reason Why Table is Un-normalised

1. Data Duplication and Data Redundancy
2. No cascading `UPDATE`, `DELETE`

## What is Normalisation?

>[!tip]- Definition
>It is the process used to **organise** data to **reduce** data *redundancy* and **improve** data *[[Data Integrity | integrity]]*.

>[!tip] Teacher's Definition
>Process of removing duplicated data and enforce integrity in a database ( table ).
>
>>[!info] Teacher's Notes
>>- Process for deciding which attributes should be grouped together in a relation.
>>- Use common-sense during conceptual data modelling to group attributes into entity types
>>- It is a primary tool to validate and improve logical design
>>
>>$\Rightarrow$ Normalisation is the process of decomposing relations with anomalies to produce smaller, well structured relations.

## Steps in Normalisation

### First Normal Form ( 1-NF )

>[!tip]- Definition
>A table is in *First Normal Form* if each column ( *field* ) contains **only** *single* values and the tables does **not** have any repeating groups ( *of attributes* )

>[!tip] Teacher's Definition
>A relation is in 1-NF **if and only if** every non-key attribute if functionally **dependent** upon the primary key.

Take a look at this picture below $\downarrow$:

![[1-NF: Not Fully Dependent of Primary Key Example.png | 600]]

This is an example of where our *attributes* are <span style="color: red;"><strong>not</strong></span> dependent on our Primary Key.

#### My Way of Seeing this Table ( 1-NF )

![[1-NF: Not Fully Dependent of Primary Key Example.png | 600]]

I think of it in terms of tables... What I mean by that.

Let's take the field `ModuleName`; Every single field needs `ModuleName` but when you take a look at `Staff No` - `Staff Name`, `Student No` - `Student Name` and `Assessment Grade` - `Assessment Type`. You can see that `Staff Name` is **dependent** ( *related* ) on `Staff No`, `Student Name` is *related* to `Student No` and same thing for `Assessment Grade` and `Assessment Type`.

Therefore we need to break down the table so that each gets its now table ( *i.e `tblStaff`, `tblStudent`, `tblClass`* ) and will be *related* with **relationships**.

>Because in this example, we know that the table ( *check the image $\uparrow$* ) is **not** normalised.
>Hence, we are going to break down the *fields* ( *i.e `Staff No`, `Student Name` and so on* ) and make each of them a **separate** table.
>So that the problem of [[Normalisation#Types of Anomalies | Anomalies]] does **not** occur!

>[!info]
>You might be wondering... *Why does a class need to know the `Module Name`*?
>>So you are telling me that a *Business and Management* student will go into a **Physics Laboratory** to learn *Accounting / Laws*
>I think you get the point that I am trying to make.

>[!tip]- What happens in 1-NF ( *the answers* )
>- Removal of multi-valued attributes
>- Removal of duplication of data / Eliminate repeating groups of attribute
>- All non-key attributes ( _i.e fields that are not **primary key**_ ) should be fully dependent on Primary Key
>- There should be no *partial dependency* $\downarrow$ ( *as the lecturer called it "part-key"* )
>
>>The lecturer said to ask the question "*Can the data item be uniquely identified by part of the compound key*"
>
>>[!note]
>>**Composite Primary Key** is when you take 2 fields and make them ( *both* ) uniquely identify all of the other attributes / fields in the table
>>A **composite primary key** can consist of *candidate* keys.
>>- Where a *candidate* key is a potential primary key
>>- Hence, it can uniquely identify a tuple in a table / relation.

>[!tip] Partial Dependency
>For more information about partial dependency; head of over to [[Partial Dependency]]


#### After Applying 1-NF

The table will be broken down into 2 tables when we *apply* 1-NF.

>Therefore we are going to be using [[Entity Relationship Diagram ( ERD ) and Relationships#Relationships | Relationships and Cardinality]] to **link** these tables.

![[1-NF: Non-Key Attributes Dependent on Primary Key ( Applied 1-NF ).png | 600]]

>As you can see, instead of 1 table, we now have:
>- `Modules`
>- `Assessments`
>BTW its not `ass Type` and `ass Grade`; nevertheless, funny mistake

### Second Normal Form ( 2-NF )

>From what I understand what will happen in this section ( *using our examples $\uparrow$* ); we are going to make another table called `Students`.

>[!tip]- Definition
>A table is in *Second Normal Form* if and only if it is in *[[Normalisation#First Normal Form ( 1-NF ) | First Normal Form]]* and all of the non-key attributes are fully functionally *dependent* on **Primary Key**.

![[1-NF: Non-Key Attributes Dependent on Primary Key ( Applied 1-NF ).png | 600]]

Let's go ahead and try to break down `Student No` and `Student Name` from the image / table `Assessment` above $\uparrow$.

Take a look at this image below $\downarrow$:

![[2-NF: Break down of Assessment Table.png | 600]]

>I do not know how to explain this so I am going to include his note also

>[!tip] Teacher's Notes
>- We need all the items of the key to tell us what `Assessment Grade` is
>- `ModuleName` has **no** influence on the `Student Name`
>- `Student No` alone determines `Student Name`
>- Break out the determinant ( *`Student No`* ) and dependent ( *`Student Name`* ) data item into their own tables
>
>>Hence, we are going to create the `Students` table.

#### My Way of Seeing this Table ( 2-NF )

![[2-NF: Break down of Assessment Table.png | 600]]

As I have been saying, the normalisation process means that we are going to *break down* everything until we cannot do anything. For example, here we have:

- `ModuleName`
- `Student No`
- `Assessment Type`
- `Student Name`

But as you / I can see, we can actually make another table ( *in this case `Students` table* ) where we are going to *store* the fields `Student No` and `Student Name`.

>This is because `Student No` can uniquely identify `Student Name`!

>[!tip]- What happens in 2-NF ( *the answers* )
>- Table must already be in [[Normalisation#First Normal Form ( 1-NF ) | First Normal Form]] ( *$\Rightarrow$ carry all the steps in First Normal Form* )
>- Removal of partial dependencies

#### After Applying 2-NF

![[2-NF: Break down of Assessment Table ( Applied 2-NF ).png | 600]]

As you can see the table `Students` have been created and then the field `Student No` becomes a *foreign key* in the table `Assessments`.

### Third Normal Form ( 3-NF )

>Again, we are going to break the table down *more*... We are still going to be using the examples from above $\uparrow$.

>[!tip]- Definition
>A table is in *Third Normal Form* if it is in *[[Normalisation#Second Normal Form ( 2-NF ) | Second Normal Form]]* and all of its non-key attributes are **not only dependent** on the **Primary Key** but also *independent* of each **other**.

>[!tip] Teacher's Weird Notes
>1. Examine every table and ask each pair of non-key data items ( *$\leftarrow$ English thrown out of the window* )
>	- Is the value of field '*A*'dependent on the value of field '*B*', or vice versa?
>	- If answer is "YES", then split off the relevant data items into a separate table
>2. A relation in Third Normal Form if and only if it is in Second Normal Form and every non-key attribute is non-transitively dependent on the primary key.

#### Example from ChatGPT

Check this table out $\downarrow$:

>This table will not contain any values its just for explanation sake.

| StudentID | StudentName | CourseID | CourseName | InstructorName |
| --------- | ----------- | -------- | ---------- | -------------- |

As you can see, `StudentName` is **dependent** on `StudentID`; similarly `CourseName` and `InstructorName` is **dependent** on `CourseID`.

>This means that we have <span style="color: red;">Transitive Dependencies</span>!

Thus, we need to break down in this way $\downarrow$:

- Students Table

| StudentID | StudentName |
| --------- | ----------- |

- Courses Table

| CourseID | CourseName | InstructorName |
| -------- | ---------- | -------------- |


- Enrollments Table

| StudentID | CourseID |
| --------- | -------- |

As you can see we have created another table. In this way each non-key attribute is **directly** dependent only on the **Primary Key** of its *own* table, **eliminating** *transitive dependencies* and ensuring that the structure of the table adheres to Third Normal Form.

>I think this is similar to [[Entity Relationship Diagram ( ERD ) and Relationships#Associative Entity | Associative Entities]]

>[!tip]- What happens in 3-NF ( *the answers* )
>Table must already be in [[Normalisation#First Normal Form ( 1-NF ) | First Normal Form]] ( *$\Rightarrow$ carry all the steps found in First Normal Form* )
>Table must already be in [[Normalisation#Second Normal Form ( 2-NF ) | Second Normal Form]] ( *$\Rightarrow$ carry all the steps found in Second Normal Form* )
>Removal of Transitive Dependencies

>[!note]- What is Transitive Dependency?
>It occurs when a non-key attribute **depends** on another non-key attribute, which in turn depends on the primary key.
>For Example:
>- `StudentID` is the *Primary Key*
>- `StudentName` **directly** depends on the `StudentID`
>- `CourseID` **directly** depends on the `StudentID`
>- `CourseName` depends on `CourseID`
>
>>I guess this is the explanation on Transitive Dependency... I am not a professional and I feel like I still did not understand a single thing.
>>This is because, it not practical; all theory.
>>Like my father ( *because he applies the theory in practice* ) says "*Pas sa ve dire to comprend li lor papier to pu kapave faire li*"
>>Life is like that... 

---

# Socials

- **Instagram**: https://www.instagram.com/s.sunhaloo
- **YouTube**: https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg
- **GitHub**: https://www.github.com/Sunhaloo

---

S.Sunhaloo
Thank You!