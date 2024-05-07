---
Alias: Insertion Sort ( Simpler Sorting Algo )
Tag: python, sorting_algo
Author: S.Sunhaloo
Type: Sorting Algorithm
Date: 2023-09-01
Status: In-Progress / Check Transposed
---

## List of Contents

## [[Arrays, Tuples, Sets - Python#One Dimensional Arrays ( 1D-Arrays )| One Dimensional Array]]

- [[Insertion Sort - Python#What is Insertion Sort? | What is Insertion Sort?]]
	- [[Insertion Sort - Python#Some advantages | Advantages]]
	- [[Insertion Sort - Python#Some Disadvantages | Disadvantages]]
- [[Insertion Sort - Python#Insertion Sort Code - 1D Array | Insertion Sort Code - 1D Array]]
	- [[Insertion Sort - Python#Template 1D-Array| Template]]
- [[Insertion Sort - Python#Example 1D-Array| Example]]

---

## [[Arrays, Tuples, Sets - Python#Two Dimensional Arrays ( 2D-Arrays )| Two Dimensional Array]]

- [[Insertion Sort - Python#Insertion Sort Code - 2D Array | Insertion Sort Code - 2D Array]]
	- [[Insertion Sort - Python#Template 2D-Array | Template]]
		- [[Insertion Sort - Python#Method 1 Sorting *rows* **only** | Sorting Rows Only]]
		- [[Insertion Sort - Python#Method 2 Sorting **entire** array | Sorting All Values In Array]]

---

My Links

- [[Insertion Sort - Python#Socials | Links to Social]]

---

# What is Insertion Sort?

This is another [[Python Data View#Sorting Algorithms ( 2D and 1D Array )| sorting algorithm]] that is works well if programmer need to find a value quickly.

The *calculation* of Insertion Sort is as follow:

1. It will find the **length** of array
2. There is a variable which will hold:
	- The **value** at *index* `x`
3. Another variable will hold the value at:
	- `x + 1`
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

# FUNCTION insertion_sort(DECLARE ARRAY array: INTEGER)
def insertion_sort(array):

    # DECLARE length_array: INTEGER
    # Calculates length of array
    length_array = len(array)

    # DECLARE i: INTEGER
    # "for" loop that starts at index 1 instead of 0
    for i in range(1, length_array):

        # DECLARE values: INTEGER
        # Values at address "i"
        values = array[i]

        # DECLARE j: INTEGER
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

>See it's really simple, that is why is is really easy to implement into code as the number of lines is oh so little.

## Example: 1D-Array

### Example 1: Complete Code 1D-Array

```python

# DECLARE ARRAY array[6]: INTEGER
array = [11, 9, 29, 7, 2, 15, 28]

# FUNCTION insertion_sort(DECLARE ARRAY array: INTEGER)
def insertion_sort(array):

    # DECLARE length_array: INTEGER
    # Calculates length of array
    length_array = len(array)

    # DECLARE i: INTEGER
    # "for" loop that starts at index 1 instead of 0
    for i in range(1, length_array):

        # DECLARE values: INTEGER
        # Values at address "i"
        values = array[i]

        # DECLARE j: INTEGER
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

# Calling Function to `main` Program
insertion_sort(array)

# DECLARE count: INTEGER
# Displaying Array
for count in array:

    # Output all the values of array on separate lines
    print(count)

```

# [[Arrays, Tuples, Sets - Python#Two Dimensional Arrays ( 2D-Arrays )| Two Dimensional Array]]

What can I say, the *codes* below will show you how to make **insertion sort** for *2D-Arrays*.

# Insertion Sort Code - 2D Array

## Template: 2D-Array

This is only the [[Functions and Procedures - Python#Example 2 Insertion Sort| function]], thus is will **not** run on its own.

### Method 1: Sorting *rows* **only**

>[!warning]
>This code will **only** sort the the values in each *rows*

```python

# Sorting ROWS Only

# FUNCTIOn insertion_sort(DECLARE ARRAY grid: INTEGER)
def insertion_sort(grid):

    # DECLARE rows: INTEGER
    # Stepping through each row
    for rows in range(len(grid)):

        # DECLARE cols: INTEGER
        # Stepping through each column
        for cols in range(1, len(grid[rows])):

            # DECLARE value: INTEGER
            # Values at "first" address
            values = grid[rows][cols]

            # DECLARE k: INTEGER
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

---

# Socials

- [**Instagram**](https://www.instagram.com/s.sunhaloo/)
- [**YouTube**](https://www.youtube.com/@s.sunhaloo539/streams)
- [**GitHub**](https://www.github.com/Sunhaloo)

---
S.Sunhaloo
Thank You!