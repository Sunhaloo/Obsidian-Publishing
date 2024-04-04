---
Alias: Insertion Sort ( Simpler Sorting Algo )
Tag: python, sorting_algo
Author: S.Sunhaloo
Type: Sorting Algorithm
Date: 2023-09-01
Status: In-Progress / Check Transposed
---

## List of Contents

## [[Arrays - Python#One Dimensional Arrays ( 1D-Arrays ) | One Dimensional Array]]

- [[Insertion Sort - Python#What is Insertion Sort? | What is Insertion Sort?]]
	- [[Insertion Sort - Python#Some advantages | Advantages]]
	- [[Insertion Sort - Python#Some Disadvantages | Disadvantages]]
- [[Insertion Sort - Python#Insertion Sort Code - 1D Array | Insertion Sort Code - 1D Array]]
	- [[Insertion Sort - Python#Template 1D-Array| Template]]
- [[Insertion Sort - Python#Examples 1D-Array| Example]]

---

## [[Arrays - Python#Two Dimensional Arrays ( 2D-Arrays ) | Two Dimensional Array]]

- [[Insertion Sort - Python#Insertion Sort Code - 2D Array | Insertion Sort Code - 2D Array]]
	- [[Insertion Sort - Python#Template 2D-Array | Template]]
		- [[Insertion Sort - Python#Method 1 Sorting *rows* **only** | Sorting Rows Only]]
		- [[Insertion Sort - Python#Method 2 Sorting **entire** array | Sorting All Values In Array]]
	- ****

---

My Links

- [[Insertion Sort - Python#Socials | Links to Social]]

---

# What is Insertion Sort?

This is another [[Python HSC Data View#Sorting Algorithms ( 2D and 1D Array )| sorting algorithm]] that is works well if programmer need to find a value quickly.

The *calculation* of Insertion Sort is as follow:

1. It will find the **length** of array
2. There is a variable which will hold:
	- The **value** at *index* "*x*"
3. Another variable will hold the value at:
	- "*x + 1*"
4. It compares the second value to the first value
	- Then swap accordingly ( ascending / descending order )

# Some advantages

- It is easy and faster to implement
	- Because lines of code is less than bubble sort
- More efficient than bubble sort
- Can sort data as it receives it

# Some Disadvantages

- Slow on large data set ( arrays )
- Does not perform well compared to more advanced sorting algorithms

# Insertion Sort Code - 1D Array

## Template: 1D-Array

This is only the [[Functions and Procedures - Python#Example 2 Insertion Sort| function]], thus is will **not** run on its own.

```python

# Insertion Sort Function 1D-Array

# Function with identifier name "insertion_sort"

# In this function. we need to pass:
# array
def insertion_sort(array):

    # Calculates length of array
    length_array = len(array)

    # "for" loop that starts at index 1 instead of 0
    for i in range(1, length_array):

        # Values at address "i"
        values = array[i]

        # Values to the left of "i" (  one before "i")
        j = i - 1

        # Condition to enter "while" loop
        while j >= 0 and array[j] > values:

            # Swapping Part
            array[j + 1] = array[j]

            # Decrease "j" by 1
            j = j - 1

        # If array is already sorted
        array[j + 1] = values

```

>See it's really simple, that is why is is really easy to implement into code as the number of lines is oh so little

## Examples: 1D-Array

### Example 1: Complete Code 1D-Array

```python

# Insertion Sort

# Array with identifier name "array"
array = [11, 9, 29, 7, 2, 15, 28]

# Function with identifier name "insertion_sort"

# In this function. we need to pass:
# array
def insertion_sort(array):

    # Calculates length of array
    length_array = len(array)

    # "for" loop that starts at index 1 instead of 0
    for i in range(1, length_array):

        # Values at address "i"
        values = array[i]

        # Values to the left of "i" (  one before "i")
        j = i - 1

        # Condition to enter "while" loop
        while j >= 0 and array[j] > values:

            # Swapping Part
            array[j + 1] = array[j]

            # Decrease "j" by 1
            j = j - 1

        # If array is already sorted
        array[j + 1] = values

# Calling Functions
insertion_sort(array)

# Displaying Array
for count in array:

    # Output all the values of array on separate lines
    print(count)

```

# [[Arrays - Python#Two Dimensional Arrays ( 2D-Arrays ) | Two Dimensional Array]]

What can I say, the *codes* below will show you how to make **insertion sort** for *2D-Arrays*

# Insertion Sort Code - 2D Array

## Template: 2D-Array

This is only the [[Functions and Procedures - Python#Example 2 Insertion Sort| function]], thus is will **not** run on its own.

### Method 1: Sorting *rows* **only**

>[!warning]
>This code will **only** sort the the values in each *rows*

```python

# Insertion Sort 2D-Array

# Sorting ROWS Only

# Function with identifier name "Insertion_Sort"

# In this function, we could pass our
# array --> In this case our parameter is called "grid"
def Insertion_Sort(grid):

    # Stepping through each row
    for rows in range(len(grid)):

        # Stepping through each column
        for cols in range(1, len(grid[rows])):

            # Values at "first" address
            values = grid[rows][cols]

            # Value to the left of "first" address
            k = cols -1

            # Condition to enter "while" loop
            while k >= 0 and grid[rows][k] > values:

                # Swapping Part
                grid[rows][k + 1] = grid[rows][k]

                # Decrease "k" by 1
                k -= 1

            # If values are already sorted
            grid[rows][k + 1] = values

```

### Method 2: Sorting **entire** array

>[!warning]
>**NOT COMPLETED**

```python

def insertion_sort_2d_array(arr):

    sorted_arr = [[0 for _ in range(len(arr[0]))] for _ in range(len(arr))]

  

    # Sort each row using insertion sort

    for i in range(len(arr)):

        sorted_row = sorted(arr[i])

        sorted_arr[i] = sorted_row

  

    # Transpose the array to sort columns using insertion sort

    transposed_arr = [[sorted_arr[j][i] for j in range(len(sorted_arr))] for i in range(len(sorted_arr[0]))]

  

    # Sort each column using insertion sort

    for i in range(len(transposed_arr)):

        transposed_arr[i] = sorted(transposed_arr[i])

  

    # Transpose back to the original array

    arr[:] = [[transposed_arr[j][i] for j in range(len(transposed_arr))] for i in range(len(transposed_arr[0]))]

```

---

# Socials

- [**Instagram:**](https://www.instagram.com/s.sunhaloo/)
- [**YouTube:**](https://www.youtube.com/@s.sunhaloo539/streams)

---
Thank You!