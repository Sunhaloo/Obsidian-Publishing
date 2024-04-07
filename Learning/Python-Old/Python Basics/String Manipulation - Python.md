---
Alias: Python String Manipualation
Tag: python, basics
Author: S.Sunhaloo
Type: String Manipulation
Date: 2023-10-01
Status: Completed
---

# List of Contents

- [[String Manipulation - Python#String Manipulation | String Manipulation]]
	- [[String Manipulation - Python#Length Function | Length Function]]
		- [[String Manipulation - Python#Example Just Finding the Length of things | Example of Length Function]]
	- [[String Manipulation - Python#Find Function | Find Function]]
		- [[String Manipulation - Python#Example Find the address of characters in these variables | Example of Find Function]]
	- [[String Manipulation - Python# Capitalize Function | Capitalise Function]]
		- [[String Manipulation - Python#Example "*Capitaling*" the first letter of some strings | Example of Capitalize Function]]
	- [[String Manipulation - Python#Upper Function | Upper Function]]
		- [[String Manipulation - Python#Example "*Capitalising*" the **whole** string | Example of Upper Function]]
	- [[String Manipulation - Python#Lower Function | Lower Function]]
		- [[String Manipulation - Python#Example "*Un-capitalising*" a string | Example of Lower Function]]
	- [[String Manipulation - Python#Digit Function | Digit Function]]
		- [[String Manipulation - Python#Example Checking if a *string* is a digit | Example Digit Function]]
	- [[String Manipulation - Python#Alpha Function | Alpha Function]]
		- [[String Manipulation - Python#Example Checking if *string* is an "*alphabet*" | Example of Alpha Function]]
	- [[String Manipulation - Python#Count Function | Count Function]]
		- [[String Manipulation - Python#Example Counting a letter in a *string* | Example of Count Function]]
	- [[String Manipulation - Python#Replace Function | Replace Function]]
		- [[String Manipulation - Python#Example Replacing some *letter* in some *string* | Example of Replace Function]]
	- [[String Manipulation - Python#Index Function | Index Function]]
		- [[String Manipulation - Python#Example Man handling some words | Example of Index Function]]
	- [[String Manipulation - Python#Slice Function | Slice Function]]
		- [[String Manipulation - Python#Example Slicing like a ninja | Example of Slice Function]]

Probably the most important

- [[String Manipulation - Python#Input Function | Input Function]]
	- [[String Manipulation - Python#Example "*Casually inputting*" some data into program | Example of Input Function]]

---

My Links

- [[String Manipulation - Python#Socials | Links to Socials]]

---

# String Manipulation

To be honest, these are those thing that need be shown how it works first, then that bulbs lights up in your tiny brain :)

Sooo... Lets Start my *Bruddas*!

---

## Length Function

First up on our list is the mighty length function. There are many use cases where one might need ( "*must*" ) use the **length** function.

>[!tip] Usage
>```python
>len(x)
>```
>Where "*x*" could be:
>- String
>- Constant
>- Array

>[!warning]
>" " ( **space** ) is also a *character*; Thus the function will count "*space*"

### Example: Just Finding the Length of things

```python

# Length Function

print()

# String Data Types

# DECLARE name: OF STRING
name = "Toto Woolff"

# Outputs the length of "name"
print("Length of Toto Woolff: " + str(len(name)))
print()

# DECLARE name_2: OF STRING
name_2 = "Lewis Hamilton"

# DECLARE name_2_length: OF INTEGER
name_2_length = len(name_2)

# Outputs the length of "name_2"
print("Length of Lewis Hamilton: " + str(name_2_length))
print()

# Arrays

# DECLARE array: OF ARRAY[0:4] OF INTEGER
array = [1, 2, 3, 4, 5]

# Outputs the length of "array"
print("Length of array: " + str(len(array)))
print()

# Integer Numbers

# DECLARE number: OF INTEGER
number = 1234

# Output the length of number
print("Length of number:  " + str(len(str(number))))
print()

```

>[!note]
>Look at "*Integer Numbers*"
>The "*len()*" function will find the *length* of **integer numbers**
>Thus, we need to convert the **constant** *number* to *string*
>Then when we *print*, we need to convert the *len()* function to **string** as the data type of *len()* is **integer**
>Hence,
>```python
>str(len(str(number)))
>```

## Find Function

So this is used to find the **address** of a *specific character* in a **string**.
Remember that this function does **not** work on *integers* and *floating point numbers*.

>[!tip] Usage
>```python
>x.find("y")
>```
>Where "*x*" is a:
>- String
>
>Where "y" is the:
>- Character that needs to be found ( *its address* )

>[!warning]
>1. " " ( **space** ) is also a *character*; Thus the function can also find "*space*"
>2. The "*find*" function will only accept data of **string** data type

>[!note]
>The "*find*" function will **only** take *string* data types
>But it will return an *integer* data type
>This is why in the examples below, you will see that I have converted the "*find*" into **string** in the "*print*" function

### Example: Find the address of characters in these variables

```python

# Find Function

# DECLARE F1_Car: OF STRING
F1_Car = "W11"

# Find "W" in "F1_Car"
print()
print("Find W in W11")

print("Address: " + str(F1_Car.find("W")))

# DECLARE name: OF STRING
name = "BONO"

# Find "O" in "name"
find_N = name.find("N")

print()
print("Find N in BONO")

print("Address: " + str(find_N))

# DECLARE number: OF INTEGER
number = 1234

# Find "3" in "number"
# Need to convert as "number" is of type "integer"

print()
print("Find 3 in 1234")

print("Address: " + str(str(number).find("3")))

# DECLARE cash: OF REAL
cash = 100.78

# Convert "cash" into string
cash_str = str(cash)

# Find "." in "cash.str"
print()
print("Find . in 100.78")

print("Address: " + str(cash_str.find(".")))

```

## Capitalize Function

What does the "*capitalize*" function do? Ohh Yes! It will capitalise **only one** letter / character in a *string*... What did you think it would have done? "*Capitalise*" the whole string. Sucks on you; **it does not!**

>[!tip] Usage
>```python
>x.capitalize()
>```
>Where "*x*" is a:
>- String

### Example: "*Capitalising*" the **first** letter of some strings

```python

# Capitalize Function

# DECLARE name: OF STRING
name = "charles"

# Will "capitalise" the first letter of variable "name"
full_name = name.capitalize()

# Displaying full name
print()
# Not need to convert to "string" because it was already a "string"
print("Full Name: " + full_name)

# DECLARE moto: OF STRING
moto = "kawasaki"

# Displaying variable "moto" with capital "k"
print()
# Not need to convert to "string" because it was already a "string"
print("Make: " + moto.capitalize())

```

>[!warning]
>It will only "*capitalise*" **only** one word in a string
>For Example:
>- If we have to "*capitalise*" "*k*" in "*kawasaki H2R*"
>- It will obviously "*capitalise*" the "*k*"
>- But it will make the other word / string **lower case**
>- Outputs:
>	- **K**awasaki **h2r**

## Upper Function

This function is not like the "*Capitalize*" function. Because this one is not a fool and will actually "*capitalise*" the **whole** string.

### Example: "*Capitalising*" the **whole** string

```python

# Upper Function

# DECLARE name: OF STRING
name = "Carlos Sainz"

# Will "capitalise" the first letter of variable "name"
cap_name = name.capitalize()

# Displaying capitalise name
print()
# Not need to convert to "string" because it was already a "string"
print("Capitalised Name: " + cap_name)

# DECLARE moto: OF STRING
moto = "kawasaki H2R"

# Displaying the variable "moto" with every letter being CAPITAL letters
print()
# Not need to convert to "string" because it was already a "string"
print("Make + Model: " + moto.upper())

```

>[!note]
>This time we do not have the problem of "H2R" being "*capitalised*".

## Lower Function

This will take a "*capital string*" and turns it into a "*un-capital string*" \\
\\_ _(^-^)_ _/

What else can I say... Nothing!

>[!tip] Usage
>```python
>x.lower()
>```
>Where "*x*" is a:
>- String

### Example: "*Un-capitalising*" a string

```python

# Lower Function

# DECLARE name: OF STRING
name = "NICHOLAS LATIFI"

# "Un-capitalising" the variable "name"
uncap_name = name.lower()

# Displaying the varibale "uncap_name"
# No need to convert to "string" as it is already a "string"
print()
print("Name: " + uncap_name)

# DECLARE ferrari: OF STRING
ferrari = "SHITBOX"

# "Un-capitalising" the variable "ferrari"
print()
# Displaying the variable "ferrari"
print("Ferrari = " + ferrari)

```

## Digit Function

"*Is it a digit?*" That is the question to ask yourself when the user enters a value.

Basically this is used to check a **string** contains *numbers* or *not*.

>[!tip] Usage
>```python
>x.isidigit()
>```
>Where "*x*" is a:
>- String

### Example: Checking if a *string* is a digit

```python

# Digit Function

# DECLARE string: OF STRING
string = "Not A Number"

# DECLARE number: OF STRING
number = "1234"

print()

# Checking if variable "string" is a digit
# DECLARE is_string_digit: OF STRING
is_string_digit = string.isdigit()
print("Is string a Digit: " + str(is_string_digit))

# Checking if variable "number" is a digit
print("Is number a Digit: " + str(number.isdigit()))

```

## Alpha Function

This function will check if the variable is a "*string*". But there are some exceptions even for **strings**.

>[!tip] Usage
>```python
>x.isalpha()
>```
>Where "*x*" is a:
>- String

### Example: Checking if *string* is an "*alphabet*"

```python

# Alpha Function

# DECLARE num: OF STRING
num = "1234"

# DECLARE is_alpha_num: OF STRING
is_alpha_num = num.isalpha()

print()

# Checking if variable "num" is an alphabet
print("Is num Alphabet: " + str(is_alpha_num))

# DECLARE Ferrari_Principal: OF STRINg
Ferrari_Principal = "FrédéricVasseur"

# Checking is variable "Ferrari_Principal" is an alphabet
print("Is Ferrar_Principal: " + str(Ferrari_Principal.isalpha()))

```

>[!warning] This does not count as "*Alphabet*"
>```python
># DECLARE Williams_Principal: OF STRING
>Williams_Principal = "James Vowles"
>
># DECLARE Alpine_Principal: OF STRING
>Alpine_Pricipal = "Otmar.Szafnauer"
>
>print()
>
># These will return "False"
>print("Williams_Principal: " + str(Williams_Principal.isalpha()))
>print("Williams_Principal: " + str(Alpine_Pricipal.isalpha()))
>```
>These will return the Boolean Value "*False*" becasuse of:
>1. There are **spaces**
>2. There are **periods** ( $.$ )

## Count Function

"*Do you know how to count mate?*" Yes, this function will count a "*letter*" in a **string**.

>[!tip] Usage
>```python
>x.count("y")
>```
>Where "*x*" is a:
>- String
>
>Where "*y*" is a:
>- String

### Example: Counting a letter in a *string*

```python

# Count Function

# DECLARE name: OF STRING
name = "Alex Albon"

# DECLARE Find_A: OF STRING
Find_A = "A"

print()

# Counting how many "A" are there in variable "name"
print(name.count(Find_A))

# DECLARE Air: OF STRING
Air = "bubble"

# Counting how many "b" are there in variable "Air"
print(Air.count("b"))

```

## Replace Function

This is used to replace a **letter** that is found in a **string**. We will then replace *that* letter with another **letter**.

>[!tip] Usage
>```python
>x.count("y", "z")
>```
>Where "*x*" is a:
>- String
>
>Where "*y*" is a:
>- String
>	- This is the letter found in the string ( needs to be replaced )
>
>Where "*z*" is a:
>- String
>	- This is the letter we will be replacing "*y*" with

### Example: Replacing some *letter* in some *string*

```python

# Replace Function

# DECLARE text: OF STRING
text = "Hell1 W1rld"

print()

# Replacing "1" with "o" in variable "text"
print(text.replace("1", "o"))

# DECLARE car: OF STRING
car = "Rimoc"

# Replacing "o" with "a" in variable "car"
print(car.replace("o", "a"))

```

## Input Function

This is probably the most important function. Then why did I place it here; Cause I am dumb!

>[!tip] Usage
>```python
>x.input("y")
>```
>Where "*x*" is a:
>- String
>
>Where "*y*" is a:
>- Text Presented to user

### Example: "*Casually inputting*" some data into program

```python

# Input Function

# DECLARE name: OF STRING
name = input("Please Enter Your Name: ")

# DECLARE car: OF STRING
car = input("Please Enter Your Favourite Car: ")

print()

# Displaying the Output
print(name)
print(car)

```

>[!note]
>The **input function** will be of type string.

## Index Function

This is to "*remove*"; to be able to get certain ( amount ) of letters in a string.
Basically, we can do things like take a work in the middle of a sentence or even reverse the order of the words

>[!tip] Usage
>```python
>x[]
>x[start:end:step]
>```
>The **start**: starts with *0* ( **inclusive** )
>The **end**: starts with *1* ( **exclusive** )
>The **step** is the *funky one*

### Example: Man handling some words

```python

# Index Function

# DECLARE word: OF STRING
word = "Nothing Just Typing"

# DECLARE first_word: Of STRING
first_word = word[0:8]

# DECLARE last_word: OF STRING
last_word = word[13:19]

# DECLARE funky_word: OF STRING
funky_word = word[::2]

# DECLARE reversed_word: OF STRING
reversed_word = word[::-1]

print()

print("First Word: " + first_word)

print()

print("Last Word: " + last_word)

print()

print("Funky Word: " + funky_word)

print()

print("Reversed Word: " + reversed_word)

```

## Slice Function

This is basically the same thing as the [[String Manipulation - Python#Index Function | index function]]. But we write it differently and it is actually a built-in function.

Also, as this is an actual function, we can re-use it somewhere else.

>[!tip] Usage
>```python
>x[slice(start, end, step)]
>```
>The **start**: starts with *0* ( **inclusive** )
>The **end**: starts with *1* ( **exclusive** )
>The **step** is the *funky one*

>[!warning]
>We do not use "*:*", but we instead use "*,*".

### Example: Slicing like a ninja

```python

# Slice Function

# DECLARE website: OF STRING
website = "https://instagram.com/s.sunhaloo"

# DECLARE car: OF STRING
car = "Mazda RX-7"

# DECLARE reversed_car: OF STRING
reversed_car = slice(0, 10)

# Displaying the results
print("Instagram: " + website[slice(8, -11)])

print("Car: " + car[reversed_car])

```

---

# Socials

- [**Instagram:**](https://www.instagram.com/s.sunhaloo/)
- [**YouTube:**](https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg)

---

S.Sunhaloo
Thank You!