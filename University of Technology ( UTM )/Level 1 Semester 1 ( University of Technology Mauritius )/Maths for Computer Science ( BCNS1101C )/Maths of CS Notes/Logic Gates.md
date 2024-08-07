---
Alias: Maths for CS - Logic Gates
Tag: uni, maths
Module: BCNS1101C
Author: S.Sunhaloo
Date: 2024-06-10
Status: Completed
---

## List of Contents

- [[Logic Gates#What is a Logic Gate | What is a Logic Gate]]
	- [[Logic Gates#Diagrams of Logic Gates | Diagrams of Logic Gates]]
- [[Logic Gates#Combination of Gates | Combination of Gates]]
- [[Logic Gates#Adders | Adders]]
	- [[Logic Gates#Half-Adder | Half-Adder]]
- [[Logic Gates#Karnaugh Map | Karnaugh Map]]
	- [[Logic Gates#Example Simple 3 Variable K-Map | Simple 3 Variable K-Map Example]]
		- [[Logic Gates#Example Given Function find the Boolean Algebra | Given Function find Boolean Algebra]]

---

### My Links

- [[Logic Gates#Socials | Link to Socials]]

---

# What is a Logic Gate

>From the trusty [Wikipedia](https://en.wikipedia.org/wiki/Logic_gate)

>[!tip] Definition
>A Logic Gate is a device that performs [Boolean Function](https://en.wikipedia.org/wiki/Boolean_function), a logical operation / connectives performed on one or more **binary** ( `1` */* `0` ) inputs that produces a **single** binary *output*. ( *Boolean Function and Logical Operation / Connective is related to [[Logic Proposition ( Logic Gates - Truth Tables ) | Logic Proposition]]* ).
>>I did not hide the definition by default; because this is something that we just "*do*".

>[!tip] Teacher's Definition
>Fundamental building blocks of digits circuits. They perform basic logical functions with 1 or more binary *inputs* to produce a **single** *output*.
>```mermaid
>graph LR
>	A[1 or More Inputs] ---> B(Single OUTPUT)
>```

>[!info] What Physical Hardware are used to make Logic Gates?
>Primary Examples of these hardware are written below $\downarrow$:
>- Diodes
>- Transistors
>	- [MOSFETs](https://en.wikipedia.org/wiki/MOSFET)
>>Now, there is one thing I want to geek out about; Apollo 11 Mission.
>>I do not know if its related or whatever, but I just wanna include this here.
>>Go check this video out: https://www.youtube.com/watch?v=6mMK6iSZsAs
>

# Diagrams of Logic Gates

## NOT $\neg$ Gate

![[NOT Gate.png]]

## AND $\land$ Gate

![[AND Gate.png]]

## OR $\vee$ Gate

![[OR Gate.png]]

## XOR $\oplus$ Gate

![[XOR Gate.png]]

# Combination of Gates

When basic gates are interconnected, combinational circuits are formed

## Separate inputs for each gate

![[Separate Inputs for Gates.png]]

## Branching ( inputs are shared )

![[Branching Inputs for Gates.png]]

# Adders

## Half-Adder

It is the combinational arithmetic that adds 2 numbers and produces a **sum bit**(s) and a **carry bit**(s) both as output.

| x | y | x' | y' | xy' | x'y | Sum ( S ) | Carry ( C ) |
| - | - | -- | -- | --- | --- | - | - |
| 1 | 1 | 0 | 0 | 0 | 0 | 0 | 1 |
| 1 | 0 | 0 | 1 | 1 | 0 | 1 | 0 |
| 0 | 1 | 1 | 0 | 0 | 1 | 1 | 0 |
| 0 | 0 | 1 | 1 | 0 | 0 | 0 | 0 |

From the truth table, it can be observed that:

$$S = xy' + x'y$$
$$C = xy$$

>[!info]-
>Now this is his explanation; in HSC, we did something like this:
>
>| A | B | S | C |
>| - | - | - | - |
>| 0 | 0 | 0 | 0 |
>| 0 | 1 | 1 | 0 |
>| 1 | 0 | 1 | 0 |
>| 1 | 1 | 0 | 1 |
>
>This is because in Computer Science, `1 + 1 = 0 Carry 1`, because the computer only understands machine code. Like we cannot do `1 + 1 = 2` in Computers ( *hardware level* )!
>But as you can see above $\uparrow$ the lecturer did not do it like in HSC.
>He made the Sum bit ( S ) = $xy' + x'y$ and the Carry Bit ( C ) = $xy$
>This is because he is making it using an `XOR` and `AND` gate;
>- The `XOR` gate gives us the Sum $\Rightarrow xy' + (xy)'$
>- The `AND` gate gives us the Carry $\Rightarrow xy$
>Here is a little diagram for you to understand
>![[Half-Adder XOR and AND gate.png | 400]]
>>He is showing us how is becomes like that ( *the diagram* ), thats why he did not do it like in HSC!

### Half-Adder Diagram

![[Half-Adder 2 AND gates, 2 NOT gates, 1 OR Gate.png]]

>[!tip]
>Check how we make $S = x'y + xy'$, in the Half-Adder Diagram
>Now if you check the diagram [[Half-Adder XOR and AND gate.png]], you can see that the `XOR` gate is basically **2** `AND` gates, **2** `NOT` gates ( *one on each `AND`* ) and **1** `OR` gate!

We can observe that:

>[!warning]
>**Simplification** of above $\uparrow$ Half-Adder diagram!
>Need to learn this to be able to draw the *Simplified Version of Half-Adder*!

$xy' + x'y = 1 + xy' + x'y + 1$
$\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\> = xx' + xy' + x'y + yy'$
$\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\> = x(x' + y') + y(x' + y')$
$\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\> = (x' + y')(x + y)$
$\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\>\> = (x + y)(xy)' \leftarrow$ Using this we can draw the simplified version.

#### Simplified Version of Half-Adder

>We are now drawing this Boolean Equation $\Rightarrow (x + y)(xy)'$

![[Half-Adder Simplified Diagram.png]]

# Example: [[Boolean Algebra]] + Drawing

## F = A'BC + AB'C' + A'B'C' + AB'C + ABC

Solution:

$\Rightarrow A'BC + ABC + AB'C' + A'B'C' + AB'C$
$= BC ( A' + A ) + B'C' ( A + A' ) + AB'C$
$= B'C' + BC + AB'C$
$= B'C' + C ( AB' + B )$
$= B'C' + C ( A + B )$
$= AC + BC + B'C' \leftarrow$

![[Boolean Algebra and Drawing Example 1.png]]

## F = A [ B + C ( AB + AC ) ]

$\Rightarrow = A [ B + ABC + ACC ]$
$= AB + AABC + AAC$
$= AB + ABC + AC$
$= A [ B + BC + C ]$
$= A [ B + C ( B + 1 )] \rightarrow$ $( B + 1 ) = 1 \leftarrow$ By [[Boolean Algebra#Dominance Laws | Dominance Law]]
$= A [ B + C ]$
$= AB + AC \leftarrow$

![[Boolean Algebra and Drawing Example 2.png]]

## F = A'B'C + ( A + B + C )' + A'B'C'D

## F = AB + ABC + A'B + AB'C

$\Rightarrow ABC + AB + A'B + AB'C$
$= AB ( C + 1 ) + A'B + AB'C$
$= AB + A'B + AB'C$
$= B ( A + A' ) + AB'C$
$= B + B' ( AC )$
$= B + ( AC )B' \rightarrow$ $b + ab' = a +b$
$\Rightarrow B + AC$
$= AC + B \leftarrow$

![[Boolean Algebra and Drawing Example 4.png]]

## F = A + A'B + A'B'C + A'B'C'D

# Karnaugh Map

>Wikipedia Link [here](https://en.wikipedia.org/wiki/Karnaugh_map)

## Example: Simple 3 Variable K-Map

Study this Truth Table below $\downarrow$:

| A | B | C | F |
| - | - | - | - |
| 0 | 0 | 0 | 0 |
| 0 | 0 | 1 | 0 |
| 0 | 1 | 0 | 1 |
| 0 | 1 | 1 | 0 |
| 1 | 0 | 0 | 1 |
| 1 | 0 | 1 | 1 |
| 1 | 1 | 0 | 1 |
| 1 | 1 | 1 | 0 |

### Drawing / Writing the K-Map

![[K-Map Simple Example.png]]

#### Calculation

##### Group x

| | First Value | Second Value | Status |
| - | ----------- | ------------ | ------ |
| A | 0 | 1 | Varies |
| B | 1 | 1 | Same |
| C | 0 | 0 | Reverse |

If the "*status*" is `Same` or `Reverse` $\Rightarrow$ We take it!

>We never take the one that `varies`

Hence, in this case our Boolean Algebra becomes $BC'$

##### Group y

| | First Value | Second Value | Status |
| - | ----------- | ------------ | ------ |
| A | 1 | 1 | Same |
| B | 0 | 0 | Reverse |
| C | 0 | 1 | Varies |

Again, using the same principles $\Rightarrow$ we get the answer $AB'$

>[!tip] Therefore the Final Answer is
>$F = AB' + BC'$

#### Logic Circuit

![[K-Map Simple Example - Logic Circuit Diagram.png]]

## Example: Given Function find the Boolean Algebra

>I will be writing everything in the drawing as it will be easier for me!

### Example 1: F = AB' + A'CD + ABC'

![[Convert Boolean Algebra to K-Map Example 1.png | 300]]

### Example 2: F = C + AD' + A'BC'D + AB'C

![[Convert Boolean Algebra to K-Map Example 2.png | 300]]

---

# Socials

- **Instagram**: https://www.instagram.com/s.sunhaloo/
- **YouTube**: https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg
- **GitHub**: https://www.github.com/Sunhaloo

---

S.Sunhaloo
Thank You!