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
- [[Random Module - Python#Displaying Integer Random Number | Displaying Integer Random Number]]
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
>Here it is **necessary** to import the random module to be able to use the following functions below $\downarrow$.

>Not like in [[Text Files - Python]], where even though we imported the OS Module. We did not use it every time.

# Displaying Random Numbers

Just as the title says, this function below will allow you to create a random number between **0** to **1**.

>[!tip] Usage
>```python
>import random
>```
>>[!note]-
>>We can can also change the way we use the random module
>>```python
>>import random as rd
>># Hence, we can use it like so
>>rd.random()
>>```


## Example: Displaying 5 Random Number between 0 and 1

```python

import random

print()

# DECLARE random_num: FLOAT
random_num = random.random()

print("Displaying 5 Random Number Between 0 and 1")
print()

# DECLARE x: INTEGER
# Displaying 5 Random Numbers
for x in range(5):

    print()
    print(f"Random Number {x} = {random_num}")

```

# Displaying Integer Random Number

This function will allow the user to set a specific number in a range ( **inclusive** ). The function will then choose a random number from that range.

>[!tip] Usage
>```python
>random.randint(x, y)
>```
>>[!note]-
>>The values of *x* and *y* are **inclusive**

## Example: Displaying 2 Random Number in Specific Range

```python

import random

print()
print("Displaying 2 Random Number Between 1 and 6")
print()

# DECLARE x: INTEGER
# Displaying 2 Random Numbers
for x in range(2):

    print()
    print(f"Random Number {x} = {random.randint(1, 5)}")

```

# Displaying Random Item from an Array

This will allow us to display and item *randomly* found **inside** the array.

>[!tip] Usage
>```python
>random.choice(x)
>```

## Example: Displaying A Random Item found in an Array

```python

import random

print()

# DECALRE ARRAY array[2]: INTEGER
array = ["rock", "paper", "scissors"]

# Displaying Output
print(f"Output: {random.choice(array)}")

```

# Shuffling An Array

This will shuffle / move the contents **inside** an array *randomly*.

>[!tip] Usage
>```python
>random.shuffle(x)
>```

## Example: Shuffling An Array

```python

import random

print()

# DECLARE ARRAY car[2]: INTEGER
car = ["Evo 9", "EG-6", "Supra MK4", "E46 M3", "R32 GTR", "Mazda 787B"]

# Suffling The Array

random.shuffle(car)

# Displaying Output
print(car)

```

>[!note]
>This function ( "*random.shuffle*" ) will **shuffle** the contents of the array, nevertheless, it will **not** output anything if you write:
>```python
>print(random.shuffle(array))
>```
>This returns:
>```python
>None
>```

---

# Socials

- [**Instagram**](https://www.instagram.com/s.sunhaloo/)
- [**YouTube**](https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg)
- [**GitHub**](https://www.github.com/Sunhaloo)

---

S.Sunhaloo
Thank You!