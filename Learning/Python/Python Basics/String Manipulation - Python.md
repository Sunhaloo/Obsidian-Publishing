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


>[!warning]
>" " ( **space** ) is also a *character*; Thus the function will count "*space*"

### Example: Just Finding the Length of things

```python

# Length Function

print()

# String Data Types

# DECLARE name: STRING
name = "Toto Woolff"

# Outputs the length of "name"
print(f"Length of Toto Woolff: {len(name)}")
print()

# DECLARE name_2: STRING
name_2 = "Lewis Hamilton"

# DECLARE name_2_length: INTEGER
name_2_length = len(name_2)

# Outputs the length of "name_2"
print("Length of Lewis Hamilton: {name_2_length}")
print()

# Arrays

# DECLARE ARRAY array: INTEGER
array = [1, 2, 3, 4, 5]

# Outputs the length of "array"
print("Length of array: {len(array)}")
print()

# Integer Numbers

# DECLARE number: INTEGER
number = 1234

# Output the length of number
print(f"Length of number:  {len(number)}")
print()

```

## Find Function

So this is used to find the **address** of a *specific character* in a **string**.

>[!note]-
>Remember that this function does **not** work on *integers* / *floating point numbers* or *arrays*.

>[!tip] Usage
>```python
>x.find("y")
>```

>[!warning]
>" " ( **space** ) is also a *character*; Thus the function can also find "*space*"

### Example: Find the address of characters in these variables

```python

# Find Function

# DECLARE F1_Car: STRING
F1_Car = "W11"

# Find "W" in "F1_Car"
print()
print("Find W in W11")
print(f"Address: {F1_Car.find("W")}")

# DECLARE name: STRING
name = "BONO"

# Find "N" in "name"
find_N = name.find("N")

print()
print("Find N in BONO")
print(f"Address: {find_N}")

# DECLARE number: INTEGER
number = 1234

# Find "3" in "number"
# Need to convert as "number" is of type "integer"

print()
print("Find 3 in 1234")
print(f"Address: {str(number).find("3")}")

# DECLARE cash: REAL
cash = 100.78

# Find "." in "cash.str"
print()
print("Find '.' in 100.78")
print(f"Address: {str(cash).find(".")}")

```

## Capitalize Function

What does the "*capitalize*" function do? Ohh Yes! It will capitalise **only one** letter / character in a *string*... What did you think it would have done? "*Capitalise*" the whole string. Sucks on you; **it does not!**

>[!tip] Usage
>```python
>x.capitalize()
>```

### Example: "*Capitalising*" the **first** letter of some strings

```python

# Capitalize Function

# DECLARE name: STRING
name = "charles"

# DECLARE full_name: STRING
# Will "capitalise" the first letter of variable "name"
full_name = name.capitalize()

# Displaying full name
print()
print(f"Full Name: {full_name}")

# DECLARE moto: STRING
moto = "kawasaki"

# Displaying variable "moto" with capital "k"
print()
print(f"Make: {moto.capitalize()}")

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

# DECLARE name: STRING
name = "Carlos Sainz"

# Will "capitalise" the first letter of variable "name"
cap_name = name.capitalize()

# Displaying capitalise name
print()
print(f"Capitalised Name: {cap_name}")

# DECLARE moto: STRING
moto = "kawasaki H2R"

# Displaying the variable "moto" with every letter being CAPITAL letters
print()
print(f"Make + Model: {moto.upper()}")

```

>[!note]
>This time we do not have the problem of "H2R" being "*capitalised*".

## Lower Function

This will take an **uppercase** string and turns it into a **lowercase** string.

What else can I say... Nothing!

>[!tip] Usage
>```python
>x.lower()
>```

### Example: "*Un-capitalising*" a string

```python

# Lower Function

# DECLARE name: STRING
name = "NICHOLAS LATIFI"

# DECLARE uncap_name: STRING
# "Lowering" the variable "name"
uncap_name = name.lower()

# Displaying the varibale "uncap_name"
print()
print(f"Name: {uncap_name}")

# DECLARE ferrari: STRING
ferrari = "SHITBOX"

print()
# "Lowering" and Displaying the variable "ferrari"
print(f"Ferrari = {ferrai.lower()}")

```

## Digit Function

"*Is it a digit?*" That is the question to ask yourself when the user enters a value.

Basically this is used to check a **string** contains *numbers* or *not*.

>[!tip] Usage
>```python
>x.isidigit()
>```

### Example: Checking if a *string* is a digit

