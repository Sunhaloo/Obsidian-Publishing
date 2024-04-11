---
Alias: Math Function in Python
Tag: python, basics
Author: S.Sunhaloo
Type: Math
Date: 2024-02-20
Status: Completed
---

## List of Contents

- [[Python Math Function#Math Functions | Math Functions]]
	- [[Python Math Function#Round Function | Round Function]]
	- [[Python Math Function#Power Function | Power Function]]
	- [[Python Math Function#ABS Function | ABS Function]]
	- [[Python Math Function#Max Function | Max Function]]
	- [[Python Math Function#Min Function | Min Function]]
- [[Python Math Function#Math Functions with `math` Module | Math Functions with `math` Module]]
	- [[Python Math Function#Ceil Function | Ceil Function]]
	- [[Python Math Function#Floor Function | Floor Function]]
	- [[Python Math Function#Square Root Function | Square Root Function]]
	- [[Python Math Function#Trigonometry Functions | Trigonometry Functions]]

---

My Links

- [[Python Math Function#Socials | Links to Socials]]

---

# Math Functions

## Round Function

*Commonly* used to **round-off** decimal numbers to the nearest value.

>[!tip] Usage
>```python
>round(x)
>```

It will follow the *normal* mathematical rule where it will only round things off at **.5** or **above**.

>"*Commonly*" $\uparrow$, like what the actual fuck, that its whole purpose in life.

```python

print()

# Round 3.5
print(f"Rounding Off 3.5 = {round(3.5)}")

# DECLARE number: REAL
number = 5.13745

# Round the variable `number`
print(f"Number = {round(number)}")

print()

```

## Power Function

>"Powwwaaahhh" [Jeremy Clarkson](https://en.wikipedia.org/wiki/Jeremy_Clarkson)

So, in the earlier classes ( *like when you were younger* ); you learnt about *power of numbers* in math. So do I really need to explain it? Well, at least I am going to say that we have a **base** and an **index** / **exponent**. I will leave you to that.

>[!tip] Usage
>```python
>pow(x, y)
>```

```python

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
>```python
>abs(x)
>```

```python

print()

print(f"The Positive of -5 is {abs(-5)}")

print()

```

## Max Function

It is used to find the maximum values from a set of numbers like an **array** or a **text file**.

>[!tip] Usage
>```python
>max(x)
>```

```python

print()

print(max(1, 2, 3, 4, 5, 6))

# DECLARE array[4]: INTEGER
array = [1, 2, 3, 4, 5]

# Output the maximum value from `array`
print(f"The Maximum Value from Array = {max(array)}")

# DECLARE big_array[3]: OF INTEGER
big_array = [111,777, 999]

# Output the Biggest Array
print(f"The Maximum Value from Array = {max(array, big_array)}")

print()

```

## Min Function

The **opposite** of the `max` function. It works exactly the same as the [[Python Math Function#Max Function | Max Function]]. Hence, I will not be wasting my time writing the same fucking thing.

>Just change `max` to `min` to use this function.

---

# Math Functions with `math` Module

>[!warning]
>The **functions** below $\downarrow$ will **not** work if you do not *import* the `math` module.
>>[!tip]- Usage
>>```python
>>import math
>>```

## Ceil Function

This is similar to the `round()` function, but will **always** *round-up* a number ( *what is mean is that it does not obey the .5 rule* ).

What I really mean is this; If you have `2.1`, when we apply the function, it will become `3`.

>[!tip] Usage
>```python
>math.ceil(x)
>```

```python

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
>```python
>math.floor(x)
>
>```

```python

# Import `math` module 
import math

print()

# Round-Up PI
print(math.floor(math.pi))

print()

```

>You can see that I am getting a bit lazy!

## Square Root Function

This function is used to find the *square root* of a number. *Do I need to say more?*

>[!tip] Usage
>```python
>math.sqrt(x)
>```

```python

# Import `math` module
import math

print()

print(f"The square root of 4 is {math.sqrt(4)}")

print()

```


## Trigonometry Functions

I think you know where this is going! We have all learned trigonometry in fucking Primary School. Do you think that I will be writing a fucking Power Point Presentation to explain to you to how *trig*?

>Also, I do not know how to use Power Point, never really used it or played with it as a Kid. Was always on Need for Speed Most Wanted 2004 Black List Edition.
>I will be writing all the trigonometry function in the code block below $\downarrow$.

```python

# Import `math` Module
import math as m

# Trigonometry
print()

# Sine
print(f"Sine of  PI by 6 = {m.sin(m.pi / 6)}")

# Cosine
print(f"Cosine of 0 = {m.cos(0)}")

# Tangent
print(f"Tangent of 0 = {m.tan(0)}")

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