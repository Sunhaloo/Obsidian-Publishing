---
Alias:
  - Python Language/Basics
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

- [[Python Language#How to Use Python for Simple Programming? | How to Use Python for Simple Programming?]]
	- [[Python Language#How to comment in Python | How to comment in Python]]
	- [[Python Language#Type Cast | Type Cast]]
	- [[Python Language#Displaying Things on the Screen | Display / Printing]]
		- [[Python Language#Strings | Strings]]
		- [[Python Language#Integers | Integers]]
		- [[Python Language#Floating Numbers / Decimal Numbers | Floating Numbers / Decimal Numbers]]
		- [[Python Language#Displaying All Data Types Together | Displaying All Data Types Together]]
	- [[Python Language#Constants | Constants]]
		- [[Python Language#Constants that are *strings* | Strings]]
		- [[Python Language#Constants that are *integers* | Integers]]
		- [[Python Language#Constants that are *floating point numbers* | Floating Point Numbers]]
		- [[Python Language#Constants that are *boolean* | Boolean]]
	- [[Python Language#Variables | Variables]]
		- [[Python Language#User Entered Variables | User Entered Variables]]
	- [[Python Language#Finding the Data Type of an Item ( Constant / Variable ) | Finding the Data Type of an Item ( Constant / Variable )]]

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

# How to Use Python for Simple Programming?

# How to comment in Python

To comment a line in python, we need to use the symbol

>[!tip] Usage
>```python
>"#"

## Example:

```python

# This is a commented line
# This is another commented line
# Today we are definitely try to finish this PDF Documents
# Ohh God; Please Help Me!

```

>[!tip]- Remember
>A commented line ( Line that starts with "#" ) will not be compile; i.e,
>Will not doing anything when running/compiling the code.

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

>[!note]-
>To display "*nothing*" or an **empty line**
>Just need to use the function by itself, i.e;
>```python
>print()

## Example:

### Strings

To outputs "*strings*" ( you naughty naughty 🤣 ). We need to place them in between **quotes**.

```python

# Display Strings

# Examples

# Display "Your Mom"
print("Your Mom")

# Display "Kawasaki-H2/H2R"
print("Kawasaki-H2/H2R")

# Display the following message
# "Please Enter A Name: "
print("Please Enter A Name: ")

```

### Integers

To display integers on the screen, we do **not** need to put them in between quotes.

```python

# Display Integers

# Examples

# Display "1234"
print(1234)

#Display "55"
print(55)

# Display "1000000"
print(1000000)

# Display "0"
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

>[!tip] To display something like
>"Age: 55"
>Where "55" is of *type* integer

We **need** to convert the data types!

```python

# Displaying "things" of different data types

# Diplay "Age: 55"
print("Age: " + str(55))

# Display "Country Code is: MU255"
print("Country Code is: " + str(MU255))

# Display "I am 18 years of age!"
print("I am " + str(18) + " of age!")

```

>[!note]
>```python
>"+" # or
> ","
>```
>This is used to **concatenate** the 2 *data types* together.

### Method 2: Using the "*f*" function

Here, we do **not** need to convert those data types

```python

# Displaying variables of different data types

# DECLARE Age: OF INTEGER
Age = 55

# DECLARE Boolean: OF BOOLEAN
Boolean = True

# DECLARE num: OF REAL
num = 6.2

# Displaying Variables
print(f"Age: {Age}")

print(f"I am bad at talking to people: {Boolean}")

print(f"Research has shown that crime rate has decreased by {num} %")

```

# Constants

In short a

- **Constant** is something / value / item that does **not** change during the execution of the program

## Constants that are *strings*

```python

# Constants

# Constant "Name" will hold the value "What is my name?"
Name = "What is my name?"

# Constant "Fav_Car" will hold the value "RX-7 FD"
Fav_Car = "RX-7 FD"

```

## Constants that are *integers*

```python

# Constants

# Constant "age" will hold the value "100"
age = 100

# Constant "Five" will hold the value "5"
five = 5

```

## Constants that are *floating point numbers*

```python

# Constants

# Constant "pi" will hold the value "3.142"
pi = 3.142

# Constant "num" will hold the value "6.69"
num = 6.69

```

## Constants that are *boolean*

```python

# Constants

# Constant "Purchased_Car" will hold the booalean value "Flase"
Purchased_Car = False

# Constant "caught" will hold the boolean value "True"
caught = True

```

# Variables

 A **Variable** is something / value / item that **does** change during the execution of the program

## User Entered Variables

>[!note]
>In Python, we can ask the user to enter data into the program.
>For this, use can you this function below ( $\downarrow$ )
>```python
>input()

### Examples

```python

# Variables

# Variable "array_size" will hold the size of array ( ENTERED by user )
array_size = int(input("Please Enter Size Of Array: "))

# Variable "Name" will hold the name of the user ( ENTERED by user )
Name = input("Please Enter Your Name: ")

# Variable "find_item" will hold the value to be found ( ENTERED by user )
find_item = int(input("Please Enter An Item To Find: "))

```

>[!warning]
>This build-in function will take the user input as "**strings**".
>Meaning that if we need to enter integer values, we need to **convert** it to integer using [[Python Language#Type Cast | type cast]] methods

# Multiple Assignments

This is basically assigning multiple values all at once in a single line instead of writing it on different lines.

> I personally like to write it on different lines because of something called compulsion :)

# Usage / Example (  because I do not know how to call it )

```python

# Multiple Assigment

# How to I put this. Nah, just look at it for yourself as it is easy
x = y = z = "What!"

# Another Way - For me, I see this as ACTAUL Multiple Assigment
pi, number_five, Boolean, text = 3.142, 5, True, "Hello"

```

# Finding the Data Type of an Item ( Constant / Variable )

As you already know; in Python, we do **not** *declare* our constants or variables.

Think of it this way, if you give someone your code to fix or to check and you are not there. And you did not use meaningful ( self-explanatory ) variables. That person could then use this function ( please let me finish this before I show you, okay ) to find what "*type*" the variable is of.

>[!tip] Usage
>To find the data type of a "*thing*" ( -_- )
>```python
>type()
>```
>You  then place the constant / variable in the brackets

See your patience was *definitely not  worth it*

## Example

```python

# Type Function

# Lets say we have constant "number" which has a value of "44"
number = 5

# This "code" will then show the "type" of "number"
print(type(number))

#Variable "name" will hold the value entered by user
name = str(input("Please Enter Your Name: "))

# Therefore,
print(type(name))

```

# Data Types ( String, Integers, Floating Point Numbers, Boolean )

In my old notes, I showed you ( myself - I do not have any friends; xD - I do ). I wrote ways how to **write** and *print* these data types.

But I think that, when you use Python, you will know how to write and use them ( ***obviously*** )

But there is a few things that I want to mention.

>[!warning]
>You cannot perform addition with **strings**
>```python
>one = "1"
>two = "2"
>total = one + two
>print(total)
>```
>**This will not output 3!**
>Instead it will output
>```python
>12 # Not 3

---

# Socials

- [**Instagram:**](https://www.instagram.com/s.sunhaloo/)
- [**YouTube:**](https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg)
- [**GitHub:**](https://www.github.com/Sunhaloo)

---

S.Sunhaloo
Thank You!