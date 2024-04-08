---
Alias: Enums in C
Tag: C, basics
Author: S.Sunhaloo
Type: Enumeration, Pointer, etc
Date: 2024-04-06
Status: In-Progress
---

## List of Contents

- [[User-Defined Data Types - C#User-Defined Data Types?| User-Defined Data Types?]]
- [[User-Defined Data Types - C#So what are Enums?| What are Enumerations]]

---

### My Links

- [[User-Defined Data Types - C#Socials| Links to Socials]]

---

>I remember doing this is school... It was in Cambridge Paper 3 Computer Science subject. Where we did this in Pseudocode ( *I just cannot remember what is was* ).
>Found it... I still have my notes from HSC!

# User-Defined Data Types?

So basically there are **User-Defined Data Types**. There are 2 types of User-Defined Data Types:

1. Non-Composite Data Types: Single Data Type that does **not** involve a *reference* to another data type ( *already available in Programming Language* ).
	- Integers
	- Strings
	- Chars
	- Boolean
	- ...
1. Composite Data Types: Data Type that is constructed from other data types.
	- Arrays
	- Classes
	- Records
	- Sets
	- ADTs ( Stacks, Queues )
	- Dictionaries

## So what are Enums?

It is a data types used to store constant values.

- It is a list of possible values.

### Enumeration in C

Check this code below first then we are going to talk about it below $\downarrow$.

```C

// Include standard input / output header
#include <stdio.h>

// TYPE TCoffee = (Black_Coffee, Espresso, Latte, Americano, Cappuccino, Mocha)
enum Coffee{Black_Coffee, Espresso = 1, Latte = 2, Americano = 3, Cappuccino = 4, Mocha = 5};

// FUNCTION output_screen()
// Outputs the screen to user
void output_screen()

{

  printf("\nWelcome to Shit Coffee!\n");
  printf("\n---Please Select A Number---\n");
  
  printf("Espresso = 1\n");
  printf("Latte = 2\n");
  printf("Americano = 3\n");
  printf("Cappuccino = 4\n");
  printf("Mocha = 5\n");

  printf("\nUsual - Black Coffee = 6\n");

}

// FUNCTION selection(DECLARE number: INTEGER)
// Will Give an Output to user selection
void selections(int number)

{

  // Conditions
  switch (number)

  {
 
 case Espresso:
    printf("\nPreparing your Espresso...");
    printf("\n");
    break;
 
 case Latte:
    printf("\nPreparing your Latte...");
    printf("\n");
    break;
 
 case Americano:
    printf("\nPreparing your Americano...");
    printf("\n");
    break;
 
 case Cappuccino:
    printf("\nPreparing your Cappuccino...");
    printf("\n");
    break;
 
 case Mocha:
    printf("\nPreparing your Mocha...");
    printf("\n");
    break;
 
 case Black_Coffee:
    printf("\nPreparing your Black Cock...");
    printf("\n");
    break;

  default:
    printf("\nPlease Enter A Number from 1 to 6!");
    printf("\n");
    break;
  }

}

int main()

{

  // NOTE: Remember they are NOT STRINGS... Instead they can be treated as INTEGERS
  // Using the enum
  // DECLARE usual: TCoffee
  enum Coffee usual = Black_Coffee;

  // Call the Function `output_screen` to display selection to user
  output_screen();

  // DECLARE selection: INTEGER
  int selection;

  // Ask the user to enter selection
  printf("\nPlease Enter Your Selection: ");
  scanf("%d", &selection);

  // Call the Function `selection` to fucking prepare coffee
  selections(selection);

  printf("\n");

  return 0;
}

```

>Might have over-complicated this a bit; but I think for a good reason!

**Take A Look At the `CASE`**!

We are passing a parameter of type **INTEGER**, but as we have made an *enumeration*. We can use that / our "*enumeration*" ( *which are coffee names* ) instead of numbers.

It will still work if you put numbers in the `case`; but now its much much more readable.

>[!note]
>Enums are <span style = "color: red;"><strong>not</strong></span> *strings*
>But they can be treated as <span style = "color: orange;"><em>integers</em></span>

---

# Socials

- [**Instagram**](https://www.instagram.com/s.sunhaloo/)
- [**YouTube**](https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg)
- [**GitHub**](https://www.github.com/Sunhaloo)

---

S.Sunhaloo
Thank You!