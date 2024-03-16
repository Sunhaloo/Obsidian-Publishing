---
Alias: Functions and Procedures C Language
Tag: C, basics
Author: S.Sunhaloo
Type: Functions / Procedures
Date: 2024-03-09
Status: In-Progress
---

## List of Contents

- [[Functions and Procedures - C#What is a Function / Procedure? | What is a Function / Procedure?]]
- [[Functions and Procedures - C#Simple Functions / Procedures in C | Simple Functions / Procedures in C]]
- [[Functions and Procedures - C#Parameters | Parameters]]
- [[Functions and Procedures - C#Return Statement | Return Statement]]

---

# My Links

- [[Functions and Procedures - C#Socials | Links to Socials]]

---

# What is a Function / Procedure?

Again, I am not going to write things that I have already written in the past ( *this is why I used Obsidian!* ). Here is the link to [[Functions and Procedures - Python#What is a Function / Procedure? | Python's Function and Procedures]]

But just remember that:

- **Functions**
	- Returns a value; whatever the case / task is.
	- It will return a value
		- Check [[Linear Search - Python | Linear Search]]
- **Procedures**
	- Might return a value, multiple values or nothing
		- Check [[Bubble Sort - Python | Bubblesort]]
- They are can be small or really big
- Part of the **main** program

>[!warning]
>C is similar to Visual Basic; where our Functions and Procedures live at the **top** of our code.
><li style = "color:red;">Always place Functions on <span style= "color:green;">top</span></li>
>>Compared to Python, where we can write our functions almost anywhere we want.

---

# Simple Functions / Procedures in C

## Example: Output Welcome Screen with Function

```C

// Include standard input / output header
#include <stdio.h>

// Our Function
// FUNCTION welcome_screen()
void welcome_sceen()

{

  printf("\nWelcome To Our Simple Program!");

  printf("\n");
  
  printf("\nPlease Select From the Selection Below:\n");

}

// Another Function
// FUNCTION selection()
void selection()

{

  printf("\n1. Burger");
  printf("\n2. Fries");
  printf("\n3. Ice-cream");
  printf("\n4. Fried Chicken");
  printf("\n5. Soft-Drinks\n");

  printf("\n");

}

// Main Function
int main()

{

  // Calling the function `welcome_screen`
  welcome_sceen();

  // Calling the function `selection`
  selection();

  return 0;

}

```

>[!note]
>In this case *nothing* is being passed as [[Functions and Procedures - Python#Parameters | Parameters]]

# Parameters

## Passing our Parameters

### Example: Displaying Our Name / User's Name

```C

// Include standard input / output header
#include <stdio.h>

// Our Function
// FUNCTION output
void ouptut(char name[25], char region[15], int age)

{

  printf("\nName: %s", name);
  printf("\nRegion: %s", region);
  printf("\nAge: %d", age);
}

// Main Function
int main()

{
  // DECLARATION

  // DECLARE name: STRING
  char name[25];
  int age;
  char region[15];

  // Ask the user to enter data
  printf("Please Enter Your Name: ");
  scanf("%s", name);

  printf("Please Enter Your Region: ");
  scanf("%s", region);

  printf("Please Enter Your Age: ");
  scanf("%d", &age);

  // Calling our Function
  ouptut(name, region, age);

  return 0;
}


```

In the code above $\uparrow$, we can see that our values that will be given / passed to the function `output` is written in the `main` *function*.

To use the function, we need to **call** it in our *main* program and then pass the parameters / arguments `name`, `region` and `age` in the function `output`. Hence, we can use the function.

>[!tip]
>Remember *Visual Basic* ( *to be honest I do not remember because FUCK YOU VB* ).
>C is similar to VB where we need to also enter our data types that will / are being passed through.

# Return Statement

Normally used to return something back to the main program.

 - Could be an *integer*, *character* or *float*.

## Example: Return the Square of a Number

In this example below, we will create a function called `square`, in which we are going to write the *main* calculation ( *basically the function which is going to perform our calculation! duh!* ). Go ahead and check out the code below; pay attention to the *word* **before** the function's name ( *i.e `square`* )

```C

// Include standart input / output header
#include <stdio.h>
// Include math library to be able to use comman math functions
#include <math.h>

// Function `square` which has an arguement passed into
// FUNCTION square( DECLARE num: DOUBLE)
double square(double num)

{
  double result = pow(num, 2);

  return result;
}

// Main Function
int main()

{
  // Declaration and Initialisation and Calling Function
  // Basically Variable `answer` hold the "answer" to `sqaure(2)`
  double answer = square(2);

  printf("The Answer is: %lf", answer);

  return 0;
}


```

>[!note]
>See how in our **main** function we have *int `main`* and for our function `square` that we have created *double `square`*. This is because we are **returning** a `double` ( *see `return result`* )
>
>In addition, we have in our main function `main`, we have `double result = square(2);`
>For the moment you might not be familiar with the syntax, but remember when we used the power function from the `math.h` header? Yes, so you simply *declare* and basically *call* the function instantly ( refer to [[C Math Function | Math Functions]] for more clarification *I mean what do I know* ).
>>[!warning] Need to clean up this part !!!

## Another Example: Code is By Me!

>This is why the reason the code is really shitty!

```C

// Include standart input / output header
#include <stdio.h>

// Function `character` which has an arguement passed into
// FUNCTION character(DECLARE i: CHAR)
char character(char i)

{
  char return_char = i;

  return return_char;
}

// Function `integer` which has an arguement passed into
// FUNCTION integer(DECLARE j: INTEGER)
int integer(int j)

{
  int plus_2 = j + 2;

  return plus_2;
}

// Main Function
int main()

{
  // Calling the functions with variables
  char answer_char = character('a');
  int answer_int = integer(2);

  // Output results to screen
  printf("\nCharacter = %c", answer_char);
  printf("\nInteger + 2 = %d\n", answer_int);

  return 0;
}

```

---

# Socials

- [**Instagram**](https://www.instagram.com/s.sunhaloo/)
- [**YouTube**](https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg)
- [**GitHub**](https://www.github.com/Sunhaloo)

---

S.Sunhaloo
Thank You!
