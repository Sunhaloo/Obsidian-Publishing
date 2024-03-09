---
Alias: C Language Tips
Tag: C
Author: S.Sunhaloo
Type: Random Notes / Tips
Date: 2024-03-09
Status: HOLD
---

## List of Contents



---

# My Links

- [[C Tips#Socials | Links to Socials]]

---

# Get Rid of `\n` ( Newline Character )

To get rid of new line character in the code below $\downarrow$, use:

```C


// Getting Rid of `\n` ---> Newline Character
scanf("c");

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
  scanf("c");

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

---

# Socials

- [**Instagram**](https://www.instagram.com/s.sunhaloo/)
- [**YouTube**](https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg)
- [**GitHub**](https://www.github.com/Sunhaloo)

---

S.Sunhaloo
Thank You!