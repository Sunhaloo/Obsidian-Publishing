---
Alias: Math Functions in C
Tag: C, basics, include_header
Author: S.Sunhaloo
Type: Math Functions
Date: 2024-02-12
Status: Completed
---

## List of Contents

- [[C Math Function#What to Include? | What to Include?]]
	- [[C Math Function#Square Root | Square Root]]
	- [[C Math Function#Power Function | Power Function]]
	- [[C Math Function#Round Function | Round Function]]
	- [[C Math Function#Ceil Function | Ceil Function]]
	- [[C Math Function#Floor Function | Floor Function]]
	- [[C Math Function#Fabs Function | Fabs Function]]
	- [[C Math Function#Logarithms / Log of Numbers | Logarithms]]
	- [[C Math Function#Trigonometry | Trigonometry]]
- [[C Math Function#Python Math Function Math Functions in Python | Math Functions in Python]]

---

### My Links

- [[C Math Function#Socials | Links to Socials]]

---

# Math Functions

## What to Include?

To be able to perform certain mathematical functions, we need to *include* a library called `math.h`. Hence, at the **start** of every code where you want to use *math* function; include it like so;

```C

// Adding the library `math.h`
#include <math.h>

```

>[!warning]
>If you do **not** include this library, then you will not be able to perform these mathematical functions.

## Square Root

To find the square root of a number, we use `sqrt()`. Below $\downarrow$ will show you a little example of finding the square root of some numbers.

>[!tip] Usage
>```C
>
>sqrt(x)
>
>```
>Where `x` can be a **integer**, **float**, **double** or any other related *numbers* data types.

```C

// Math Function

// Include math Library
#include <math.h>

// Square Root

int int_square_root = sqrt(9);
float float_square_root;
double double_square_root;

float_square_root = sqrt(16);
double_square_root = sqrt(144);

```

## Power Function

Remember boys ( *and girls* ); the *anatomy* of *powering* numbers! They have a **base** and **index** / **exponent**. Like so, $2^3$, Here we can see that the **base** is *2* and the **index** / **exponent** is *3*. Similarly, the `pow()` function has a place to put the **base** and **index**.

>[!tip] Usage
>```C
>
>pow(x, y)
>
>```
>Where `x` is the **base** and `y` is the **index**. In addition, both can be an *integer*, *float*, or any other data types related to numbers.

```C

// Math Function

// Include Math Library
#include <math.h>

// Power

int int_power = pow(2, 3);
float float_power;
double double_power;

float_power = pow(5, 2);
double_power = pow(4, 4);

```

## Round Function

This is used to **round-off** decimal numbers to certain decimal place.

This will follow the normal mathematical rule ( *what I mean by rule is the .5 thing!* )

>[!tip] Usage
>```C
>
>round(x)
>
>```
Where `x` can be... *Do I need to say this again; Fuck this, amma go write the code below* $\downarrow$ !

```C

// Math Function

// Include Math Library
#include <math.h>

// Rounding Number

int int_round = round(3.142);
float float_round;
double double_round;

float_round = round(3.142);
double_round = round(3.142);

```

## Ceil Function

This is similar to `round()` but will will only **round-up** a number. Like it does not obey the "*.5*" rule.

What I really mean is this; If you have `2.1`, when we apply the function, it will become `3`.

>[!tip] Usage
>```C
>
>ceil(x)
>
>```
>Where `x` can be any number of any data type.

```C

// Math Function

// Include Math Library
#include <math.h>

// Ceiling ( Rouding Up Numbers )

int int_ceil = ceil(3.142);
float float_ceil;
double double_ceil;

float_ceil = ceil(3.142);
double_ceil = ceil(3.124);

```

## Floor Function

This is similar to `ceil()` but will will only **round-down** a number. Like it does not obey the "*.5*" rule.

What I really mean is this; If you have `1.9`, when we apply the function, it will become `1`.

>[!tip] Usage
>```C
>
>floor(x)
>
>```
>Where `x` can be any number of any data type.

```C

// Math Function

// Include Math Library
#include <math.h>

// Floor Function ( Rounding Down Numbers )

int int_floor = floor(100.999);
float float_floor;
double double_floor;

float_floor = floor(2.5284);
double_floor = floor(12.714);

```

# Fabs Function

This will take any **negative** value and convert it into a **positive** value.

>I think this is simple enough to understand that we are converting a $-$ve number to a $+$ve number. Else, you need to go and insert a toothbrush up your tiny ass

>[!tip] Usage
>```C
>
>fabs(x)
>
>```
>Where `x` can be any number of any data type.

```C

// Math Function

// Include Math Library
#include <math.h>

// Fabs Function ( Convert Negative Numbers to Positive Numbers )

int int_fabs = fabs(-100);
float float_fabs;
double double_fabs;

float_fabs = fabs(-55);
double_fabs = fabs(-44);

```

# Logarithms / Log of Numbers

So you know the $\log_{10}(a) = b$ $\Rightarrow$ $10_{b} = a$. So it is basically that in programming.

>[!warning]-
>We are **not** converting it as shown above $\uparrow$.
>We are just finding the value of $b$ by placing $a$ inside of `log()` 

>[!tip] Usage
>```C
>
>log(x)
>
>```
>Where `x` can be any number of any data type.

```C

// Math Function

// Include Math Library
#include <math.h>

// Logarithms

int int_log = log(2);
float float_log;
double double_log;

float_log = log(5);
double_log = log(-1);

```

# Trigonometry

Okay who da fuck does not know *trigonometry*; even my grandmother know this ( *she doesn't* )

>[!note]
>I recommend using the **float** or **double** *data types*.
>This is because most values in trigonometry are pretty much full of **decimal** numbers; Hence, you will get a better and more precise answer.

>[!tip] Usage
>```C
>
>sin(x)
>cos(x)
>tan(x)
>
>```
>Where `x` can be any number of any data type.

```C

// Math Function

// Include Math Library
#include <math.h>

// Trigonometry

// NOTE: I will only be doing a mix and not everything, you will see what I am talking about below
float int_sine = sin((0.5 * 3.141592));
float float_cos;
double double_tan;

float_cos = cos(0);
double_tan = tan(45);

```

# [[Python Math Function | Math Functions in Python]]

We know that Python is was made using **C**. This means that most of the things that we said here applies also for Python.

---

# Socials

- [**Instagram**](https://www.instagram.com/s.sunhaloo/)
- [**YouTube**](https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg)
- [**GitHub**](https://www.github.com/Sunhaloo)

---

S.Sunhaloo
Thank You!