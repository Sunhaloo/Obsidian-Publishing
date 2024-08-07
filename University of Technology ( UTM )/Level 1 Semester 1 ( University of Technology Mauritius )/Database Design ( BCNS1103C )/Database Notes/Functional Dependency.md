---
Alias: Database Design ( Functional Dependency related with Normalisation ) - Week 6
Tag: uni, db
Module: BCNS1103C / DBT1103C
Author: S.Sunhaloo
Date: 2024-07-09
Status: HOLD
---

## List of Contents

- [[Functional Dependency#Functional Dependency | Functional Dependency]]
	- [[Functional Dependency#What is the Logic behind Functional Dependency? | Logic behind Functional Dependency]]
	- [[Functional Dependency#Onto the Real Example | Example]]
		- [[Functional Dependency#Example of <span style="color green;">VALID</span> Functional Dependency | Example of Valid Functional Dependency]]
		- [[Functional Dependency#Example of <span style="color red;">INVALID</span> Functional Dependency | Example of Invalid Functional Dependency]]

---

### My Links

- [[Functional Dependency#Socials | Link to Socials]]

---

>[!note]
>This note on Functional Dependency is related with [[Normalisation]].

>[!info] Resource
>Link to YouTube Video: https://www.youtube.com/watch?v=fZ41WtisQgo 

# Functional Dependency

>[!tip]- Definition
>Functional Dependency in a database is the **relationship** between 2 sets of attributes.
>It checks if the **value** of 1 *attribute* ( *or set of attributes* ) determine the **value** of another *attribute* ( *or set of attributes* )
>- Functional Dependency *exists* when 1 attribute **uniquely** determines another attribute.

## What is the Logic behind Functional Dependency?

Let's say that you have a function that takes an input / number and then outputs the **square** of that value.

$$
\begin{align*}
f(x) \rightarrow y
\end{align*}
$$

Where we take $x$ as input and $y$ would be the output ( *i.e the square of $x$* ).

For example if you have:

$$
\begin{align*}
f(2) \rightarrow 4
\end{align*}
$$

Hence, the input $x$ was 2 and the output $y$ was 4.

In other words, you can say that $4$ is **determined** by $2$ by the function $f(x) \ \leftarrow$

>The last line above $\uparrow$ is the whole concept of Functional Dependency!

## Onto the Real Example

>What is "*real*" nowadays!

Take a look at this table below $\downarrow$:

| A | B |
| - | - |
| 1 | AB |
| 2 | CD |
| 3 | EF |
| 4 | GH |

$$
\begin{align*}
A \rightarrow B
\end{align*}
$$

Now, this does **not** mean that we can *compute* the $B$ with $A$.
But actually we say:

>The *value* of $A$ **determines** the *value* of $B$

Let me do one for you.

If you have the value of $A$ which is `3`... Could we **determine** the value of $B$?

Yes! Yes, you can, because if you apply the logic of $A \rightarrow B$; you will see that our value for $B$ when $A$ is `3` is equal to `EF`

$$
\begin{align*}
A \rightarrow B
\Rightarrow 3 \rightarrow EF
\end{align*}
$$

Then we get the *active* and *passive* forms. What is the *active* and *passive* form you ask? English, there is something in the English language where you learn about active and passive form.

Active Form $\Rightarrow \ A$ determines $B$
Passive Form $\Rightarrow B$ is determined by $A$

>[!note]
>Here $A$ is the **determinant** and $B$ is the **dependent**.
>>This is because with the value of $A$ you get the value of $B$!

---

## Student Table

Take a look at this `Student` table.

| Roll_No | Student_Name | Dept_Name | Dept_Building |
| ------- | ------------ | --------- | ------------- |
| 2 | abc | CS | A4 |
| 3 | pqr | IT | A3 |
| 4 | xyz | CS | A4 |
| 5 | xyz | IT | A3 |
| 6 | mno | EC | B2 |
| 7 | jkl | ME | B2 |

### Example of <span style="color: green;">VALID</span> Functional Dependency


#### Case 1: `Roll_No` $\rightarrow$ { `Student_Name`, `Dept_Name`, `Dept_Building` }

$\Rightarrow$ 3 $\rightarrow$ { pqr, IT, A3 }

In the case where we have different **determinants** and corresponding different **dependants**... Its <span style="color: green;">always</span> going to be **valid**.

| Determinant | Dependent |
| ----------- | --------- |
| 1 | a |
| 2 | b |

This is always a valid Functional Dependency!

#### Case 2: `Dept_Name` $\rightarrow$ `Dept_Building`

Now, we can all see and agree that we have duplication in the column `Dept_Name`; but that does **not** mean that we are going to have a "*non-functional*" dependency. Lets me show you how its done.

This is for `Roll_No` $2$ and $3$ respectively.
$\Rightarrow$ CS $\rightarrow$ A4
$\Rightarrow$ IT $\rightarrow$ A3

Now let's go ahead and look at the "*duplicated*" values, i.e for `Roll_No` $4$ and $5$
$\Rightarrow$ CS $\rightarrow$ A4
$\Rightarrow$ IT $\rightarrow$ A3

Its still the **same**!

This means that its a <span style="color: green;">always</span> Functional Dependency.

| Determinant | Dependent |
| ----------- | --------- |
| 1 | a |
| 1 | a |

This is considered to be a **valid** Functional Dependency.

>[!warning]
>Where it would <span style="color: red;"><strong>not</strong></span> have been valid is, if one time it was:
>$\Rightarrow$ CS $\rightarrow$ A4
>And another time it becomes:
>$\Rightarrow$ CS $\rightarrow$ XX

#### Case 3: `Dept_Name` and `Dept_Building`

Lets take this as example:

$\Rightarrow$ EC $\rightarrow$ B2
$\Rightarrow$ ME $\rightarrow$ B2

This is still considered to be a <span style="color: green;">valid</span> Functional Dependency.

>This is because **different** *department* can use / be in the **same** *building*.

| Determinant | Dependent |
| ----------- | --------- |
| 1 | a |
| 2 | a |

This is considered to be a **valid** Functional Dependency.

### Example of <span style="color: red;">INVALID</span> Functional Dependency

#### Case: `Student_Name` $\rightarrow$ `Dept_Name`

Check out the `Roll_No` for $4$ and $5$

$\Rightarrow$ xyz $\rightarrow$ CS
$\Rightarrow$ xyz $\rightarrow$ IT

This is <span style="color: red;"><strong>NOT</strong></span> a valid Functional Dependency!!!

This is because for the **same** *determinant* we have **different** *dependent*

| Determinant | Dependent |
| ----------- | --------- |
| 1 | a |
| 1 | b |

This is what I was talking about in the <span style="color: orange;">Warning</span> in [[Functional Dependency#Case 2 `Dept_Name` $ rightarrow$ `Dept_Building` | Case 2]]. This is an example of an <span style="color: red;"><strong>INVALID</strong></span> Functional Dependency.

>[!note]
>I think you can say that [[Partial Dependency]] is part of *Functional Dependency*.
>>It's a specific type of *Functional Dependency*!

---

# Socials

- **Instagram**: https://www.instagram.com/s.sunhaloo
- **YouTube**: https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg
- **GitHub**: https://www.github.com/Sunhaloo

---

S.Sunhaloo
Thank You!