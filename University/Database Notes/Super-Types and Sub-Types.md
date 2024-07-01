---
Alias: Database Design ( Entity Mapping + Supertypes and Subtypes ) - Week 5 
Tag: uni, db
Module: BCNS1103C / DBT1103C
Author: S.Sunhaloo
Date: 2024-06-10
Status: Completed
---

>[!warning]
>This "*note*" is **not** complete; please refer to [[Main Slides ( Enhanced ERD + Business Rules ).pdf]] for full notes
>>Why is that?
>>Because I do not understand a thing!

## List of Contents

- [[Super-Types and Sub-Types#Entity Mapping | Entity Mapping]]
- [[Super-Types and Sub-Types#Super-Types and Sub-Types | Super-Types and Sub-Types]]
	- [[Super-Types and Sub-Types#Diagrams of Super-Type and Sub-Type | Diagrams of Super-Type and Sub-Type]]
- [[Super-Types and Sub-Types#Relationships and Sub-Type | Relationships and Sub-Type]]
- [[Super-Types and Sub-Types#Generalisation and Specialisation | Generalisation and Specialisation]]
	- [[Super-Types and Sub-Types#Diagrams of Generalisation and Specialisation | Diagrams of Generalisation and Specialisation]]

---

### My Links

- [[Super-Types and Sub-Types#Socials | Link to Social]]

---

# Entity Mapping

## Types of Entities

>We have already look at the types of entities over at [[Entity Relationship Diagram ( ERD ) and Relationships#Types of Entities | ERD and Relationship - Types of Entities]]

Just know that we have:

- Regular / Strong Entities
- Weak Entities
- Associative Entities

>I do not really know how to like structure this note!
>So for now, I am only including the Teacher's Notes
>I have searched online, they are just actually documentation for softwares or just repeating things like [[Entity Relationship Diagram ( ERD ) and Relationships#Cardinality / Relationship | Cardinality]] which we have already covered.

>[!tip] Teacher's Notes
>## Regular Entity Mapping
>- Each regular entity types in ERD is transformed into a relation
>- The name of relation is **same** as the entity name
>- Each simple attribute of the entity type becomes an attributes of the relation
>- Identifier of the entity types becomes the primary key of the corresponding relation.
>>Refer to [[Main Slides ( Enhanced ERD + Business Rules ).pdf]] for diagrams
>>>[!warning]
>>>Some diagrams are fucking trash and are wrong!
>## Regular Entity with Multivalued Attribute Mapping
>- When the *regular entity* types contains a Multivalued Attribute, 2 new relation are created
>- First relation contains all of the attributes of the entity type except the multivalued attribute
>- Second relation contains two attributes that form Primary Key to second relation
>- First of these attributes is Primary Key from the first relation
>- Second is the Multivalued Attribute

# Super-Types and Sub-Types

>[!tip]- Definition
>- Supertype: It is an entity type that has got *relationship* ( *parent to child* ) with **one** or **more** *subtypes* and it contains *attributes* that are **common** to its subtypes
>- Subtypes: They are subgroups of the *Supertype* entity and have **unique** *attributes*; But will be **different** from each *Subtype*

>[!tip] Teacher's Definition
>- Supertype: A generic entity type that has a relationship with one or more subtypes
>- Subtype: A subgrouping of the entities in an entity type which has attributes that are distinct from those in other subgroupings
>- Inheritance:
>>[!info] Important
>>- Subtype entities **inherit** value of all attributes of the Supertype
>>- An **instance** of a Subtype is also an instance of the Supertype
>

### Diagrams of Super-Type and Sub-Type

![[SuperType with 3 SubTypes.png | 700]]

## Relationships and Sub-Type

- Relationships at the **Supertype** level indicate that **all** *Subtypes* will participate in the relationship.
- Instances of a **Subtype** <span style="color: red;">may</span> participate in a relationship **unique** to that *Subtype*.
	- Hence, the relationship is shown at the Subtype level.

### Diagram of Relationship and Sub-Type

![[SuperType - SubTypes Relationships.png | 700]]

## Generalisation and Specialisation

>[!tip]- Definition
>- Generalisation: Process of defining a more *General* entity type from a set of more *Specialised* entity types
>	- Bottom-Up $\uparrow$
>- Specialisation: Process of defining **one** or **more** *Subtypes* of the *Supertype*, and forming supertype / subtype relationships
>	- Top-Down $\downarrow$

### Diagrams of Generalisation and Specialisation

#### Example 1: Generalisation 3 Entity Types `CAR`, `TRUCK` and `MOTOCYCLE`

![[SuperType - SubTypes Generalisation Example 1.png | 700]]

#### Example 2: Generalisation to `VEHICLE` Super-Type

![[SuperType - SubTypes Generalisation Example 2.png | 700]]

#### Example 1: Specialisation Entity Type `PART`

![[SuperType - SubTypes Specialisation Example 1.png | 700]]

#### Example 2: Specialisation to `MANUFACTURED PART` and `PURCHASED PART`

![[SuperType - SubTypes Specialisation Example 2.png | 700]]

## Constraints in Super-Type

>[!tip]- Definition
>1. Completeness Constraints: Whether an instance of a *Supertype* **must** also be a member of **at least** 1 *Subtype*
>	- Total Specialisation Rule: `Yes` ( *double lined* )
>	- Partial Specialisation Rule: `No` ( *single lined* )
>2. Disjointness Constraints: Whether and **instance** of a *Supertype* may simultaneously be a member of **two** or **more** *Subtypes*
>	- Disjoint Rule: An instance of the Supertype can be **only** 1 of the *Subtypes*
>	- Overlap Rule: An instance of the *Supertype* could be **more** than 1 of the *Subtypes*
>3. Subtype Discriminator: An *attribute* of the *Supertype* whose values determine the target Subtype(s)
>	- Disjoint: A simple *attribute* with alternative values to indicate the possible *Subtypes*
>	- Overlapping: [[Entity Relationship Diagram ( ERD ) and Relationships#Composite Attributes | Composite]] *attribute* whose subparts [pertain]() to different *Subtypes*. Each subpart contains a **boolean** value to indicate whether or not the instance belongs to the **associated** *Subtype*

### Completeness Constraints

![[SuperType - SubTypes Completeness Constraint.png | 700]]

### Disjointness Constraints

#### Disjoint Rule

![[SuperType - SubTypes Disjointness Constraint.png | 700]]

#### Overlap Rule

![[SuperType - SubTypes Overlap Constraint.png | 700]]

## Entity Clusters

Breaking down of Entity Relationship Diagrams when it get too large / big

>[!tip] Teacher's Notes
>ERD are difficult to read when there are too many entities and relationships
>Solution: Group entities and relationships into **Entity Clusters**
>**Entity Clusters**: Set of one or more entity types and associated relationships grouped into a single abstract entity type.


---

# Socials

- [**Instagram**](https://www.instagram.com/s.sunhaloo/)
- [**YouTube**](https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg)
- [**GitHub**](https://www.github.com/Sunhaloo)

---

S.Sunhaloo
Thank You!