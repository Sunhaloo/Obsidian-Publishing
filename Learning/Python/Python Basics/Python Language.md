---
Alias: Python Language / Basics
Tag: python, basics
Author: S.Sunhaloo
Type: Basics
Date: 2023-10-01
Status: Completed
---

## List of Contents

- [[Python Language#What is Python? | What is Python]]
	- [[Python Language#Creator of Python | Creator of Python]]
- [[Python Language#What can Python Do? | What can Python Do?]]

---

- [[Python Language#How to comment in Python | How to comment in Python]]
- [[Python Language#Type Cast | Type Cast]]
- [[Python Language#Displaying Things on the Screen | Display / Printing]]
	- [[Python Language#Strings | Strings]]
	- [[Python Language#Integers | Integers]]
	- [[Python Language#Floating Numbers / Decimal Numbers | Floating Numbers / Decimal Numbers]]
	- [[Python Language#Displaying All Data Types Together | Displaying All Data Types Together]]
- [[Python Language#Constants | Constants]]
- [[Python Language#Variables | Variables]]
- [[Python Language#Multiple Assignments | Multiple Assignments]]
- [[Python Language#Type Function | Type Function]]
- [[Python Language#User Inputs | User Inputs]]

---

### My Links

- [[Python Language#Socials | Link to Socials]]

---

# What is Python?

It is a **high-level language** designed for *general purpose* programming. It has an **emphasis** on *code readability* and makes use of *indentations*.

It supports many programming [paradigms](https://en.wikipedia.org/wiki/Programming_paradigm) like:

1. Procedural Programming
2. Object Oriented Programming
3. Functional Programming

Python is really popular and ranks among the most used programming languages every time.

> The last sentence was a bit biased :) !

## Creator of Python

**Name:** [Guido van Rossum](https://en.wikipedia.org/wiki/Guido_van_Rossum)
**Created At:** Centrum Wiskunde & Informatica ( CWI ) in Netherlands
**Created On:** 20 February 1991
# What can Python do?

Python can do a lot of things; from simple programming to most complex and illegal tasks.

Example includes:

- Build Websites
- Automation of Tasks
- Data Analysis / Data Science
- Hacking
	- Crack Passwords
	- Key logging
	- Sniffing
	- Scripts

---

# How to comment in Python

To comment a line in Python, we need to use the symbol

>[!tip] Usage
>```python
># This is a comment!
>```

To comment multiple lines in Python, we will use:

>[!tip] Usage
>```python
>'''
>This is a multi-line comment
>'''
>```
>>[!note]
>>Python does **not** really have multi-line comments.

# Type Cast

This is used to **convert** data types.

> Why am I doing this first? You make ask yourself this question.
> Trust me, I know what I am doing; Trust... I trust you ( '_' )

## Example:

- Displaying numbers with text
- Displaying boolean values with normal strings

## Converting Data Types

To convert those pesky data types so that we can "*print*" all of the data types together

>[!tip] Usage
>```python
>str()
>int()
>float()

> We will now move on to the rest of the notes and come back to this later
> Try to read the notes sequentially; it will make more sense: TRUST ME ( >_< )

# Displaying Things on the Screen

To display "*things*" on the screen; its very simple look; you just need to press these keys on the ( mechanical? ) keyboard: "p r i n t ()"

>[!tip] Usage
>To print "*stuff*" on the damn screen  ( or tablet screen, because we are pros and use **termux** on tablets )
>Use the *built-in* function below
>```python
>print()

## Example:

### Strings

To outputs "*strings*" ( you naughty naughty 🤣 ). We need to place them in between **quotes**.

```python

# Display Strings

print("Your Mom")

print("Kawasaki-H2/H2R")

print("Mazda RX-7 Rotary / Dorito Goodness!")

```

### Integers

To display integers on the screen, we do **not** need to put them in between quotes.

```python

# Display Integers

print(1234)

print(55)

print(1000000)

print(0)

```

### Floating Numbers / Decimal Numbers

To "*write*" decimal numbers in python. We just need to type them as [[Python Language#Integers | integers]]

```python

# Display Decimal Numbers

# Examples

# Display "1.2"
print(1.2)

# Display "6.9"
print(6.9) # Hmmm

# Display "1.2200901267"
print(1.2200901267)

```

## Displaying All Data Types Together

### Method 1: Using **[[Python Language#Type Cast | Type Cast]]**

```python

# Displaying "things" with different data types

print("Age: " + str(55))

print("Lucky Number = " + str(666))

print("I am " + str(18) + " of age!")

```

>[!note]
>The symbol `+` and `,` are used to **concatenate** 2 data types together.

### Method 2: Using the "*f*" function

Here, we do **not** need to convert those data types, but we need to use `{}` and place the *other* data type inside.

```python

# Displaying variables of different data types

# DECLARE Age: OF INTEGER
Age = 55

# DECLARE Boolean: OF BOOLEAN
Boolean = True

# DECLARE num: OF REAL
num = 6.2

# Displaying To Screen
print(f"Your Number is {5}")

print(f"Age: {Age}")

print(f"I am bad at talking to people: {Boolean}")

print(f"Research has shown that crime rate has decreased by {num} %")

```

# Constants

>[!warning] 
>Python does not have Declaration!
>Instead we use *CAPTIAL* Letters to indicate that something is a **constant**

```python

# Constants

# Strings

# DECLARE NAME: STRING
NAME = "What is my name?"
# DECLARE FAV_CAR: STRING
FAV_CAR = "RX-7 FD"

# Integers

# DECLARE AGE: INTEGER
AGE = 100
# DECLARE FIVE: INTEGER
FIVE = 5

# Floating Points / Decimal Numbers

# DECLARE PI: REAL
PI = 3.142
# DECLARE NUM: REAL
NUM = 6.69

# Booleans

# DECLARE PURCHASED_CAR: BOOLEAN
PURCHASED_CAR = False
# DECLARE CAUGHT: BOOLEAN
CAUGHT = True

```

# Variables

>[!warning]
>Again, we know that we cannot ( *do not* ) have Declaration in Python.
>But we do not need to write in caps for variables. It can be anything.
>But beware; your variables needs to be self-explanatory.
>>You will thank yourself if you use self-explanatory variables / constants names.

```python

# Variables

# DECLARE name: STRING
name = "Lewis GOAT Hamilton"

# DECLARE number: INTEGER
number = 44

# DECLARE activated: BOOLEAN
activated = True

# DECLARE temp: DOUBLE
temp = 30.2

```

# Multiple Assignments

This is basically assigning multiple values all at once in a single line instead of writing it on different lines.

> I personally like to write it on different lines because of something called *OCD* :)

# Usage / Example

```python

# Multiple Assigment

# How to I put this. Nah, just look at it for yourself as it is easy
x = y = z = "What!"

# Another Way - For me, I see this as ACTAUL Multiple Assigment
pi, number_five, Boolean, text = 3.142, 5, True, "Hello"

```

# Type Function

>[!tip] Usage
>To find the data type of a "*thing*" ( -_- )
>```python
>type()
>```

## Example: Find the Data Type of Variable / Constant

```python

# Type Function

# DECLARE num: INTEGER
num = 5

# Shows the "type" of variable `num`
print(type(num))

# DECLARE name: STRING
name = str(input("Please Enter Your Name: "))

# Shows the "type" of variable `name`
print(type(name))

```

# User Inputs

>[!note]
>In Python, we can ask the user to enter data into the program.
>For this, you can use the function below $\downarrow$:
>```python
>input()

```python

# User Inputs

# DECLARE array_size: INTEGER
array_size = int(input("Please Enter Size Of Array: "))

# DECLARE Name: STRING
Name = input("Please Enter Your Name: ")

# DECLARE find_item: INTEGER
find_item = int(input("Please Enter An Item To Find: "))

```

>[!warning]
>This built-in function will take the user input as "**strings**".
>Meaning that if we need to enter integer values, we need to **convert** it to integer using [[Python Language#Type Cast | type cast]] methods. Like we did with `array_size` and `find_item` $\uparrow$.
---

# Socials

- [**Instagram**](https://www.instagram.com/s.sunhaloo/)
- [**YouTube**](https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg)
- [**GitHub**](https://www.github.com/Sunhaloo)

---

S.Sunhaloo
Thank You!