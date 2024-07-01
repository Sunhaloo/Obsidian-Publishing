---
Alias: Database Design ERD - Week 1
Tag: uni, db
Module: BCNS1103C / DBT1103C
Author: S.Sunhaloo
Date: 2024-05-19
Status: Completed
---

## List of Contents

- [[Entity Relationship Diagram ( ERD ) and Relationships#Definitions | Definitions]]
- [[Entity Relationship Diagram ( ERD ) and Relationships#What is an Entity? | What is an Entity?]]
	- [[Entity Relationship Diagram ( ERD ) and Relationships#Types of Entities | Types of Entities]]
- [[Entity Relationship Diagram ( ERD ) and Relationships#What is an *Instance* of an Entity? | What is an Instance of an Entity?]]
	- [[Entity Relationship Diagram ( ERD ) and Relationships#Example Entity - Instances | Example]]
	- [[Entity Relationship Diagram ( ERD ) and Relationships#Check if Entity / Instance | Check if Entity / Instance]]
- [[Entity Relationship Diagram ( ERD ) and Relationships#What is an Attribute? | What is an Attribute?]]
	- [[Entity Relationship Diagram ( ERD ) and Relationships#Types of Attributes | Types of Attributes]]
- [[Entity Relationship Diagram ( ERD ) and Relationships#What is an Entity Relationship Diagram? | What is an Entity Relationship Diagram?]]
	- [[Entity Relationship Diagram ( ERD ) and Relationships#Basic E-R Notation | Basic E-R Notation]]
	- [[Entity Relationship Diagram ( ERD ) and Relationships#Sample E-R Diagram | Sample E-R Diagram]]
- [[Entity Relationship Diagram ( ERD ) and Relationships#Relationships | Relationships]]
	- [[Entity Relationship Diagram ( ERD ) and Relationships#Cardinality / Relationship | Cardinality / Relationships]]
- [[Entity Relationship Diagram ( ERD ) and Relationships#Degree of Relationships | Degree of Relationships]]
	- [[Entity Relationship Diagram ( ERD ) and Relationships#Types of Degree | Types of Degree]]
- [[Entity Relationship Diagram ( ERD ) and Relationships#Constraints and Assumptions | Constraints and Assumptions]]
- [[Entity Relationship Diagram ( ERD ) and Relationships#Constructing an ER Model | Summary on Construction of ERD]]

---

### My Links

- [[Entity Relationship Diagram ( ERD ) and Relationships#Socials| Link to Social]]

---

# Definitions

>[!tip]- Definition
>- Entity:
>	- Concept to abstractly represent all instances of a group of similar "*objects*"
>		- Anything about which data are to be recorded and stored
>	- Can be a real-world object, either animate or inanimate, that can be easily identifiable
>		- Example:
>			- Computer Part
>			- Person
>			- Car
>- Entity Type:
>	- Collection of entities having similar **attributes**
>- Entity Instance:
>	- It is a single occurrence of **an** entity.
>- Attribute:
>	- Characteristic / trait of an entity type that describe the entity
>		- Example:
>			- Computer_ID
>			- Name
>			- Chassis Number
>	- Type of Attributes
>		- Volatile Attributes
>			- Values that are constantly changing
>		- Non-Volatile Attributes
>			- Values that rarely ( *if ever* ) change.
>		- Mandatory Attributes
>			- The attribute needs to exists
>- Instance of an Entity
>	- Single occurrence of an entity
>- Degree of Relationships
>	- Number of entity types that are associated with a relationship
>	- Type of Degree
>		- Unary
>		- Binary
>		- Ternary
>		- N-ary $\rightarrow$ consist of many "*degree*"

# What is an Entity?

>[!tip]- Definition
>Concept to abstractly represent all instances of a group of similar "*objects*"

Examples of Entities:

1. Person
2. Customer
3. Car

>Anything that is an object can be considered as an Entity

>[!tip] Teacher's Definition
>Anything about which data are to be collected and stored
>An entity is:
>- "*Something*" of significance to the business about which data must be known
>- A name for a set of similar things that you can list
>	- Usually a **noun**
>	- Have [[Entity Relationship Diagram ( ERD ) and Relationships#What is an *Instance* of an Entity? | instances]]

## Types of Entities

- Strong Entity
- Weak Entity
- Associative Entity

### Strong Entity

Entity that is **not** *dependent* on any other entity.
Meaning, other entities will / can related to this *main* entity.
It has a **primary key** that can uniquely identify each instance of the entity.

#### Example of Strong Entity

- Customer, Product, Employee

### Weak Entity

>This is the opposite of *Strong* entity... *yeah, that's why its called "weak" instead of "strong"*, duh!

It is an entity that is dependent on other entities; cannot uniquely be identified on its own.
It relies on **foreign key** from parent entity combined with its own partial key to uniquely identify its instances.

>[!info]- What is a Partial Key?
>Set of **attributes** ( columns ) that can uniquely identify a subset of records within a table but **not** on its *own*.

#### Example of Strong Entity

- `OrderItem` ( Weak ) and `Order`
- `DogOwner` ( Weak ) and `Dog`

### Associative Entity

>[!note]
>Used in **[[Data Modelling - Conceptual - Logical Level Modelling#Logical Design| Logical]]** ERD! $\Rightarrow$ Cannot implement `m:n` relationships in **logical** ERD!

It is an association between two fundamental entities that has a potential of being a `many-to-many` cardinality or that holds some attributes.

>[!info] When should a *relationship with Attributes* instead be an associative entity?
>>In other words, when should you use an *Associative Entity*
>- All relationships for the associative entity should be **many**
>- The associative entity preferably has a unique identifier, and should also have other attributes
>- The associative may be participating in other relationships other than the entities of the associated relationship.
>- Ternary relationships should be converted to associative entities.
>>[!note]
>>For more information about "*participating*" and Ternary relationships head over to [[Entity Relationship Diagram ( ERD ) and Relationships#Degree of Relationships | Degree of Relationships]] down below $\downarrow$

# What is an *Instance* of an Entity?

>[!tip] Definition ( *Stack Overflow* $=$ *Teacher's Definition* )
>It is a **single** occurrence of an *entity*.

## Example: Entity - Instances

| Entity | Instances |
| ------ | --------- |
| CAR | Mazda RX-7, GTR-R32 |
| PLANE | Boeing F/A-18, Lockheed SR-71 Blackbird |
| JOB | Software Engineer, Linux Kernel Developer |
| ANIMAL | Cheetah, Dog |

### Check if Entity / Instance

>[!tip] Question: Is a Dog an Entity or Instance?
>It can be <span style="color: orange;">both</span>. Hence, it depends.
>If you consider `ANIMAL` as an **entity**; then `Dog`, `Cat`, `Horse` are *instances* of the entity... But ( *big butt* )
>If you consider `DOG` as an **entity**; then breeds of dog will be **instances** of the... like `Labrador`, `Poodle`, `Bulldog`, `Terrier`

# What is an Attribute?

>[!tip]- Definition
>It is the characteristic / trait of an entity type that describe the entity.

>[!info]
>It helps to *describe, quantify, qualify, classify and specify*
>An attribute has a single value.

## Example: Entities and their Attributes

| Entities | Attributes |
| -------- | ---------- |
| CUSTOMER | ID, Name, Age, Residence, DOB |
| CAR | ID, Make, Model, Service Date |
| JOB | Title, Description, Salary |

## Types of Attributes

>[!tip]- Definition
>Volatile Attributes
>- They have **values** that are constantly *changing*
>	- Examples:
>		- Age
>		- Contact / Phone / Telephone / Mobile Phone number
>		- Salary
>		- Location
>
>Non-Volatile Attributes
>- They do not really change ( "*if ever*" )
>	- Examples:
>		- Date of Birth
>		- Gender
>		- National Identity Card
>		- Country of Origin
>		- Original Hire Date
>
>Mandatory Attributes
>- As the name implies; the value in a "*mandatory*" attribute needs to exists.
>	- They cannot be left as `Null` values
>	- Examples:
>		- Username
>		- Password

### Composite Attributes

>[!note]
>Normal / Composite Attributes are represented with a simple Oval / Esclipse.
>In addition, the Attribute name must <span style="color: red;">not</span> be **uppercased**.
>>Check below $\downarrow$

A composite attribute is just like any other attribute but can also be broken down into *sub-parts* ( *"component parts"* $\rightarrow$ in notes ).
They are often used **together** to *describe* the larger attribute.

Below $\downarrow$ is a little example:

![[Attributes - Composite Attributes.png | 650]]

### Multi-Valued Attributes

It is an attribute that can have multiple values for a single entity instance.

- Allows for storing multiple pieces of information for a single entity without creating redundant rows.

Here $\downarrow$ is an example:

![[Attributes - Multi-Valued Attributes.png | 650]]

#### Example of Both Composite and Multi-Valued Attribute

![[Attributes - Composite + Multi-Valued.png | 650]]

>[!warning]
>I forgot to underline the Primary Key; i.e <u>Employee_ID</u>

# What is an Entity Relationship Diagram?

An Entity Relationship Diagram ( ERD ) visualises the relationships between *entities* / concepts in a [[Database and Flat Files#What is a Database? | database]].

## Purpose

This is used during [[Data Modelling - Conceptual - Logical Level Modelling| Data Modelling]] and in the construction of the [[ANSI - SPARC Model#Conceptual Level / Logical Level | conceptual / logical]] level.

An ERD should completely capture and accurately "*model*" the the organisation's information / needs to support the function of the business.

## Basic E-R Notation

![[ERD - Notation.png | 555]]

>Some of this you already know from HSC but things like **Associative Entity**, **Relationship**, **Identifying Relationship**

We are going to see an **example** below $\downarrow$

## Sample E-R Diagram

![[ERD - Sample E-R Diagram.png | 650]]

### Writing the [[Business Rules]]

>Not really, because we are just doing like in HSC, but the lecturer calls it "*Business Rules*"

>[!tip]
>Look at the Key and the direction you are going to "*say*" it.

- SHIPMENT - ITEM
	- Active Form
		- $\rightarrow$ A SHIPMENT **must** *include* 1 or Many ITEMS
	- Passive Form
		- $\rightarrow$ An ITEM **may** be *included* on 0 or Many SHIPMENT

- CUSTOMER - ORDER
	- Active Form
		- $\rightarrow$ A CUSTOMER **may** *submit* 0 or Many ORDER
	- Passive Form
		- $\rightarrow$ An ORDER **must** be *placed* by 1 and only 1 CUSTOMER
- PRODUCT - ITEM
	- Active Form
		- $\rightarrow$ A PRODCUT **must** be *used in* in 1 or Many ITEM
	- Passive Form
		- $\rightarrow$ An ITEM **must** be *made-up* of 1 or Many PRODUCTS

---

# Relationships

## Cardinality / Relationship

>[!note]- What is a Cardinality?
>Refers to the **relationship** between 2 tables and indicate the number of instances of one entity that can or must be associated with each instance of another entity.
>![[What is Cardinality Example.png]]

>[!info] 3 Main Types of *Relationships*:
>1. One-to-One ( `1:1` )
>2. Many-to-One ( `m:1` ) *or* One-to-Many ( `1:m` )
>3. Many-to-Many ( `m:n` )

>[!warning] This is just for me to remember to complete the note well
>As you know; you cannot draw a many to many ( `m:n` ) relationship and leave it as it is... you have to `m:1` and `1:m`.
>But, we **can** draw it in the [[ANSI - SPARC Model#Conceptual Level / Logical Level | Conceptual / Logical Level]].
>>Now, from what I understand; the *conceptual level* is **not** *Normalised*

## Cardinality Constraints

This is a restriction placed on a data. I will give you an example below $\downarrow$.

### SUPPLIER - SHOP

```console

The SUPPLIER may supply Zero or Many SHOPS
SHOPS must receive One or Many products from the SUPPLIER

```

>This is know as the <span style="color: green;"><strong>Business Rule</strong></span>
>We are going to talk more about Business Rule [[Business Rules| here]].

### Take a Look at this Diagram

![[Entity Relationship Diagram ( Flow Lines ).png | 500]]

#### Minimum Cardinality

- Optional ( 0 ): The entity occurrence is **optional**
	- Symbol is a Circle $\circ$
- Mandatory ( 1 ): The entity occurrence is **mandatory**
	- Symbol is a Bar $|$

#### Maximum Cardinality

- One ( 1 ): At *most* **one** entity can be associated
	- Symbol is a Double Bar $\|$
- Many ( * ): **Multiple** entities can be associated
	- Symbol is the normal *Crow's Feet* `m:n` Symbol

>[!tip] What is CASE Tool?
>CASE ( *Computer-Aided Software Engineering* ) Tools are software packages used by Software Engineers; who uses them to **design** Databases.

### Properties of a Relation

1. There should be not duplicate tuples / rows
2. All columns should have different names
3. All attribute's values are atomic
4. Tuples are unordered ( *referring to rows* )
5. Attributes are unordered ( *referring to columns* )

# Degree of Relationships

>Part of [[Data Modelling - Conceptual - Logical Level Modelling| Data Modelling]]
>Link to Geek for Geeks Website: https://www.geeksforgeeks.org/degree-of-relations-in-dbms/

>[!tip]- Definition
>It represents the number of Entity **Types** that are *associated* with a relationship.

>[!tip]- Teacher's Definition
>It is the number of entity **types** that *participate* in it.

## Types of Degree

1. Unary
2. Binary
3. Ternary
4. N-ary $\rightarrow$ **not** covered by the lecturer.

### Unary Degree

As the name implies; 1. In this *degree*, the associating entity types are the **same**.
In other words, **only** 1 entity is participating in this case. 

#### Example: Unary Degree

In a particular class, we have **many** students, there are m monitors too. So, here class monitors are *also* students.

Thus we can say that **only** students are participating here.

![[Degree of Relationships - Unary Degree.png | 400]]

### Binary Degree

Yes, yes and yes; 2 Entities!
In this case we can say that a Binary relationships exists when there are 2 types of entity and we can them a *degree of relationship* of 2.

#### Example: Binary Degree

![[Degree of Relationships - Binary Degree.png | 500]]

### Ternary Degree

Now we are going to have 3 Entities that are associated... *What did you think, duh!!!*

Again, in this case we have a *degree of relationship* of 3.

#### Example: Ternary Degree

![[Degree of Relationships - Ternary Degree.png | 500]]

>[!warning]
>Even though the Lecturer did **not** cover the "*<span style="color: green;">N-ary</span>*";
>Just know that it involves many entity types and can be a combination of *unary*, *binary* and *ternary*.

# Constraints and Assumptions

## Constraints

- Not all data requirements can be **captured** using *entities*, *attributes* and relationships.
- Such items are simply recorded as *constraints*
	- Examples:
		- A course cannot accommodate more than 25 students
		- A motorcycle cannot have more than 2 passengers

## Assumptions

- To construct ERD we make assumptions about the data that are not stated in the data requirements
	- Example:
		- Assume that a Car in only *registered* once

---

# Constructing an ER Model

## Steps

1. Identify Entities
2. Read requirements specification + List all possible entity types
3. Object of Interest in the System
	- Good to put many in and then discard the rest ( *that we did not use* )
4. Remove Duplicate Entities
5. List the Attributes
6. Mark the [[Microsoft Access ( 2007 )#Primary Key | Primary Keys]]
7. Define the Relationships
8. Describe the Cardinality + Optionality of the Relationships
9. Examine the constraints which hold between participating entities
10. Remove Redundant Relationships

## Summary

- Identify Potential Entities
- Identify Attributes
- Choose Identifier
- Draw an initial ERD ( *rough* )
- Add Relationships Information
- Add Participation Information
- Redraw the ERD

---

# Socials

- [**Instagram**](https://www.instagram.com/s.sunhaloo/)
- [**YouTube**](https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg)
- [**GitHub**](https://www.github.com/Sunhaloo)

---

S.Sunhaloo
Thank You!