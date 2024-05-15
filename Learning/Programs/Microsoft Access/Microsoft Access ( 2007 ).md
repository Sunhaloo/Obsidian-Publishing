---
Alias: MS Access Database
Tag: uni, db
Author: S.Sunhaloo
Date: 2024-05-08
Status: In-Progress
---

<p align="center">Introduction to Databases<br>Lab 1<br>BCNS1103C / DBT1103C<br>SUNHALOO Shehzaad</p>

<br>

<p align="center">University of Technology, Mauritius</p>

## List of Contents

- [[Microsoft Access ( 2007 )#Create a New Database File | Create a New Database File]]
- [[Microsoft Access ( 2007 )#Switching Views | Switching Views]]
- [[Microsoft Access ( 2007 )#Adding Data into Table | Adding Data into Table]]
- [[Microsoft Access ( 2007 )#Primary Key | Primary Key]]
- [[Microsoft Access ( 2007 )#Default Values, Field Validation Rules & Validation Text | Default Values, Field Validation Rules & Validation Text]]
- [[Microsoft Access ( 2007 )#Relationships | Relationships]]
- [[Microsoft Access ( 2007 )#Delete Relationships | Delete Relationships]]
- [[Microsoft Access ( 2007 )#Delete Tables | Delete Tables]]
- [[Microsoft Access ( 2007 )#Referential Integrity | Referential Integrity]]

---

## My Links

- [[Microsoft Access ( 2007 )#Socials | Link to Socials]]

---

>[!warning]
>This is part of an assignment given by our lecturer. Hence, this file can be related to [[University Data View#Database Folder | Database Design]] $\rightarrow$ Spring Double Glazing Company.
>Because I would have never learned MS Access and would have gone straight to **mySQL** or **Oracle**.

>[!note]-
>I am using Microsoft Access 2007.
>But should be the same for everything

>[!info]
>Access is a **[[Overview of Database Management System#Relational Model | Relational]] Database Management System ( RDBMS or RDMS )**.
>This means that; all the data is organised into **two-dimensional** ( *2D-Relation* ) tables.
>---
>Rows $\Rightarrow$ Data Records / Records
>Columns $\Rightarrow$ Data Fields / Fields

# Create a New Database File

I think you know how to do that without any tutorial or anything, right? ( *I fucking hope so* ).

>The file extension for Micro-soft ( *get it... micro soft* ) Access is: `.accdb`

After clicking the <button>Create</button> button. You will be dropped straight into a table ( *Table 1* ) with the **Datasheet View**.

There are 2 types of views:

1. Datasheet View $\Rightarrow$ Looks like an Excel Sheet!
	- Normally used to add data into the table
2. Design View
	- Normally used to create the table ( *fields, data types of fields, etc* )

# Switching Views

To switch to the "**Design View**"; just **right**-click on the table in the *Navigation Pane* and select *Design View*.

This will prompt you to save the **table** ( *not the whole database, but that current table* ). Name that table `tblCustomer`

>[!tip]- Naming Conventions
>Similar to programming, make sure that you "*variables*" names are **meaningful**
>In addition, if you need to write for example `Spare Parts` just write it like you would in programming: `spare_parts`.
>For Example
>- If you are creating a Table
>	- use the prefix `tbl` and then put the actual name of the table
>- For Queries
>	- Use the prefix `qry`
>- For Forms
>	- Use the prefix `frm`
>- For Reports
>	- Use the prefix `rpt`

>Please Check the "Naming Conventions" above $\uparrow$.

# Adding Data into Table

Now we can easily start adding data to the table.

Add these following data:

<p align="center"><strong>Table:</strong> tblCustomer</p>

| Fields | Data Type | Field Size |
| ------ | --------- | ---------- |
| Customer_ID | Autonumber | - |
| Surname | Text | 30 |
| Name | Text | 30 |
| FirstName | Text | 30 |
| Address 1 | Text | 30 |
| Address 2 | Text | 30 |
| Address 3 | Text | 30 |
| Address 4 | Text | 30 |
| Phone | Text | 15 |
| PostCode | Text | 8 |

>[!note]
>An **AutoNumber** field automatically enters a unique number as each record.

It should look something like this:

![[MS Access Design View.png | 700]]

## Primary Key

### What is a Primary Key

We know that it is a unique field identifier ( *given to us in HSC* ).

A Primary Key **must** be:

- Not Null: Primary Key should always have a value
- Stable: Should / Does NOT change once entered
- Unique: Value should uniquely identify the record

### Set Primary Key in MS Access

We just need to simple **right**-click on the *field* that want to make primary key and then click on `Primary Key`.

>A little golden key will appear next to the "*selected*" field!

---

>[!warning]
>As I said in the beginning; this Markdown Document is part of my Lecture assignment; hence I will be using this "*task*" given to us as an example.

## Create More Tables

<p align="center"><strong>Table:</strong> tblStock</p>

| Fields | Data Type | Field Size |
| ------ | --------- | ---------- |
| Stock_ID | Autonumber | - |
| Description | Text | 50 |
| Selling Price | Currency | - |

> Set `Stock_ID` as Primary Key

<p align="center"><strong>Table:</strong> tblOrder</p>

| Fields | Data Type | Field Size |
| ------ | --------- | ---------- |
| Order_ID | Autonumber | - |
| Customer_ID | Number | Long Integer |
| Order Date | Date/Time | - |
| PaymentMethod | Text | 1 |

> Set `Order_ID` as Primary Key

We can see that in this case; `Customer_ID` can be called a **Foreign Key**

<p align="center"><strong>Table:</strong> tblOrderLine</p>

| Fields | Data Type | Field Size |
| ------ | --------- | ---------- |
| OrderLine_ID | Autonumber | - |
| Order_ID | Number | Long Integer |
| Stock_ID | Number | Long Integer |
| Quantity | Number | Byte |

---

# Default Values, Field Validation Rules & Validation Text

>[!tip] Data should be **validated** before it get *stored*!

## Default Values

This is like when you are entering some information; it will automatically enter a *default value*.

For example you are booking an airline ticket and they have a section called "*Today's Date*" to fill. Instead of you needing to fill that section, it will **automatically** input that data for you.

## Validation in MS Access

>Remember Validation and Verification in HSC
>This is him now!

Validation can be achieved through:

- Table Design
- Form Design
- Coding
- Lookup Tables

Validation should happen at the **first** level $\Rightarrow$ In MS Access this means that it is better to include the validation as part of the **table** design rather than relying on *entry validation* at **form** level.

Below $\downarrow$ you can take a look what it looks like:

![[MS Access Default, Validation Rule and Text.png | 700]]

---

# Relationships

In HSC, we learnt about the ERD ( *Entity Relationship Diagram* ) Diagram; where we had to draw *fields* connecting to other *fields* and see how they where **related**.

## Types of Relationships ( *learned in HSC* )

1. One to One ( 1:1 )
2. Many to One ( m:1 ) OR One to Many ( 1:m )
3. Many to Many ( m:n )

>Now we are going to learn how to actually do these things in Linux... WTF am I saying... In MS Access.
>I like Linux; I am sorry, I <span style="color: pink;">LOVE</span> Linux! But here I am on Windows using MS Access... WWWWHHHHHYYYYY!

## Setup Relationships in MS Access

In MS Access, *table* **relationships** are setup in the "**Relationships Window**". In the 2007 version of Access. You just need to find `Database Tools` in the Ribbon Menu and you are going to see a button named <button>Relationships</button>.

### Steps

>[Here](https://www.youtube.com/watch?v=DlGEECPru3E) is a good video on how to setup Relationships

1. Close all / any of the **Tables** you have opened
	- We cannot implement relationships while **Tables** are opened!
2. Switch to "*Database Window*" by pressing the `F11` Key
3. Find the <button>Relationships</button> button ( *check above $\uparrow$* )
4. "*Show Tables*" Menu $\Rightarrow$ Add the tables you want to relate
	- If you did **not** setup any relationships, the "*Show Tables*" menu will automatically pop up.
	- If the "*Show Tables*" menu does not pop up; you can easily find the button <button>Show Table</button> in the Ribbon Menu.
5. Drag the **field** that you to to relate from one table to related *field* in the other table.
	>[!note]- In this Case
	>We have:
	>- Each customer may place many orders
	>- Each order may have many order lines
	>- Each order line is for a particular item of stock
6. In most cases; you will only drag the **primary key** of one table to another's table **foreign key**.
	```mermaid
	graph LR
	A[Primary Key] --->| to | B[Foreign Key]
	```
7. Then after connecting it; a new menu will appear.
	![[Edit Relationships Menu.png | 340]]
	- Please $\checkmark$ on
		1. Choose Enforce Referential Integrity
		2. Choose both Cascade *option*
	- Click on the big ass <button>Create</button> button
8. Repeat Steps `5` to `7`

>What is a Foreign Key?
>In HSC, we learnt that a **Foreign Key** is a key that is a *Primary Key* in another Table.

## Delete Relationships

Just simply click on the connecting arrow and press `Del` on the keyboard!

## Delete Tables

Sometimes you might accidentally add the **same** Table twice.

- If the table does not have any relationships; then just **right**-click on the table, an option called `Hide Table` will appear
- If the table **has** a / many relationships;
	- We need to first, delete the relationships and then
	- Proceed to `Hide Table`

---

# Referential Integrity

## What is Referential Integrity?

>Source: https://www.ibm.com/docs/en/informix-servers/14.10?topic=integrity-referential

It refers to the relationships between **Tables**. As you know, every table in a *database* has a **primary key**. If you are going to link ( *add relationships* ) with / to other tables in that database. The primary key in one table can / must become a **foreign key** in another.

>This was also explained above $\uparrow$

When you **delete** a row that contains a *primary key* or **update** it with a different primary key. You essentially *destroy* the **meaning** of any rows that contain that value as a **foreign key**. Referential Integrity is the logical dependency of a foreign key on a primary key.

>[!tip]- Definition Given By Lecturer
>System of rules to ensure that relationships between records in related tables are valid.
>Hence, the user cannot accidently change, update or delete any data.

### Rules of Referential Integrity

- Cannot enter a value in the foreign key field of the related table that does not exist in the primary key of the primary table
	>You cannot add something ( *data* ) that does not exists in the primary table.
- You cannot delete a record from a primary table if matching records exists in related table
	>You cannot delete something in the primary table that also exists in another table.

>[!info]
>Hence, that is why we have $\checkmark$ the  `Enforce Referential Integrity` check box
>- Prevents us from breaking these rules mentioned above $\uparrow$; else a warning / error message will appear
>This option can be **over-written** by checking $\checkmark$ `Cascade Updated Related Fields` and `Cascade Delete Related Records`
>- When `Cascade Updated Related Fields` are $\checkmark \ \Rightarrow$ changing a *primary key* **value** in the **primary** table will automatically update the matching values in all related records
>- When `Cascade Delete Related Records` are $\checkmark \ \Rightarrow$ deleting a **record** in *primary table* **deletes** any related records in the related table.

---

# Socials

- [**Instagram**](https://www.instagram.com/s.sunhaloo/)
- [**YouTube**](https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg)
- [**GitHub**](https://www.github.com/Sunhaloo)

---

S.Sunhaloo
Thank You!