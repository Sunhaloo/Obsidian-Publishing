---
Alias: C Language Tips
Tag: C
Author: S.Sunhaloo
Type: Random Notes / Tips
Date: 2024-03-09
Status: HOLD
---

## List of Contents

- [[C Tips#Get Rid of ` n` ( Newline Character ) | Get Rid of New Line Character]]
- [[C Tips#Calculate the Size of Arrays ( Not Length of Array ) | Calculate the Size of Arrays in Bytes]]
- [[C Tips#Swapping Values of Two Variables | Swapping Values of Two Variables]]

---

# My Links

- [[C Tips#Socials | Links to Socials]]

---

# Get Rid of `\n` ( Newline Character )

To get rid of new line character in the code below $\downarrow$, use:

```C


// Getting Rid of `\n` ---> Newline Character
scanf("%c");

```

Example Code: Input Character After Integer Input

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

  // Getting Rid of `\n` ---> Newline Character
  scanf("%c");

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

# Calculate the Size of Arrays ( Not Length of Array )

As you know everything has a size in / on computers; files, texts, games.

We measure the size of files / games / etc in:

- From Largest to Smallest ( *there are more, just including the size that we normally use* )
	- Terabyte = 1000 Gigabytes
	- Gigabyte = 1000 Megabytes
	- Megabyte = 1000 Kilobytes
	- Kilobyte = 1000 Bytes
	- Byte = 8 Bits

>Some of you may be asking "*is it not 1024 Bytes?*"
>Yes, but no! The thing is <span style="color: green;">kilo</span>bytes and <span style="color: red;">kibi</span>bytes are 2 **different** things.
>We can also use Google converter if you need to.

>[!tip] Usage
>```C
>
>// Use the function:
>sizeof(insert array here)
>
>```
>- Will return INTEGER

### Example Code:

```C

// Include standard input / output header
#include <stdio.h>
// Include string library / header
#include <string.h>

int main()

{

  // DECLARE ARRAY intials[5]: INTEGER
  int initials[] = {'S', 'U', 'S', 'S', 'Y'};
  // DECLARE ARRAY prices[4]: INTEGER
  double prices[] = {12.50, 9.99, 449.99, 10.00};

  // Display the size ( like actual size in Bytes ) each array

  // Size of Array `initials` in Bytes
  printf("\nSize of Array `initials` = %d Bytes", sizeof(initials));
  printf("\nSize of Array `prices` = %d Bytes\n", sizeof(prices));

  return 0;

}

```


# Swapping Values of Two Variables

In the code below, we are going to learn on how to swap the values of 2 variables

>Bubblesort algorithm will really like this one, because if you know, we are going to be using one of the greatest variable name to have ever existed: `temp`, Welcome to the party again Sir.

## With Integers

```C

// Include standard input / output header
#include <stdio.h>

// FUNCTION display_values(int var1, int var2, int temp)
void display_values(int var1, int var2, int temp){

  // Output the values of
    // variable_1
    // variable_2
    // temp

  printf("\nValues of Variables:\n");

  printf("variable_1 = %d", var1);
  printf("\ntemp = %d", temp);
  printf("\nvariable_2 = %d\n", var2);

}

int main()

{

  // DECLARE variable_1: INTEGER
  int variable_1 = 5;
  // DECLARE variable_2: INTEGER
  int variable_2 = 10;

  // DECLARE temp: INTEGER
  // Will be used as a temporary holder for swapping values
    // Initialised with value '0'; else will be some random fucking number
  int temp = 0;

  // Call Function `display_values` to output the values of variables
  display_values(variable_1, variable_2, temp);

  // Swapping Values
  temp = variable_1;
  variable_1 = variable_2;
  variable_2 = temp;

  // Output values of variables after swapping
  display_values(variable_1, variable_2, temp);

  return 0;
}

```

## With Arrays / Characters / Strings

>[!note] Same principle as above $\uparrow$ but `temp` need to be assigned a size!

In this case, the principle is similar; but the method we use to move / swap the values from one variable to the next is completely different.

We are going to be using the `strcpu()` Function to copy values. This is done using the `<string.h>` library.

```C

// Include standard input / output header
#include <stdio.h>
// Include string manipulation library
#include <string.h>


// FUNCTION display_values(char var1, char var2, char temp)
void display_values(char var1[], char var2[], char temp[]){

  // Output the values of
    // variable_1
    // variable_2
    // temp

  printf("\nValues of Variables:\n");

  printf("variable_1 = %s", var1);
  printf("\ntemp = %s", temp);
  printf("\nvariable_2 = %s\n", var2);

}

int main()

{

  // DECLARE variable_1: STRING
  char variable_1[25] = "Mazda";
  // DECLARE variable_2: STRING
  char variable_2[25] = "Nissan";

  // DECLARE temp: STRING
  // Will be used as a temporary holder for swapping values
  char temp[20];

  // Call Function `display_values` to output the values of variables
    // `temp` variable should not have any value Initially
  display_values(variable_1, variable_2, temp);

  // Swapping Values
    // Same Principle but Different Format
  strcpy(temp, variable_1);
  strcpy(variable_1, variable_2);
  strcpy(variable_2, temp);

  // Output values of variables after swapping
  display_values(variable_1, variable_2, temp);

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