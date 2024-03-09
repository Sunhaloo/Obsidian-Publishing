---
Alias: Random Module Python
Tag: python, basics, python_module
Author: S.Sunhaloo
Type: Module
Date: 2023-10-15
Status: Completed
---

## List of Contents

- [[Random Module - Python#What is the Random Module used for?| What is the Random Module used for?]]
	- [[Random Module - Python#Importing Random Module| Importing Random Module]]
- [[Random Module - Python#Displaying Random Numbers| Displaying Random Numbers]]
	- [[Random Module - Python#Example Displaying 5 Random Number between 0 and 1| Example of Displaying Random Numbers ( b/w 0 and 1 )]]
- [[Random Module - Python#Displaying Random Number in Desired Range| Displaying Random Number in Desired Range]]
	- [[Random Module - Python#Example Displaying 2 Random Number in Specific Range| Example of Displaying Random Numbers in Specific Range]]
- [[Random Module - Python#Displaying Random Item from an Array| Displaying Random Item from an Array]]
	- [[Random Module - Python#Example Displaying A Random Item found in an Array| Example of Displaying a Random Item from an Array]]
- [[Random Module - Python#Shuffling An Array| Shuffling An Array]]
	- [[Random Module - Python#Example Shuffling An Array| Example of Shuffling an Array]]

---

My Links

- [[Random Module - Python#Socials| Links to Socials]]

---

# What is the Random Module used for?

The random module ( part of the [[Modules - Python| module]] notes ); is used to generate random number, shuffle data and more. It is basically used to perform *random* things :)

## Importing Random Module

>[!warning]
>Here it is **necessary** to import the random module as we will be using it constantly

>Not like in [[Text Files]], where even though we imported the OS Module. We did not use it every time.

# Displaying Random Numbers

Just as the title says, this function below will allow you to create a random number between **0** to **1**.

>[!tip] Usage
>```python
>random.random()
>```

>[!note]
>We will need to convert the "*random.random*" function into **string** data type as if we do **not**; it will return value with the *float* data type

## Example: Displaying 5 Random Number between 0 and 1

```python

# "random.random" Function

# Importing "random" Module
import random

print()

# DECLARE random_num: OF STRING
random_num = str(random.random())

print("Displaying 5 Random Number Between 0 and 1")
print()

# Displaying 5 Random Numbers
for x in range(5):

    print()
    print("Random Number " + str(x) + ": " + random_num)

```

# Displaying Random Number in Desired Range

This will allow to user to choose from *between* which values ( **inclusive** ). Thus, we are not stuck with the value in between 0 and 1

>[!tip] Usage
>```python
>random.randint(x, y)
>```
>Where "*x*" is an:
>- Integer
>- Start Value
>
>Where "*y*" is an:
>- Integer
>- End Value
>
>>[!note]
>>The values of *x* and *y* are **inclusive**

## Example: Displaying 2 Random Number in Specific Range

```python

# "random.randint" Function

# Importing "random" Module
import random

print()
print("Displaying 2 Random Number Between 1 and 6")
print()

# Displaying 2 Random Numbers
for x in range(2):

    print()
    print("Random Number " + str(x) + ": " + str(random.randint(1, 6)))

```

# Displaying Random Item from an Array

This will allow us to display and item *randomly* found **inside** the array.

>[!tip] Usage
>```python
>random.choice(x)
>```
>Where "*x*" is an:
>- Array

## Example: Displaying A Random Item found in an Array

```python

# "random.choice" Function

# Importing "random" Module
import random

print()

# DECLARE array: ARRAY[2] OF INTEGER
array = ["rock", "paper", "scissors"]

# Displaying Output
print("Output: " + str(random.choice(array)))

```

# Shuffling An Array

This will shuffle / move the contents **inside** an array *randomly*.

>[!tip] Usage
>```python
>random.shuffle(x)
>```
>Where "*x*" is an:
>- Array

## Example: Shuffling An Array

```python

# "random.shuffle" Function

# Importing "random" Module
import random

print()

# DECLARE car: ARRAY[2] OF INTEGER
car = ["Evo 9", "EG-6", "Supra MK4", "E46 M3", "R32 GTR", "Mazda 787B"]

# Suffling The Array

# This is not used inside a "print()" function
# This is because it changes the contents of array "car"
random.shuffle(car)

# Displaying Output
print(car)

```

>[!note]
>This function ( "*random.shuffle*" ) will shuffle the contents of the array.
>It will **not** output anything if you write:
>```python
>print(random.shuffle(array))
>```
>This returns:
>```python
>None
>```

---

# Socials

- [**Instagram:**](https://www.instagram.com/s.sunhaloo/)
- [**YouTube:**](https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg)

---

S.Sunhaloo
Thank You!