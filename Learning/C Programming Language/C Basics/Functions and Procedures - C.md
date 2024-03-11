---
Alias: Functions and Procedures C Language
Tag: C, basics
Author: S.Sunhaloo
Type: Functions / Procedures
Date: 2024-03-09
Status: In-Progress
---

## List of Contents


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

```C



```

---

# Socials

- [**Instagram**](https://www.instagram.com/s.sunhaloo/)
- [**YouTube**](https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg)
- [**GitHub**](https://www.github.com/Sunhaloo)

---

S.Sunhaloo
Thank You!