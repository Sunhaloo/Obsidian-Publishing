---
Alias: Computational Mathematics ( Matrices ) - Week 1
Tag: uni, maths, uom
Module: ICT 1207
Author: S.Sunhaloo
Date: 2024-07-24
Status: Completed
---

## List of Contents

- [[Computational Mathematics - Matrices#Matrices | Matrices]]
	- [[Computational Mathematics - Matrices#Example of a Matrix | Example of a Matrix]]
	- [[Computational Mathematics - Matrices#Order of Matrix | Order of Matrix]]
- [[Computational Mathematics - Matrices#Elements | Elements]]
	- [[Computational Mathematics - Matrices#Transpose of a Matrix | Transpose of a Matrix]]
	- [[Computational Mathematics - Matrices#Minor of an Element | Minor of an Element]]
- [[Computational Mathematics - Matrices#Determinant of Matrices - Without Co-Factor | Determinant of Matrices - Without Co-Factor]]
- [[Computational Mathematics - Matrices#Co-Factor of Matrix / Elements | Co-Factor of Matrix]]
	- [[Computational Mathematics - Matrices#Sign Chart | Sign Chart]]
- [[Computational Mathematics - Matrices#Inverse of Matrix | Inverse of Matrix]]
	- [[Computational Mathematics - Matrices#Example of Inverse of Matrix | Example of Inverse of Matrix]]
- [[Computational Mathematics - Matrices#Simultaneous Equations with Matrices | Simultaneous Equations with Matrices]]

---

### My Links

- [[Computational Mathematics - Matrices#Socials | Link to Socials]]

---

>[!info]
>For more precise notes / explanation; refer to [[Computational Mathematics - Senior's Notes.pdf]].

# Matrices

>[!tip]- What is a [Matrix](https://en.wikipedia.org/wiki/Matrix_(mathematics))?
>It is a rectangular array or table of *numbers*, *symbol*, or *expressions*, with elements or entries arranged in **rows** and **columns**, which is used to represent a mathematical object or property of such an object.

## Example of a Matrix

Consider this matrix below $\downarrow$:

![[Simple Example of Matrix.png | 550]]

This matrix is referred to as $A$. The *elements* are referred to as $a$.

$$
\Rightarrow a_{11} = d
$$
$$
\Rightarrow a_{12} = b
$$

## Order of Matrix

The *Order of a Matrix* can be found using the formula below $\downarrow$:

$$
Order = row \times column
$$

Take a look at the image below:

![[Order of Matrix Examples.png | 400]]

---

# Elements

## Transpose of a Matrix

The *Transpose of a Matrix* is obtained by interchanging the row and column **index** of each element

### For 2 By 2 Matrix

$$
A = 
\begin{pmatrix}  
d & b \\  
c & e   
\end{pmatrix}

\rightarrow

\begin{pmatrix}  
d & c \\  
b & e   
\end{pmatrix}
$$

### For 3 By 3 Matrix

$$
A = 
\begin{pmatrix}  
1 & 2 & 3 \\
a & b & c \\
x & y & z \\
\end{pmatrix}

\rightarrow

\begin{pmatrix}  
1 & a & x \\
2 & b & y \\
3 & c & z \\
\end{pmatrix}
$$

## Minor of an Element

A minor for any element is the determinant that results when the **row** and **column** that element is in, are **deleted**

>[!note]
>$$M_{ij} = Minor \ ( a_{ij} )$$
>Where: $M_{ij}$ is the $( n - 1 ) \times ( n - 1 )$ matrix made by removing the row $i$ and column $j$ of $A$

>Take a look at these images below so that you can get an idea of how we can calculate the Minor ( $M_{{ij}}$ ) of an element

### 2 By 2 Matrix

![[Minor of 2 by 2 Matrix Example.png | 500]]

### 3 By 3 Matrix

![[Minor of 3 by 3 Matrix Example.png | 890]]

## Determinant of Matrices - Without Co-Factor

>[!note]
>- Determinant is **Unique**
>- When determinant is equal to $0$, the matrix is said to be a *singular matrix*

### 2 By 2 Matrix

This is simple, we have been doing this since Grade 10.

Consider this Matrix below $\downarrow$:

$$
A = 
\begin{pmatrix}  
a & b \\  
c & d   
\end{pmatrix}
$$

The Determinant of the above matrix is given by:

$$
| A | = ( a \times d ) - ( c \times d )
$$

>This is what we learned in the lower classes and this is <span style="color: green;"><em>good</em></span>!
>But in University; they are using another method to find the *Determinant* and that method requires us to know **Co-Factor**
>*We will get to that later $\downarrow$*

### 3 By 3 Matrix

>Again this is method; I am doing it without using the "*Co-Factor*" method.

![[Determinant of 3 by 3 Matrix Example.png | 890]]

# Co-Factor of Matrix / Elements

A *Co-Factor* for any element is either the **minor** or the *opposite* of the **minor**, depending where the element is in the original **determinant**.
If the row and column of the element add up to be an even number, the the Co-Factor is the **same** as the *minor*. If the row and column add up to be an odd number, then the Co-Factor is the opposite of the minor.

>I did not understand a single thing, but I know I get it when I do it.
>But first, we need to understand that it the meaning of a **Sign Chart**

>[!tip] What is the point of finding the *Co-Factor*?
>The point of finding the Co-Factor of a matrix is to be able to find the **inverse** of that matrix
>Because we know that we can calculate the determinant of a 3 by 3 matrix **without** passing through the Co-Factor *method*.

## Sign Chart

A *Sign Chart* can be used instead of adding up the row and column of each of element.
It is either a $+$ or $-$ for each element in the matrix.
The first element ( *found at row 1 and column 1* ) is **always** a $+$ and it alternates from there.

### Sign Chart for 2 By 2 Matrix

$$
A = 
\begin{pmatrix}  
+ & - \\  
- & +   
\end{pmatrix}
$$

### Sign Chart for 3 By 3 Matrix

$$
\begin{pmatrix}  
+ & - & + \\
- & + & - \\
+ & - & + \\
\end{pmatrix}
$$

## Co-Factor of 2 By 2 Matrix

![[Co-Factor of 2 by 2 Matrix Example.png | 890]]

## Co-Factor of 3 By 3 Matrix

>It's basically the same as above $\uparrow$ but now with more elements / values.

![[Co-Factor of 3 by 3 Matrix Examples.png | 600]]

# Inverse of Matrix

The inverse of a matrix is the $\frac{1}{determinant} \times Adjoint$

$$
\Rightarrow A^{-1} = \frac{1}{| A |} \times Adjoint ( A )
$$

>[!tip] Steps to Calculate Inverse of Matrix
>1. Calculate Co-Factor of Matrix ( _hence, we need to calculate the Minor **before**_ )
>2. Calculate the Determinant **using** Co-Factor
>3. Transpose the Co-Factor
>4. Use Formula Given $\uparrow$

## Adjoint

It is the **transposition** of the *Co-Factor* of a Matrix

>We just [[Computational Mathematics - Matrices#Transpose of a Matrix | transpose]] the [[Computational Mathematics - Matrices#Co-Factor of Matrix / Elements | Co-Factor]] Matrix

## Example of Inverse of Matrix

![[Inverse of Matrix Example.png | 1000]]

---

# Simultaneous Equations with Matrices

>We are going to use most of the things that we used above $\uparrow$

## Example 1: Simple 2 Equations Simultaneous Equation

![[Matrix 2 by 2 Simultaneous Equation.png | 800]]

## Example 2: 3 Equations Simultaneous Equation

![[Matrix 3 by 3 Simultaneous Equation.png | 1000]]

>[!warning]
>I am a little mistake when finding the value of $z$
>I wrote $y$ twice $\uparrow \ \Rightarrow$ Check when calculating the value of $z$

---

# Socials

- **Instagram**:https://www.instagram.com/s.sunhaloo
- **YouTube**:https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg
- **GitHub**:https://www.github.com/Sunhaloo

---

S.Sunhaloo
Thank You!