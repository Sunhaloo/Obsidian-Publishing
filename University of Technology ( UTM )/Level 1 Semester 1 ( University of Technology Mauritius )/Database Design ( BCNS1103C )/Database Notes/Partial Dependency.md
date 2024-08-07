---
Alias: Database Design ( Partial Dependency related with Normalisation ) - Week 6 
Tag: uni, db
Module: BCNS1103C / DBT1103C
Author: S.Sunhaloo
Date: 2024-07-09
Status: Completed
---

## List of Contents

- [[Partial Dependency#Partial Dependency | Partial Dependency]]
	- [[Partial Dependency#Example | Example]]
	- [[Partial Dependency#Define the Functional Dependency | Define the Functional Dependencies]]
- [[Partial Dependency#Steps to Find Partial Dependencies | Steps to Find Partial Dependencies]]

---

### My Links

- [[Partial Dependency#Socials | Link to Socials]]

---

>[!note]
>This note on Partial Dependency is related with [[Functional Dependency]].

>[!info] Resource
>Link to YouTube Video: https://www.youtube.com/watch?v=pYASiat3eQg
>BTW composite key and candidate key is **not** the same, but the they can overlap in practice.
>
>>[!warning]
>>In the video you will see $\{ A, B \}$ is a *Candidate Key*. But I know that as **Composite Key** $\Rightarrow$ because 2 ( *more* ) attributes are needed to uniquely identify the table.
>>While $A$ and $B$ can be considered as Candidate Key
>>Click [here](https://www.youtube.com/watch?v=pYASiat3eQg&t=80s) to listen to him!

# Partial Dependency

>[!tip]- Definition
>It is a situation in a database where an attribute depends only on a **part** of a *composite* key instead of depending on the **entire** composite key.

## Example

Suppose we have the table `Table R` $\downarrow$:

| A | B | C | D |
| - | - | - | - |
| SM | LQ | GT | HY |
| - | - | - | - |
| - | - | - | - |
| - | - | - | - |

### Define the [[Functional Dependency]]

Let's say that `Table R` has the following functional dependencies:

- $A, B \longrightarrow D$
- $B \longrightarrow C$

Hence, we get:

- $A, B \longrightarrow A, B ,C , D$

This means that $A$ and $B$ will determine all the attributes in the table.

>[!note]
>- $A, B \longrightarrow D \Rightarrow$ A and B determines D
>- $B \longrightarrow C \Rightarrow$ B determines C
>- Therefore we get:
>	- $A, B \longrightarrow A, B ,C , D$ where A, B can determine A, B, C and D
>
>>He considers this ( $\{ A, B \}$ ) a *Candidate Key*

---

No we have defined our Functional Dependencies... we can now proceed to find our **Prime** and **Non Prime** attribute.

>[!note]-
>Our lecturer calls **Prime** $\rightarrow$ *Key* attributes and **Non-Prime** $\rightarrow$ *Non-key* atrributes!

Hence we can say that in this example our "*composite key*" is our **Primary Key**

$\Rightarrow \{ A, B \} \rightarrow$ **Primary Key**


---

Now, we have figured out what our **prime** ( *key* ) and **non-prime** ( *non-key* ) attributes are; we can go back to focusing in Functional Dependency

Lets do for $A, B \longrightarrow D$ where A and B determines D

This is fine, we have **no** problem here

But if we take a loo at $B \longrightarrow C$

Now, this is <span style="color: red;"><strong>not</strong></span> right. This is because $B$ which forms part of *Composite Key* ( *hence, we can say that $B$ is a candidate key* ) and $B$ **solely** can identify $C$.

Hence, this is called a <span style="color: orange;"><strong>Partial Dependency</strong></span>!

>And this is true; if you take a look at the definition given above $\uparrow$ ( *at the start of the notes* ); it is valid!

>[!info]
>$\{ A, B \}$ is called the **Determinant** while $D$ is called the **Dependent**
>- $D$ is dependent on $\{ A, B \}$

>But wait a second; so from what he is saying [here](https://www.youtube.com/watch?v=pYASiat3eQg&t=210s)
>Its that Partial Dependency is a *type* of Functional Dependency!


#### Steps to Find Partial Dependencies

- **Identify** the *Composite Keys* ( *and maybe the Candidate Keys* )
- **Differentiate** between *Prime* and *Non-Prime* attributes
- Find the *Non-Prime* attribute that is determined by **part** or **subset** of Composite Key

>[!bug] NOTE NOTE and NOTE
>**Partial Dependencies** can only occur is your table has _**Composite** Primary Key_
>If you table **only** have *Primary Key* $\Rightarrow$ There can **never** be *Partial Dependencies*!

---

# Socials

- **Instagram**: https://www.instagram.com/s.sunhaloo
- **YouTube**: https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg
- **GitHub**: https://www.github.com/Sunhaloo

---

S.Sunhaloo
Thank You!