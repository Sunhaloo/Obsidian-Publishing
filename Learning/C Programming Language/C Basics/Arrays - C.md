---
Alias: Arrays in C
Tag: C, bascis, 1D-Array, 2D-Array
Author: S.Sunhaloo
Type: Arrays ( 1D / 2D )
Date: 2024-03-19
Status: In-Progress
---

## list of contents

- [[Arrays - C#Little Introduction of Arrays | Little Introduction to Arrays]]

## One Dimensional Array

- [[Arrays - C#Creating A 1D-Array | Creating A 1D-Array]]
- [[Arrays - C#Displaying 1D-Arrays | Displaying 1D-Arrays]]
- [[Arrays - C#Adding Elements into 1D-Arrays | Adding Elements into 1D-Arrays]]

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

### Method 3: Niche Way of Iterating through Array

We are going to be using the `sizeof()` Function. If you do not know what this does, then head over to [[C Tips#Calculate the Size of Arrays ( Not Length of Array ) | How to Calculate the Size of Array - Not the Length]]

```C

// Include standard input / output header
#include <stdio.h>

int main()

{

  // DECLARE ARRAY intials[5]: INTEGER
  int initials[] = {'S', 'U', 'S', 'S', 'Y'};
  // DECLARE ARRAY prices[4]: INTEGER
  double prices[] = {12.50, 9.99, 449.99, 10.00};

  // Display the size ( like actual size in Bytes ) each array

  // Size of Array `initials` in Bytes
  printf("\nSize of Array `initials` = %ld Bytes", sizeof(initials));
  printf("\nSize of Array `prices` = %ld Bytes\n", sizeof(prices));

  // Use `sizeof()` Function to Display Arrays `initials` and `prices`

  for (int x = 0; x < sizeof(prices) / sizeof(prices[0]); x++) {
    printf("\n%0.2lf", prices[x]);
  }

  return 0;
}


```

I mean, there is not point to this. This is making the program slower ( *I think* ). Because we need to use the function `sizeof()`, when we **run** the program; it will need to like also run the function `sizeof()` instead of a simple number.

Yeah, when you compile C program with GCC, it will also compile all of the function and other shit that comes with it. But I think you know what I am trying to say.

## Adding Elements into 1D-Arrays

### "*Appending*" Elements into 1D-Array

This code $\downarrow$ will show you how to insert an element into an array at the **end** of an array.

```C

// Include standard input / output header
#include <stdio.h>

// FUNCTION dis(DECLARE array[]: INTEGER, DECLARE size: INTEGER)
void display(int array[], int size)

{
  // Displays any array
  for(int i = 0; i < size; i++){
    printf("\nIndex = %d | Value: %d", i , array[i]);
  }
}

int main()

{

  // DECLARE size_array: INTEGER
  int size_array;

  // Ask the user to enter the size of array
  printf("\nPlease Enter The Size of Array: ");
  scanf("%d", &size_array);

  // DECLARE ARRAY intials[]: INTEGER ( user will be ask the enter the size of array )
  // NOTE: Declaring AFTER getting the `size_array` from the user.
    // This is because C, Yeah C, Memory Management and stuff.
    // This is big men / chad toy now, not Python, we need to be one with the computer.
  int initials[size_array];

  printf("\nSize of Array: %d", size_array);

  printf("\n");

  // Ask the user to enter the the elements in array
  // DECLARE counter: INTEGER
  for(int counter = 0; counter < size_array; counter++){
    printf("\nPlease Enter Elements: ");
    scanf("%d", &initials[counter]);
  }

  // Display the Array using Function `display`
  display(initials, size_array);
  
  printf("\n");

  return 0;
}


```

Here are some explanation:
1. The first thing that we ( *more like "I"* ) did, is create a function called `display` to display our ( *can also display any array* ) array. We need to pass the array name and the size of the array; which were both in this case `initials` and `size_array` respectively.

2. Then we need to ask the user to enter:
	- Size of Array
	- The Elements ( *that will go inside the array* )

3. After asking the Size and Elements that will go inside of our array, We then use the for loop to enter the elements given by the user into the array with each incrementing counter `counter` by 1 until the limit ( *here the limit is the size of array* ) is reached.

#### Equivalent Python Code

>To be honest, I much prefer to write Python Codes than C, but the **SPEED** of C is soooooooo much better than Python.

I normally write the array in the very **first** line. This is because look at the above $\uparrow$ code, I declared the `size_array` first then asked the user to enter its value. Finally, we use the array as normally. 

>But if I was actually writing Python Code; I would structure it like this:
>- All declaration like
>	- Globals
>	- Arrays
>	- Constants
>- User input
>But then again I have not written many code, just some algorithms like [[Binary Search - Python#Example 1 Complete Code for 1D-Array| binary search]] and other.

```python

print()
# Ask the user to enter the size of array
array_size = int(input("Please Enter The Size of Array: "))

# DECLARE ARRAY array[array_size]: INTEGER ---> User Will Give The Size
array = []

print()

# Loop to iterate through array
for x in range(array_size):

    # Ask the user to enter elements / values into array
    # DECLARE user_input: INTEGER
    user_input = int(input("Please Enter A Value: "))
    
    # Appends the user value to array
        # Append ---> The value will added will always go to the last index of array
    array.append(user_input)

print()

# Output Array
for i, y in enumerate(array):

    print(f"Index: {i} | Value: {y}")


```

---

# Socials

- [**Instagram**](https://www.instagram.com/s.sunhaloo/)
- [**YouTube**](https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg)
- [**GitHub**](https://www.github.com/Sunhaloo)

---

S.Sunhaloo
Thank You!