```python

# Digit Function

# DECLARE string: STRING
string = "Not A Number"

# DECLARE number: STRING
number = "1234"

print()

# DECLARE is_string_digit: STRING
is_string_digit = string.isdigit()

# Checking if variable "string" is a digit
print(f"Is `string` a Digit? {is_string_digit}")

# Checking if variable "number" is a digit
print("Is `number` a Digit? {number.isdigit()}")

```

## Alpha Function

This function will check if the variable is a "*string*". But there are some exceptions even for **strings**.

>[!tip] Usage
>```python
>x.isalpha()
>```

### Example: Checking if *string* is an "*alphabet*"

```python

# Alpha Function

# DECLARE num: STRING
num = "1234"

# DECLARE is_alpha_num: STRING
is_alpha_num = num.isalpha()

print()

# Checking if variable "num" is an alphabet
print(f"Is `num` Alphabet: {is_alpha_num}")

# DECLARE Ferrari_Principal: STRING
Ferrari_Principal = "FrédéricVasseur"

# Checking is variable "Ferrari_Principal" is an alphabet
print(f"Is Ferrar_Principal: {Ferrari_Principal.isalpha()}")

```

>[!warning] This does not count as "*Alphabet*"
>```python
># DECLARE Williams_Principal: STRING
>Williams_Principal = "James Vowles"
>
># DECLARE Alpine_Principal: STRING
>Alpine_Pricipal = "Otmar.Szafnauer"
>
>print()
>
># These will return "False"
>print(f"Williams_Principal: {Williams_Principal.isalpha()}")
>print(f"Williams_Principal: {Alpine_Pricipal.isalpha()}")
>```
>These will return the Boolean Value "*False*" becasuse of:
>1. There are **spaces**
>2. There are **periods** ( $.$ )

## Count Function

"*Do you know how to count mate?*" Yes, this function will return the number of times a *character* has appeared in a **string**.

>[!tip] Usage
>```python
>x.count("y")
>```

### Example: Counting a letter in a *string*

```python

# Count Function

# DECLARE name: STRING
name = "Alex Albon"

# DECLARE Find_A: STRING
Find_A = "A"

print()

# Counting how many "A" are there in variable "name"
print(name.count(Find_A))

# DECLARE Air: STRING
Air = "bubble"

print()

# Counting how many "b" are there in variable "Air"
print(Air.count("b"))

```

## Replace Function

This is used to replace a **letter** that is found in a **string**. We will then replace *that* letter with *another* letter.

>[!tip] Usage
>```python
>x.count("y", "z")
>```
### Example: Replacing some *letter* in some *string*

```python

# Replace Function

# DECLARE text: STRING
text = "Hell1 W1rld"

print()

# Replacing "1" with "o" in variable "text"
print(text.replace("1", "o"))

# DECLARE car: STRING
car = "Rimoc"

print()

# Replacing "o" with "a" in variable "car"
print(car.replace("o", "a"))

```

## Index Function

This is to "*remove*"; to be able to get certain ( amount ) of letters in a string.
Basically, we can do things like take a word in the middle of a sentence or even reverse the order of the words

>[!tip] Usage
>```python
>x[]
>x[start:end:step]
>```
>- The **start**: starts with *0* ( **inclusive** )
>- The **end**: starts with *1* ( **exclusive** )
>- The **step** is the *funky one*.

### Example: "Man-handling" some words

```python

# Index Function

# DECLARE word: STRING
word = "Nothing Just Typing"

# DECLARE first_word: STRING
first_word = word[0:8]

# DECLARE last_word: STRING
last_word = word[13:19]

# DECLARE funky_word: STRING
funky_word = word[::2]

# DECLARE reversed_word: STRING
reversed_word = word[::-1]

print()

print(f"First Word: {first_word}")

print()

print(f"Last Word: {last_word}")

print()

print(f"Funky Word: {funky_word}")

print()

print(f"Reversed Word: {reversed_word}")

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

# DECLARE website: STRING
website = "https://instagram.com/s.sunhaloo"

# DECLARE car: STRING
car = "7XR-adzaM"

# DECLARE sliced_location: STRING
sliced_location = slice(0, 10)

# Displaying the results
print(f"Instagram's URL: {website[slice(8, -11)]}")

print(f"Car: {car[sliced_location]}")

```

---

# Socials

- [**Instagram**](https://www.instagram.com/s.sunhaloo/)
- [**YouTube**](https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg)
- [**GitHub**](https://www.github.com/Sunhaloo)

---

S.Sunhaloo
Thank You!