---
Alias: Maths of CS - Boolean Algebra
Tag: uni, maths
Module: BCNS1101C
Author: S.Sunhaloo
Date: 2024-06-03
Status: Completed
---

## List of Contents

- [[Boolean Algebra#Boolean Algebra | Boolean Algebra]]
	- [[Boolean Algebra#Definition | Definition]]
- [[Boolean Algebra#Laws of Boolean Algebra | Laws of Boolean Algebra]]
- [[Boolean Algebra#Proofs | Proofs]]
- [[Boolean Algebra#Rules | Rules]]
- [[Boolean Algebra#Examples | Examples]]
- [[Boolean Algebra#Canonical Sum of Product | Canonical Sum of Product]]

---

### My Links

- [[Boolean Algebra#Socials | Link to Social]]

---

# Boolean Algebra

>[!tip]- English Definition
>Mathematical structure that deals with **Binary** variables and **Logical** operations.
>- Named after the mathematician [George Boole](https://en.wikipedia.org/wiki/George_Boole)

## Definition

>No need to learn this part by heart $\downarrow$
>If $A$ is a **Non-Empty** Set with 2 *binary* operation $0$ and $1$ with a *unary* operation $NOT \ (1)$ then $A$ is called a Boolean Algebra if the following basic properties held for all $a$, $b$ and $c$ in $A$.


>[!warning] Need to Learn by Heart!!!
>Need to know like the back of you hand.

| Laws | Statements | Code |
| ---- | ---------- | ---- |
| Identity Laws | a + 0 = a<br>a $\cdot$ 1 = a | A1 |
| Commutative Laws | a + b = b + a<br>a $\cdot$ b = b $\cdot$ a | A2 |
| Associative Laws | ( a + b ) + c = a + ( b + c )<br>( a $\cdot$ b ) $\cdot$ c = a $\cdot$ ( b $\cdot$ c ) | A3 |
| Distributive Laws | a + ( b $\cdot$ c ) = ( a + b ) $\cdot$ ( a + c )<br>a $\cdot$ ( b + c ) = ( a $\cdot$ b ) + ( a $\cdot$ c ) | A4 |
| Complement Laws | a + a' = 1<br>a $\cdot$ a' = 0 | A5 |

## Laws of Boolean Algebra

>[!warning] Again! Need to Learn by Heart!!! $\downarrow$
>Need to know like the back of you hand.

### Idempotent Laws

$a + a = a$ and $a \cdot a = a$ for all $a \in A$

### Dominance Laws

$a + 1 = 1$ and $a \cdot 0 = 0$ for all $a \in A$

### Absorption Laws

$a \cdot ( a + b ) = a$ and $a + ( a \cdot b ) = a$ for all $a, b \in A$

### De Morgan's Laws

$( a + b )' = a' \cdot b'$ and $( a \cdot b )' = a' + b'$ for all $a, b \in A$

### Double Complement ( Involution ) Law

$(a')' = a$ for all $a \in A$

### Zero and One Laws

$0' = 1$ and $1' = 0$

# Proofs

>[!warning] Again and Again! Need to Learn by Heart!!!
>Need to know like the back of you hand.

## Idempotent Laws

$a + a = a$ and $a \cdot a = a$ for all $a \in A$

1. Proving $a + a = a$

$\Rightarrow a = a + 0 \rightarrow$ A1
$\>\>\>\>\>\>\>\>\> = a + ( a \cdot a' ) \rightarrow$ A5
$\>\>\>\>\>\>\>\>\> = ( a + a ) \cdot ( a + a' ) \rightarrow$ A4
$\>\>\>\>\>\>\>\>\> = ( a + a ) \cdot 1 \rightarrow$ A5
$\>\>\>\>\>\>\>\>\> = a + a \rightarrow$ A1

Hence $a = a + a \leftarrow$

2. Proving $a \cdot a = a$

$\Rightarrow a = a \cdot 1 \rightarrow$ A1
$\>\>\>\>\>\>\>\>\> = a \cdot ( a + a' ) \rightarrow$ A5
$\>\>\>\>\>\>\>\>\> = (a \cdot a ) + ( a \cdot a' ) \rightarrow$ A4
$\>\>\>\>\>\>\>\>\> = a \cdot  a + 0 \rightarrow$ A5
$\>\>\>\>\>\>\>\>\> = a \cdot a \rightarrow$ A1

Hence $a = a \cdot a \leftarrow$

## Dominance Laws

$a + 1 = 1$ and $a \cdot 0 = 0$ for all $a \in A$

1. Proving $a + 1 = 1$

$\Rightarrow a + 1= ( a + 1 ) \cdot 1 \rightarrow$ A1
$\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\> = ( a + 1 ) \cdot ( a \cdot a' ) \rightarrow$ A5
$\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\> = a + 1 \cdot a'\rightarrow$ A4
$\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\> = a + a' \cdot 1 \rightarrow$ A2
$\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\> = a + a' \rightarrow$ A1
$\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\> = 1 \rightarrow$ A5

Hence, $a + 1 = 1 \leftarrow$

2. Proving $a \cdot 0 = 0$

$\Rightarrow a \cdot 0 = ( a \cdot 0 ) + 0 \rightarrow$ A1
$\>\>\>\>\>\>\>\>\>\>\>\>\>\>\> = ( a \cdot 0 ) + ( a \cdot a' ) \rightarrow$ A5
$\>\>\>\>\>\>\>\>\>\>\>\>\>\>\> = a \cdot ( 0 + a' ) \rightarrow$ A4
$\>\>\>\>\>\>\>\>\>\>\>\>\>\>\> = a \cdot  ( a' + 0 ) \rightarrow$ A2
$\>\>\>\>\>\>\>\>\>\>\>\>\>\>\> = a \cdot a' \rightarrow$ A1
$\>\>\>\>\>\>\>\>\>\>\>\>\>\>\> = 0 \rightarrow$ A5

## Absorption Laws

$a \cdot ( a + b ) = a$ and $a + ( a \cdot b ) = a$ for all $a, b \in A$

1. Proving $a \cdot ( a + b ) = a$

$\Rightarrow a \cdot ( a + b ) = ( a + 0 ) \cdot ( a + b ) \rightarrow$ A1
$\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\> = a + ( 0 \cdot b ) \rightarrow$ A4
$\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\> = a + ( b \cdot 0 ) \rightarrow$ A2
$\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\> = a + 0 \rightarrow$ by Dominance Law
$\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\> = a \rightarrow$ A1

2. Proving $a + ( a \cdot b ) = a$

$\Rightarrow a + ( a \cdot b ) =  ( a \cdot 1 ) + ( a \cdot b ) \rightarrow$ A1
$\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\> = a + ( 1 + b ) \rightarrow$ A4
$\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\> = a \cdot ( b + 1 ) \rightarrow$ A2
$\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\> = a \cdot 1 \rightarrow$ by Dominance Law
$\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\> = a \rightarrow$ A1

## De Morgan's Laws

$( a + b )' = a' \cdot b'$ and $( a \cdot b )' = a' + b$ for all $a, b \in A$

>[!note]
>If $y$ is to be the *complement* of $x$,
>By definition, we must show that $x + y = 1$ and $x \cdot y = 0$

1. Proving $( a + b )' + a' \cdot b' = 1$

$\Rightarrow ( a + b ) + ( a' \cdot b' ) = \{ ( a + b ) + a' \} \cdot \{ ( a + b ) + b' \} \rightarrow$ A4
$\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\> = \{ b + a + a' \} \cdot \{ ( a + b ) + b' \} \rightarrow$ A2
$\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\> = \{ b + ( a + a' ) \} \cdot \{ a + ( b + b' ) \} \rightarrow$ A3
$\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\> = ( b + 1 ) \cdot ( a + 1 ) \rightarrow$ A5
$\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\> = 1 \cdot 1 \rightarrow$ by Dominance Laws
$\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\> = 1 \rightarrow$ A1

2. Proving $( a + b ) \cdot ( a' \cdot b' ) = 0$ 

$\Rightarrow ( a + b ) \cdot ( a' \cdot b' ) = ( a' \cdot b' ) \cdot ( a + b ) \rightarrow$ A2
$\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\> = a' \cdot b' \cdot a + a' \cdot b \cdot b \rightarrow$ A4
$\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\> = a \cdot ( a' \cdot b' ) + a' \cdot ( b' \cdot b ) \rightarrow$ A3
$\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\> = ( a \cdot a') \cdot b' + a' \cdot ( b' \cdot b ) \rightarrow$ A3 + A2
$\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\> = 0 \cdot b' + a' \cdot 0 \rightarrow$ A5
$\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\> = 0 + 0 \rightarrow$ by Dominance Laws
$\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\> = 0 \rightarrow$ A1

So for both we get $a' \cdot b'$ is the complement of $( a + b )$. That is $( a + b )' = a' \cdot b'$

## Double Complement / Involution Law

$( a' )' = a$ for all $a \in A$

$\Rightarrow a + a' = 1$ and $a \cdot a' = 0 \rightarrow$ A5
$\Rightarrow a' + a = 1$ and $a' \cdot a = 0 \rightarrow$ A5

Therefore $a$ is the complement of $a'$; that is $( a' )' = a \leftarrow$

## Zero and One Law

$0' = 1$ and $1' = 0$

Proving $0' = 1$

$\Rightarrow 0' = ( a \cdot a')' \rightarrow$ A5
$\>\>\>\>\>\>\>\>\>\> = a' + ( a' )' \rightarrow$ De Morgan's Law
$\>\>\>\>\>\>\>\>\>\> = a' + a \rightarrow$ Involution Law
$\>\>\>\>\>\>\>\>\>\> = a + a' \rightarrow$ A2
$\>\>\>\>\>\>\>\>\>\> = 1 \rightarrow$ A2

Now $( a' )' = 1'$; that is, $0 = 1'$ and $1' = 0$

>[!warning] NOTE
>$$a' + 1 = 1$$
>$$( a + a'b ) = a + b$$
>$$OR$$
>$$( b + ab' ) = b + a$$

# Rules

## Complement

$$( A' ) = A$$

## AND

$$( A \cdot A ) = A$$
$$( A \cdot 0 ) = 0$$
$$( A \cdot 1 ) = A$$
$$( A \cdot A' ) = 0$$

## OR

$$( A + A ) = A$$
$$( A + 0 ) = A$$
$$( A + 1 ) = 1$$
$$( A + A' ) = 1$$

## Distributive

$$A + ( B \cdot C ) = ( A + B ) \cdot ( A + C )$$
$$A \cdot ( B + C ) = ( A \cdot B ) + ( A \cdot C )$$
$$A + ( A' \cdot B ) = A + B$$
$$A' + ( A \cdot B ) = A' + B$$

## De Morgan's Law

$$( A + B )' = A' \cdot B'$$
$$( A \cdot B )' = A' + B'$$

# Examples

## Example 1

Use Boolean Algebra and [[Logic Proposition ( Logic Gates - Truth Tables )#Truth Table| Truth Table]]

$$A \cdot B + A \cdot B'$$

### Boolean Algebra

Let $y = A \cdot B + A \cdot B'$

$\Rightarrow A \cdot B + A \cdot B' = A \cdot ( B + B' )$
$\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\> = A \cdot ( B + B' )$
$\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\> = A \cdot ( 1 ) \rightarrow$ A5
$\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\> = A\rightarrow$ A2

### Truth Table

| A | B | $\neg$ B | A $\land$ B | A $\land \ \neg$ B | ( A $\land$ B ) $\vee$ ( A $\land \ \neg$ B ) |
| - | - | ------- | ----------- | ---------------- | ------------------------------------------ |
| 0 | 0 | 1 | 0 | 0 | 0 |
| 0 | 1 | 0 | 0 | 0 | 0 |
| 1 | 0 | 1 | 0 | 1 | 1 |
| 1 | 1 | 0 | 1 | 0 | 1 |

| Final Answer | A |
| ------------ | - |
| 0 | 0 |
| 0 | 0 |
| 1 | 1 |
| 1 | 1 |

>[!tip] Final Answer is Equal to A

>In this case, it was like this ( *the final answer is $A$* ).
>But we could have another **equation** as our *answer*!

## Example 2

Use Boolean Algebra and Truth Table to simplify

>In this case it have not included `\cdot` / $\cdot$

$$A  B + A B' C + A B' C'$$

## Boolean Algebra

Let $y = A  B + A B' C + A B' C'$

$\Rightarrow y = A  B + A B' C + A B' C'$
$\>\>\>\>\>\>\>\>\>\> = A ( B + B'C + B'C' )$
$\>\>\>\>\>\>\>\>\>\> = A [ B + B'( C + C') ]$
$\>\>\>\>\>\>\>\>\>\> = A ( B + B' \times 1 )$
$\>\>\>\>\>\>\>\>\>\> = A ( 1 \times 1 )$
$\>\>\>\>\>\>\>\>\>\> = A \leftarrow$

## Truth Table

| A | B | C | A $\land$ B | $\neg$ B | $\neg$ C | A $\land \ \neg$ B | A $\land \ \neg$ B $\land$ C | A $\land \ \neg$ B $\land \ \neg$ C |
| - | - | - | ---------- | ------- | -------- | ---------------- | ------------------------- | -------------------------------- |
| 0 | 0 | 0 | 0 | 1 | 1 | 0 | 0 | 0 |
| 0 | 0 | 1 | 0 | 1 | 0 | 0 | 0 | 0 |
| 0 | 1 | 0 | 0 | 0 | 1 | 0 | 0 | 0 |
| 0 | 1 | 1 | 0 | 0 | 0 | 0 | 0 | 0 |
| 1 | 0 | 0 | 0 | 1 | 1 | 1 | 0 | 1 |
| 1 | 0 | 1 | 0 | 1 | 0 | 1 | 1 | 0 |
| 1 | 1 | 0 | 1 | 0 | 1 | 0 | 0 | 0 |
| 1 | 1 | 1 | 1 | 0 | 0 | 0 | 0 | 0 |


>The Truth Table continues below $\downarrow$

| ( A $\land$ B ) $\vee$ ( A $\land \ \neg$ B $\land$ C ) | ( A $\land$ B ) $\vee$ ( A $\land \ \neg$ B $\land$ C ) $\vee$ ( A $\land \ \neg$ B $\land \ \neg$ C ) |
| -------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| 0 | 0 |
| 0 | 0 |
| 0 | 0 |
| 0 | 0 |
| 0 | 1 |
| 1 | 1 |
| 1 | 1 |
| 1 | 1 |

| Final Answer | A |
| ------------ | - |
| 0 | 0 |
| 0 | 0 |
| 0 | 0 |
| 0 | 0 |
| 1 | 1 |
| 1 | 1 |
| 1 | 1 |
| 1 | 1 |

---

# Canonical Sum of Product

The Canonical Sum of Product need not contain all literals but in *canonical form*, each product term contains all literals either in *complemented* or *un-complemented* form.
These products terms are nothing but **minterms** such of all *minterms* of expressions, $F$, for which $F$ assumes 1 is called the Canonical Sum of Product

## Example 1: Find Canonical Sum of Product

Consider the $\downarrow$ truth table:

| $x$ | $y$ | $z$ | $F$ |
| -- | --- | --- | -- |
| 0 | 0 | 0 | 0 |
| 0 | 0 | 1 | 1 |
| 0 | 1 | 0 | 0 |
| 0 | 1 | 1 | 1 |
| 1 | 0 | 0 | 0 |
| 1 | 0 | 1 | 1 |
| 1 | 1 | 0 | 0 |
| 1 | 1 | 1 | 1 |

Find the above $\uparrow$ Canonical Sum of Products from the above $\uparrow$ table.

$$
F ( x, y, z ) = x'y'z + x'yz + xy'z + xyz
$$

>[!tip]
>We only take the "*equation*" when the output becomes '1'.

--- 

# Socials

- **Instagram**: https://www.instagram.com/s.sunhaloo/
- **YouTube**: https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg
- **GitHub**: https://www.github.com/Sunhaloo

---

S.Sunhaloo
Thank You!