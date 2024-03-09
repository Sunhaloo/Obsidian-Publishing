---
Alias: Conditions and Loops in C
Tag: C, basics
Author: S.Sunhaloo
Type: Conditions / Statements
Date: 2024-02-22
Status: In-Progress
---

## List of Contents

- [[Selection and Iteration - C#Selections and Iterations Introduction | Selections and Iterations Introduction]]

---

- [[Selection and Iteration - C#Conditional Statements | Conditional Statements]]
	- [[Selection and Iteration - C#`if` Statements | IF Statements]]
	- [[Selection and Iteration - C#`switch` / CASE Statements | CASE Statements]]

---

- [[Selection and Iteration - C#Pre-Condition Loops | Pre-Condition Loops]]
	- [[Selection and Iteration - C#`for` Loops | FOR Loops]]
	- [[Selection and Iteration - C#`while` Loops | WHILE Loops]]
	- [[Selection and Iteration - C#`do ... while` Loops | DO WHILE Loops]]

---

- [[Selection and Iteration - C#Nested Loops | Nested Loops]]
	- [[Selection and Iteration - C#Example Code | Example Code]]

---

### Another Little Thing related to Loops

- [[Selection and Iteration - C#Break Continue | Break | Continue]]
	- [[Selection and Iteration - C#Break | Break]]
	- [[Selection and Iteration - C#Continue | Continue]]


---

## My Links

- [[Selection and Iteration - C#Socials | Links to Socials]]

---

# Selections and Iterations Introduction

If you want to learn more about selections and iterations; please refer to the <span style="color: yellow;">Python</span> notes down below $\downarrow$.

![[Selection and Iteration - Python#What is a Selection?]]

![[Selection and Iteration - Python#What is an Iteration?]]

---

# Conditional Statements

>We are about to eat some delicious things!

## `if` Statements

>[!note]
>Again if you need a simple explanation, please refer to [Google](https://www.google.com) for more information as they are the fundamentals of computer programming and you should already know these fundamentals.

### Example 1: Simple Age Verification

```C

// `if` Statements

// Include standard input / output header
#inlude <stdio.h>

int main()

{

	// Ask the user to enter their age
    printf("Please Enter Your Age: ");
    scanf("%d", &age);

	// Conditions to be able to sign up
    if( age <= 17 ){

        printf("You are to young to sign up!");

    }
    else if( age >= 18 && age <= 30 ){

        printf("You have the age to sign up!");

    }
    else{

        printf("You are too old to sign up!");

    }

    return 0;

}

```

>[!note]
>The symbol `&&` means the **AND** operator in C!

## `switch` / CASE Statements

So in most ( *if not all of them* ) languages we do not use "*CASE*" per se. We rather use the `switch` function to be able to use `CASE` functions

### Example 1: Simple Grade Checker

```C

// `switch` / Switch Case Statements

// Include standard input / output header
#include <stdio.h>

int main()
{

    // DECLARE grade: CHAR
    char grade;

    // Ask the user to enter grade
    printf("\nPlease Enter Your Grade: ");
    scanf("%c", &grade);

    switch(grade){
        case 'A':
            printf("\nExcellent, Keep Up The Performance");
            break;
        case 'B':
            printf("\nYou Could Have Done Better");
            break;
        case 'C':
            printf("\nYou Need To Put In More Effort");
            break;
        case 'D':
            printf("\nMust Focus on The Real Things In Life");
            break;
        case 'E':
            printf("\nYou Nearly Failed; Because You Have Not Been Paying Attention");
            break;
        case 'F':
            printf("\nLost Cause ---> You FAILED!");
            break;
        default:
            printf("\nPlease Enter A Grade From 'A' to 'F'");

	return 0;

    }
    
}

```

>[!warning] Inclusion of `break`
>Why do we need to include `break` at the end of each `case`?
>- If we do **not** `break`; then it will also continue to **execute** the next `case`.
>Hence, remember to add our little `break` | Because in this case, `break` are more like "*brakes*".

# Pre-Condition Loops

As you know, *pre-condition* loops will read *condition* **first** and then executes it's *statements*. Again, for more information refer to [Google](https://www.google.com) for more information.

## `for` Loops

Like I cannot explain this; like it is so simple that is become difficult to explain it. We just have to **CODE**!

Below $\downarrow$ you will find the *template* for `for` loops.

```C

for( initialisation, condition, update ){

	// Statements

}

```

### Example 1: Writing User's Name 5 Times

>[!bug]
># NOT WORKING $\downarrow$

```C

// Include standard input / output header
#include <stdio.h>

int main() {
  
  // Declaration

  // DECLARE user: STRING
  char user[25];

  // Ask user to enter his username
  printf("Please Enter Your UserName: ");
  scanf("%s", user);

  // Output his username 5 times
  for( int x = 0; x <= 5; x++ ){
    printf("\n%s", user);
  }

  // Adds space after writing last user's username
  printf("\n");
  printf("\n");

  return 0;
}


```

>[!note]
>You can *declare* your variables like **counters** inside the `for` loop ( as seen above $\uparrow$ ).

### Example 2: Counting From 0 To 100

```C

// Include standard input / output header
#include <stdio.h>

int main()

{

	printf("\n");
	printf("Counting From 0 to 100\n");
	printf("\n");

	// We could have also used `x += 1` or any number to increment
	for(int x = 0; x <= 100; x++){
		printf("%d\n", x);
	}

	printf("\n");

	return 0;

}

```

### Example 3: Counting Down From 10 to 0

```C

// Include standart input / output header
#include <stdio.h>

int main()

{

	printf("\n");
	printf("Counting Down From 10 to 0\n");
	printf("\n");

	for(int i = 10; i >= 0; i--){

		printf("%d\n", i);

	}

	return 0;

}

```

## `while` Loops

So this is not like the `for` loop; where we have a *declaration*, *condition* and *update* part. This is simply like in [[Selection and Iteration - Python#While Loops | Python's While Loops]]. Where we only need to put the *condition* / *statement* inside `()`.

### Example 1: Incrementing Until Reaching 10

```C

// Include standart input / output header
#include <stdio.h>

int main()

{

  int y = 0;

  while(y <= 9){

    printf("\n");
    printf("Less than 10 Incrementing\n");
    printf("\n");

    y++;
  
    printf("%d\n", y);

  }

	return 0;

}

```

### Example 2: Continue to Ask for User's Name

```C

// Include standard input / output header
#include <stdio.h>
// Include string function ---> allows use to use function `fgets`
#include <string.h>

int main()

{

    // Declaration
    
    // DECLARE name: STRING
    char name[25];

    // Asks the user to input his name
    printf("\nPlease Enter Your Name: ");
    fgets(name, 25, stdin);
    name[strlen(name) - 1] = '\0';

    while(strlen(name) == 0){

        // Output message to user
        printf("You Must Enter Your Name!");

        // Ask for user's name again
        printf("\nPlease Enter Your Name: ");
        fgets(name, 25, stdin);
        name[strlen(name) - 1] = '\0';

    }

    // Output user's name to the screen
    printf("\nYour Name is %s", name);

    return 0;

}

```

# Post-Condition Loops

This is basically the opposite of [[Selection and Iteration - C#Pre-Condition Loops | pre-conditioned loops]]. Now, we are going to **executes** the *statements* first then we will read the *condition*

## `do ... while` Loops

This one should fall under [[Selection and Iteration - C#`while` Loops | `while` loops]]; but because, it is *post-conditioned* its right here motherfucker.

>I do whatever the fuck I want; [DILLIGAF](https://www.urbandictionary.com/define.php?term=Dilligaf)

### Example 1: Continue to Enter Numbers Until Number Equal To 0

```C

// Include standard input / output header
#include <stdio.h>

int main()

{
  // Declaration
  // DELCLARE num: INTEGER
  int num;
  // DELCLARE sum: INTEGER
  int sum;

  do {

    printf("\n");
    // Ask the user to enter a number
    printf("Please Enter A Number: ");
    scanf("%d", &num);

    // Check if number if greater than 0
    if (num > 0) {
      sum += num;
    }
    // Until the user enters the number '0' ==> Stops Program
  } while (num >= 0);

  // Outputs the sum / total of numbers
  printf("\nSum of Numbers = %d\n", sum);

  printf("\n");

  return 0;
}

```

# Nested Loops

## Example Code

This code will ask the user to enter the number of rows and columns and a symbol ( *could be anything* ). Will display / make an *image* with that symbol in that *size*.

```C

// Include standard input / output header
#include <stdio.h>

int main()

{
  // Declaration
  // DECLARE rows: INTEGER
  int rows;
  // DECLARE cols: INTEGER
  int cols;
  // DECLARE user_symbol: CHAR
  char user_symbol;

  // Ask the user to enter number of rows
  printf("\nPlease Enter The Number Of Rows: ");
  scanf("%d", &rows);
  // Ask the user to enter number of columns
  printf("Please Enter The Number Of Columns: ");
  scanf("%d", &cols);

  // Allows us to switch from input of Integers to Characters  
  getchar();

  // Ask the user to enter symbol to print / output
  printf("Please Enter The Symbol To Be Used: ");
  scanf("%c", &user_symbol);

  // Displaying the "image"
  for (int x = 1; x <= rows; x += 1) {
    for (int y = 1; y <= cols; y += 1) {
      printf("%c", user_symbol);
    }
    printf("\n");
  }

  return 1;
}

```

# Break | Continue

This is similar ( *in theory not syntax wise* ) to [[Selection and Iteration - Python#Break Continue Pass | Python Break and Continue]]

## Break

### Example: The Code will Stop at value 11

```C

// Include standard input / output header
#include <stdio.h>

int main()

{
  // Declaration
  // DECLARE i: INTEGER
  int i;

  // Count from 0 to 20
  for(i = 0; i <= 20; i++){

    // Stop the program when `i` is equal to '11'
    if(i == 11){

      // Stops the Program
      break;

    }

    // Output the numbers
    printf("%d\n", i);
  }

  return 0;

}

```

## Continue

### Example: Continue to Print Out Numbers

This is basically the opposite of `break`, where the program will continue to execute what it needs to execute.

>I will be using the same program as above; but instead of `break`; will use `continue`

```C

// Include standard input / output header
#include <stdio.h>

int main()

{
  // Declaration
  // DECLARE i: INTEGER
  int i;

  // Count from 0 to 20
  for(i = 0; i <= 20; i++){

    // Continue the program when `i` is equal to '11'
    if(i == 11){

      // Does not Stop the Program
      break;

    }

    // Output the numbers
    printf("%d\n", i);
  }

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