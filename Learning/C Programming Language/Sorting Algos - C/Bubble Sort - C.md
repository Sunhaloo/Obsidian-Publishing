---
Alias: Bubble Sort Algorithm in C
Tag: C, sorting_algo
Author: S.Sunhaloo
Type: Sorting Algorithm
Date: 2024-04-03
Status: In-Progress
---

## List of Contents

### One Dimensional Array

- [[Bubble Sort - C#Bubble Sort Code - 1D Array | Bubble Sort Code - 1D Array]]
	- [[Bubble Sort - C#Function ( 1D-Array ) | Function ( 1D-Array )]]
	- [[Bubble Sort - C#Complete Code ( 1D-Array ) | Complete Code ( 1D-Array )]]

### Two Dimensional Array



---

### My Links

- [[Bubble Sort - C#Socials | Links to Socials]]

---

>[!note]
>If you want to learn more about Bubble Sort Algorithm
>I have made a simple note [[Bubble Sort - Python#What is Bubble Sort? | here]]. If you want to learn more about time complexity and stuff; just use Google / use YouTube University!

# Bubble Sort Code - 1D Array

### Function ( 1D-Array )

```C

// Include standard input / output header
#include <stdio.h>
// Include boolean data type
#include <stdbool.h>

// FUNCTION bubble_sort(int array, int array_length)
// Bubble Sort Optimised
void bubble_sort(int array[], int array_length){

  // DECLARE update: BOOLEAN
  bool update = true;
  // DECLARE swap: INTEGER
  int swap = 0;
  // DECLARE temp: INTEGER
    // Initialise `temp` to 0; so that it does not become some random fucking value due to memory shitting itself
  int temp = 0;

  // Condition to enter `while` loop
  while(update == true && array_length > 1){

    // Variable `update` needs to become 'false'
      // So that we know that the swapping has happened
    update = false;

    // Number of times it will iterate through array
    for(int x = 0; x < array_length - 1; x++){
      // Checks every value in array
      for(int y = 0; y < array_length - 1; y++){
        // Sort in Ascending Order
        if(array[y] > array[y + 1]){

          // Swap Values
          temp = array[y];
          array[y] = array[y + 1];
          array[y + 1] = temp;
          swap++;

        }
      }
    }
  }

}

```

### Complete Code ( 1D-Array )

```C

// Include standard input / output header
#include <stdio.h>
// Include boolean data type
#include <stdbool.h>

// FUNCTION bubble_sort(int array, int array_length)
// Bubble Sort Optimised
void bubble_sort(int array[], int array_length){

  // DECLARE update: BOOLEAN
  bool update = true;
  // DECLARE swap: INTEGER
  int swap = 0;
  // DECLARE temp: INTEGER
    // Initialise `temp` to 0; so that it does not become some random fucking value due to memory shitting itself
  int temp = 0;

  // Condition to enter `while` loop
  while(update == true && array_length > 1){

    // Variable `update` needs to become 'false'
      // So that we know that the swapping has happened
    update = false;

    // Number of times it will iterate through array
    for(int x = 0; x < array_length - 1; x++){
      // Checks every value in array
      for(int y = 0; y < array_length - 1; y++){
        // Sort in Ascending Order
        if(array[y] > array[y + 1]){

          // Swap Values
          temp = array[y];
          array[y] = array[y + 1];
          array[y + 1] = temp;
          swap++;

        }
      }
    }
  }

}

// FUNCTION display_array(int array)
void display_array(int array[], int array_length){

  // Display Array
  // DECLARE x: INTEGER
  for(int x = 0; x < array_length; x++){

    // Output the index and value at the index
    printf("\nIndex: %d | Value = %d", x, array[x]);

  }

  printf("\n");

}

int main()

{

  // DECLARE ARRAY numbers[]: INTEGER
    // Some random size ---> So that we can make useof 
  int numbers[] = {5, 4, 3, 2, 1};
  // DECLARE array_length: INTEGER
  int array_length = sizeof(numbers) / sizeof(numbers[0]);

  // Call `display_array`
  // Output Array BEFORE Sorting
  printf("\nUn-Sorted Array\n");
  display_array(numbers, array_length);

  // Calling Function `bubble_sort` to sort array `numbers`
  bubble_sort(numbers, array_length);

  // Call `display_array`
  // Display Array AFTER Sorting
  printf("\nSorted Array\n");
  display_array(numbers, array_length);

  return 0;
}

```

#### Equivalent Python Code

The equivalent Python Code would be down below $\downarrow$. Actually, I have taken the Python Bubble Sort Algorithm and **translated** it into C Code.

![[Bubble Sort - Python#Template - 1D Array | Bubble Sort Python Algorithm]]

>This is just the Function!

---

# Socials

- [**Instagram**](https://www.instagram.com/s.sunhaloo/)
- [**YouTube**](https://www.youtube.com/@s.sunhaloo539/streams)
- [**GitHub**](https://www.github.com/Sunhaloo)

---
Thank You!