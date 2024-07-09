---
Alias: Database Design ( Partial Dependency related with Normalisation ) - Week 6 
Tag: uni, db
Module: BCNS1103C / DBT1103C
Author: S.Sunhaloo
Date: 2024-07-09
Status: In-Progress
---

## List of Contents



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

### Define the [[Functional Dependency | Functional Dependencies]]

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


# Socials

- **Instagram**: https://www.instagram.com/s.sunhaloo
- **YouTube**: https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg
- **GitHub**: https://www.github.com/Sunhaloo

---

S.Sunhaloo
Thank You!