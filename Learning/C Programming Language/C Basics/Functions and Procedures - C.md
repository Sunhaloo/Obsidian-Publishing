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

## Simple Examples

### Example 1: Output Welcome Screen with Function

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

---

# Socials

- [**Instagram**](https://www.instagram.com/s.sunhaloo/)
- [**YouTube**](https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg)
- [**GitHub**](https://www.github.com/Sunhaloo)

---

S.Sunhaloo
Thank You!