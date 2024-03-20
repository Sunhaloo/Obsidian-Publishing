---
Alias: Math Function in Python
Tag: python, basics
Author: S.Sunhaloo
Type: Math
Date: 2024-02-20
Status: Completed
---

## List of Contents

- [[Python Math Function#Math Functions]]
	- [[Python Math Function#Round Function | Round Function]]
	- [[Python Math Function#Power Function | Power Function]]
	- [[Python Math Function#ABS Function | ABS Function]]
	- [[Python Math Function#Max Function | Max Function]]
	- [[Python Math Function#Min Function | Min Function]]
- [[Python Math Function#Math Functions with `math` Module | Math Functions with `math` Module]]
	- [[Python Math Function#Ceil Function | Ceil Function]]
	- [[Python Math Function#Floor Function | Floor Function]]
	- [[Python Math Function#Square Root Function | Square Root Function]]

---

My Links

- [[Python Math Function#Socials | Links to Socials]]

---

# Math Functions

## Round Function

*Commonly* used to **round-off** decimal numbers to the nearest value.

>[!tip] Usage
>```C
>
>round(x)
>
>```
>Where `x` can be any **number**

It will follow the *normal* mathematical rule where it will only round things off at **.5** or **above**.

>"*Commonly*", like what the actual fuck, that its whole purpose in life.

```python

# Round Function

print()

# Round 3.5
print("Rounding Off 3.5 = str(round(3.5))")

# DECLARE number: DOUBLE
number = 5.13745

# Round the variable `number`
print(f"Number = {round(number)}")

print()

```

## Power Function

>"Powwwaaahhh" Jeremy Clarkson

So, in the earlier classes ( *like when you were younger* ); you learnt about *power of numbers* in math. So do I really need to explain it? Well, at least I am going to say that we have a **base** and an **index** / **exponent**. I will leave you to that.

>[!tip] Usage
>```C
>
>pow(x, y)
>
>```
>Where `x` is the **base** and `y` is the **index**. In addition, both can be an *integer*, *float*, or any other data types related to numbers.

```python

# Power Function

print()

# DECLARE base: INTEGER
# DECLARE index: INTEGER

# Ask the user to enter some values
base = int(input("Please Enter A Value For The Base: "))
index = int(input("Please Enter A Value For The Index: "))

print()

# Output the value of calculation
print(f"The Answer = {pow(base, index)}")

print()

```

## ABS Function

First and foremost this is **not** *Anti-Lock Braking System* or "*ABS*" ( *like the human body thing* ). This is simply a function that will convert a **negative** number into a **positive** number.

>[!tip] Usage
>```C
>
>abs(x)
>
>```
>Where `x` can be any number, yes, even a positive one.

```python

# ABS Function

print()

print(f"The Positive of -5 is {abs(-5)}")

print()

```

## Max Function

It is used to find the maximum values from a set of numbers like an **array** or a **text file**.

>[!tip] Usage
>```C
>
>max(x)
>
>```
>Where `x` can be a number or array. Like just go and fucking check, I do not need to write everything for you. That is why we have Google you dumb fuck.

```python

# Max Function

print()

print(max(1, 2, 3, 4, 5, 6))

# DECLARE array[0:4]: INTEGER
array = [1, 2, 3, 4, 5]

# Output the maximum value from `array`
print(f"The Maximum Value from Array = {max(array)}")

# DECLARE big_array[0:3]: OF INTEGER
big_array = [111,777, 999]

# Output the Biggest Array
print(f"The Maximum Value from Array = {max(array, big_array)}")

print()

```

## Min Function

The **opposite** of the `Max` function. It works exactly the same as the [[Python Math Function#Max Function | Max Function]]. Hence, I will not be wasting my time writing the same fucking thing.

>Just change `max` to `min` to use this function.

---

# Math Functions with `math` Module

>[!warning]
>The **functions** below $\downarrow$ will **not** work if you do not *import* the `math` module.

## Ceil Function

This is similar to the `round()` function, but will **always** *round-up* a number ( *what is mean is that it does not obey the .5 rule* ).

What I really mean is this; If you have `2.1`, when we apply the function, it will become `3`.

>[!tip] Usage
>```C
>
>math.ceil(x)
>
>```
>Where `x` can be any number of any data type.

```python

# Ceil Function

# Import `math` module 
import math

print()

# Round-Up PI
print(math.ceil(math.pi))

print()

```

## Floor Function

This is similar to `ceil()` but will will only **round-down** a number. Like it does not obey the "*.5*" rule.

What I really mean is this; If you have `1.9`, when we apply the function, it will become `1`.

>[!tip] Usage
>```C
>
>math.floor(x)
>
>```
>Where `x` can be any number of any data type.

```python

# Ceil Function

# Import `math` module 
import math

print()

# Round-Up PI
print(math.floor(math.pi))

print()

```

>You can see that I am getting a bit lazy!

## Square Root Function

>Ahh, finally the last one!!!

This function is used to find the *square root* of a number. *Do I need to say more?*

>[!tip] Usage
>```C
>
>math.sqrt(x)
>
>```
>Where `x` can be any number of any data type. Obviously, we cannot find the square root of a negative number. Even though $i = \sqrt{-1}$.

```python

# Squre Root Function

# Import `math` module
import math

print()

print(f"The square root of 4 is {math.sqrt(4)}")

print()

```

---

# Socials

- [**Instagram**](https://www.instagram.com/s.sunhaloo/)
- [**YouTube**](https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg)
- [**GitHub**](https://www.github.com/Sunhaloo)

---

S.Sunhaloo
Thank You!