---
Alias: Functions and Procedures C Language
Tag: C, basics
Author: S.Sunhaloo
Type: Functions / Procedures
Date: 2024-03-09
Status: Completed
---

## List of Contents

- [[Functions and Procedures - C#What is a Function / Procedure? | What is a Function / Procedure?]]
- [[Functions and Procedures - C#Simple Functions / Procedures in C | Simple Functions / Procedures in C]]
- [[Functions and Procedures - C#Parameters | Parameters]]
- [[Functions and Procedures - C#Return Statement | Return Statement]]
- [[Functions and Procedures - C#Function Prototypes / `void`| Function Prototypes / `void`]]

---

# My Links

- [[Functions and Procedures - C#Socials | Links to Socials]]

---

# What is a Function / Procedure?

Again, I am not going to fucking write things that I have already written in the past ( *this is why I used Obsidian!* ). Here is the link to [[Functions and Procedures - Python#What is a Function / Procedure? | Python's Function and Procedures]]

But just remember that:

- **Functions**
	- Returns a value; whatever the case / task is.
	- It will return a value
		- Check [[Linear Search - Python | Linear Search]]
- **Procedures**
	- Might return a value, multiple values or nothing
		- Check [[Bubble Sort - Python | Bubblesort - Python]] or [[Bubble Sort - C | Bubblesort - C]]
- They are can be small or really big ( *because `clean code` = **Horrible Performance** and I care about performance* )
- Part of the **main** program

>[!warning]
>C is similar to Visual Basic; where our Functions and Procedures live at the **top** of our code.
><li style = "color:white;"><span style = "color: red;">Always place Functions on</span> <span style= "color:green;">top</span></li>
>
>$\Rightarrow$ Because of memory, it need to *read* / compile the functions first to be able to use it!
>
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
void ouptut(char name[], char region[], int age)

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

  // Calling our Function and passin in our Parameters
  ouptut(name, region, age);

  return 0;
}

```

>[!tip]
>No need to pass the size of "*array*" ( *our string variables* ) inside the Function Prototype and Function.
>- As it has already been declared ( *i.e the size of array / string* ) in `main`.

>[!note]
>For now, just remember that `void` means that it has **no** specific *type*, *number of parameters*, etc.
>- Like take a look, we are passing `char` and also `int` in the same function

In the code above $\uparrow$, we can see that our values that will be passed to the function `output` is written in the `main` *function*.

To use the function, we need to **call** it in our *main* program and then pass the parameters / arguments `name`, `region` and `age` in the function `output`. Hence, we can use the function.

>[!tip]
>Remember *Visual Basic* ( *to be honest I do not remember because FUCK YOU VB and Lan $\rightarrow$ If you know you know* ).
>C is similar to VB where we need to also enter our data types that will / are being passed through.

# Return Statement

Normally used to return something back to the main program.

 - Could be an *integer*, *character* or *float*.

## Example: Return the Square of a Number

In this example below, we will create a function called `square`, in which we are going to write the *main* calculation ( *basically the function which is going to perform our calculation! duh!* ). Go ahead and check out the code below; pay attention to the *word* **before** the function's name ( *i.e `square`* )

```C

// Include standard input / output header
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

## Another Example: Code is By Me!

>This is the reason why the code is so shitty!

```C

// Include standard input / output header
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

# Function Prototypes / `void`

So you know that how I have been saying that *C is similar to Visual Basic* $\Rightarrow$ Because we write our functions at the top first...

>Insert "*so that was a fucking lie* meme here"

I mean, not really, like the thing that I have been saying and *writing* / *coding* above definitely still apply. Nevertheless, for [[Functions and Procedures - C#Function Prototypes | this part]], I do not really know how to explain it. So I have gathered the help from [ChatGPT](chat.openai.com), in addition to [Bro Code's Video Explanation](https://www.youtube.com/watch?v=87SH2Cn0s9A&t=6083s)

## Explanation on Function Prototypes

A **function prototype** is a declaration of a function that tells the **compiler** about the function's *specifications*, like:

- Function's name
- Number of Parameters
- Return Type

This is done **before** ( *i.e at the top of the `main` function* ) the function's actual implementation.

It serves as a way to **inform** the *compiler* about the existence and signature of functions that will be **later** defined in the program.

#### Some Advantages of Function Prototypes

1. Easier to navigate code base when `main` function is at the top of file
2. Helps with debugging as compiler will flag an error if any arguments are missing
3. Commonly used in [[C Language#What does ` include <stdio.h>` means? | header files]]

>In some ways it tells the compiler that "*heh, there is $x$ amount of parameters in that function and you are missing one*"
>Basically helping you ( *the programmer* ) in some ways.
>Its more simple if I just show you the code, because notes $\neq$ understanding in coding $\rightarrow$ Check [BigBoxSWE's Video](https://www.youtube.com/watch?v=QMbx0dTWJIQ)

### Example 1: Bro Code's Code

```C

// Include standard input / output header
#include <stdio.h>

// Function Prototype
void output(char name[], char proffession[], int age);

// Main Function
int main()

{
  // Declaration
  // DECLARE user_name: STRING
  char user_name[25];
  // DECLARE user_proffession: STRING
  char user_proffession[25];
  // DECLARE user_age: INTEGER
  int user_age;

  // Ask the user to input data
  printf("\nPlease Enter Your Name: ");
  scanf("%s", user_name);
  printf("Please Enter Your Proffession: ");
  scanf("%s", user_proffession);

  printf("Please Enter Your Age: ");
  scanf("%d", &user_age);

  // Calling Function
  output(user_name, user_proffession, user_age);

  return 0;

}

// Function `output` which has 3 arguements passed into
// FUNCTION output(DECLARE name: STRING, DECLARE proffession: STRING, DECLARE age: INTEGER)
// NOTE: See how it also has the same name as its function prototype
void output(char name[], char proffession[], int age)

{

	printf("\nName: %s\n", name);
	printf("Proffession: %s\n", proffession);
	printf("Age: %d\n", age);

}

```

>[!tip]
>No need to pass the size of "*array*" ( *our string variables* ) inside the Function Prototype and Function.
>- As it has already been declared ( *i.e the size of array / string* ) in `main`.

>[!note]
>For now, just remember that `void` means that it has **no** specific *type*, *number of parameters*, etc.
>- Like take a look, we are passing `char` and also `int` in the same function.

### Example 2: ChatGPT's Code

```C

// Include standard input / output header
#include <stdio.h>

// Function Prototype
int addition(int x, int y);

// Main Function
int main()

{
  // Declaration
  // DECLARE num1: INTEGER
  int num1;
  // DECLARE num2: INTEGER
  int num2;

  // Ask the user to input numbers
  printf("\nPlease Enter Number 1: ");
  scanf("%d", &num1);
  printf("\nPlease Enter Number 2: ");
  scanf("%d", &num2);

  // Calling Function
  int answer = addition(num1, num2);

  // Output Addition
  printf("\nAddition = %d\n", answer);
}

// Function `addition` which has 2 arguements passed into
// FUNCTION addition(DECLARE x: INTEGER, DECLARE y: INTEGER)
// NOTE: See how it also has the same name as its function prototype
int addition(int x, int y)

{
  return x + y;
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
