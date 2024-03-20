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

# Calculate the Size of Arrays

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

---

# Socials

- [**Instagram**](https://www.instagram.com/s.sunhaloo/)
- [**YouTube**](https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg)
- [**GitHub**](https://www.github.com/Sunhaloo)

---

S.Sunhaloo
Thank You!