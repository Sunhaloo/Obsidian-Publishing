---
Alias: Arrays in C
Tag: C, bascis, 1D-Array, 2D-Array
Author: S.Sunhaloo
Type: Arrays ( 1D / 2D )
Date: 2024-03-19
Status: In-Progress
---

## List of Contents

[[Arrays - C#Little Introduction of Arrays | Little Introduction to Arrays]]

## One Dimensional Array

---

### My Links

- [[Arrays - C#Socials | Links to Socials]]

---

# Little Introduction to Arrays

So arrays or *lists* are basically that: **lists** ( *formally known as Data Structures* 🤓 ) that holds the **same** data type.
Think about a single row **or** / **and** columns in an Excel Documents.

For more information about Arrays head over to [[Arrays - Python#What is an Array/List?| Arrays in Python]] or Google, YouTube University or even ChatGPT.

>Remember Boys ( *and Girls* ), we use ChatGPT for information gathering and **not** *cheating*
>No for real, I hate fuckin cheaters, if there was a way to ban people like you ban them in games; I would gladly press the <button>Report</button> ( *$\leftarrow$ an actually button - like the HTML button tag ) Button.

Yeah so lets get started with coding because I want to actually code some shit instead of me typing this; I know I wasted a bunch of time saying this... GO FUCK YOURSELF!

---

# One Dimensional Arrays ( 1D-Arrays )

## Creating A 1D-Array

So the code below $\downarrow$ will show you how to create 1D-Arrays.

>[!tip] Usage
>Here is the format of a 1D-Array
>```
>DataType array_name[] = {value1, value2, value3, ...};
>
>```

### Example: 2 Ways of Making an Array

>Refer to **comments** inside the code for explanation!

```C

// Include standard input / output header
#include <stdio.h>
// Include string library / header
#include <string.h>

int main()

{

  // First Method to Declare and Initialise an Array
    // Normally used when we know the values that will go into the array
  // DECLARE ARRAY numbers[5]: INTEGER
  int numbers[] = {1, 2, 3, 4, 5};
  
  // Second Method to Declare and Initalise an Array
    // This method is used when we only know the Size of the array
  // DECLARE ARRAY characters[5]: CHAR
  char characters[5];

  // We can then, later, come back to insert the values as so:
  characters[0] = 'a';
  characters[1] = 'b';
  characters[2] = 'c';
  characters[3] = 'd';
  characters[4] = 'e';

  return 0;

}

```

## Displaying 1D-Arrays

So as you know our arrays have something call "*index*". Basically the **first** value is at **index** *0*. Take a look below $\downarrow$

- Mark-up of a simple 1D-Array

| Index | Contents |
| ----- | -------- |
| 0 | 44 |
| 1 | 55 |
| 2 | 16 |
| 3 | 7 | 
| 4 | 3 |

>I like Formula 1, especially if Merc and / or Lewis Hamilton is Winning.

So there are a few ways to display the an array in C

### Method 1: Displaying values individually

```C

// Include standard input / output header
#include <stdio.h>
// Include string library / header
#include <string.h>

int main()

{

  // DECLARE ARRAY numbers[5]: INTEGER
  int numbers[] = {1, 2, 3, 4, 5};

  // Output the values of array `numbers` ( individually )

  printf("\nNumbers Array\n");
  printf("%d", numbers[0]);
  printf("\n%d", numbers[1]);
  printf("\n%d", numbers[2]);
  printf("\n%d", numbers[3]);
  printf("\n%d", numbers[4]);

  return 0;

}

```

This is normally used to print out single values from an array. As you can see from the above $\uparrow$ code; it's not that efficient to write every single index of the array. Because what are you going to do if the array has over a 1000 index? Cry! I bet so!

### Method 2: Displaying with a Loop

```C

// Include standard input / output header
#include <stdio.h>
// Include string library / header
#include <string.h>

int main()

{

  // DECLARE ARRAY intials[5]: INTEGER
  int initials[] = {'S', 'U', 'S', 'S', 'Y'};

  // Output the values of array `initials` ( using a `for` loop )

  // DECLARE i: INTEGER
    // In this case we have declared the counter `i` inside the for loop itself
    // Actually the best / main way to create counter is by doing it within the `for` loop itself
  for(int i = 0; i < 5; i += 1){
    // Displaying Characters on Different Lines
    printf("\n%c", initials[i]);
  }
  
  printf("\n\n");

  for(int i = 0; i < 5; i++){
    // Displaying all Characters on Same Line
    printf("%c", initials[i]);
  }

  return 0;

}

```

>[!note]- Equivalent Python Code
>The equivalent Python Code is:
>```python
>
>initials = ['S', 'U', 'S', 'S', 'Y']
>
># Display on Separate Lines
>for x in intials:
>	print(x)
>
># Display on Same Line
>for x in intials:
>	print(x, end="")
>
>```

This is the better way of displaying an array.
In the code above $\uparrow$; you can see that there are 2 `for` loops.
The first one is used to display the contents on **separate** lines, while the other will display the contents on the **same** line.

In addition, You **cannot** use the same counter `i` for both.
But you say yourself, you just did you dogshit little liar!.
Brother take a look again; I *re-declared* the counter `i`

---

# Socials

- [**Instagram**](https://www.instagram.com/s.sunhaloo/)
- [**YouTube**](https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg)
- [**GitHub**](https://www.github.com/Sunhaloo)

---

S.Sunhaloo
Thank You!