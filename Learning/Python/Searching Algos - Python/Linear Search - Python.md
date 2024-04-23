---
Alias: Linear Search In Python
Tag: python, searching_algo, 1D-Array, 2D-Array
Author: S.Sunhaloo
Type: Searching Algorithm
Date: 2023-09-13
Status: Completed
---

## List of Contents

- [[Linear Search - Python#What is a Linear Search? | What is a Linear Search?]]

---
## Linear Search

## [[Arrays - Python#One Dimensional Arrays ( 1D-Arrays ) | One Dimensional Arrays]]

- [[Linear Search - Python#Linear Search Code - 1D Arrays | Linear Search Code]]
	- [[Linear Search - Python#Template 1D-Array| Template Function]]
	- [[Linear Search - Python#Example 1D-Array| Example]]

---

## [[Arrays - Python#Two Dimensional Arrays ( 2D-Arrays ) | Two Dimensional Arrays]]

- [[Linear Search - Python#Linear Search Code - 2D Arrays | Linear Search Code]]
	- [[Linear Search - Python#Template 2D-Array | Template Function]]
		- [[Linear Search - Python#Method 1 Using `enumerate` function | Using Enumerate Function]]
		- [[Linear Search - Python#Method 2 Using `range()` function | Using Range Function]]
	- [[Linear Search - Python#Example 2D-Array | Example]]

---

My Links

- [[Linear Search - Python#Socials | Links to Socials]]

---

# [[Arrays - Python#One Dimensional Arrays ( 1D-Arrays ) | One Dimensional Arrays]]

# What is a Linear Search?

This is one of the simplest [[Python Data View#Searching Algorithms| searching algorithm]]. This is because it searches the array **sequentially**. In fact, the another name for linear search is *sequential search*.

In linear search the array does **not** need to be *sorted*.

The *calculations* of linear search is written below:

1. We have to calculate the **length** of *array*
2. There is a ( `for` )  loop which will step through the array
	- If the **value** at that *address* is found
		- It returns the **address** of the value
3. If value has **not** been found it exits the loop
	- By return `-1` or `False`

# Some Advantages

- Very easy to implement in code
- Fast on ( and only on ) small arrays
- The array does not need to be sorted
- Linear Search if not affected by the data movement
	- Data being:
		- Added to array
		- Removed from array

# Some Disadvantages

- Very slow for large data sets ( arrays )
	- Because it searches the array sequentially

> For more advantages and disadvantages; just [Google](https://google.com) them. The thing is that you need to know is:
> - Understand how it works
> - The actually program code

# Linear Search Code - 1D Arrays

## Template: 1D-Array

This is only the [[Functions and Procedures - Python#Example 4 Linear Search| function]], thus is will **not** run on its own.

```python

# FUNCTION linear_search(DECLARE ARRAY array: INTEGER, DECLARE user_find: INTEGER)
def linear_search(array, user_find):

    # DECLARE i: INTEGER
    # Loop steps through array
    for i in range(0, len(array)):

        # If value is found
        if array[i] == user_find:

            # Returns the address of "user_find"
            return i

    # If search value has not been found
    return -1

```

## Example: 1D-Array

### Example 1: Complete Code for 1D-Array

```python

print()

# DECLARE ARRAY numbers: INTEGER
numbers = []

# Exception Handling
try:

    print()

    # DECLARE array_size: INTEGER
    # Variable "array_size" will hold the "size of the array"
    array_size = int(input("Please Enter Size Of Array: "))

    print()

# If user enter any character other than Integers
except ValueError:

    print()
    # Outputs appropriate message
    print("Please Enter Integer Values Only!")
    print()

# DECLARE x: INTEGER
# Asking the user to enter data into array
for x in range(array_size):

    # DECLARE user_input: STRING
    # Asking the user to enter a value
    user_input = input("Please Enter A Number: ")

    # Check if user_input is a digit
    if user_input.isdigit():

        # If "user_input" is an integer
        # "user_input" will be converted to Integer
        user_input = int(user_input)

    # If user does not input Integers
    else:

        # Ouptputs appropriate message
        print("Please Enter Whole Numbers Only!")

    # When "user_input" is of type Integer
    # Appends the value to the array
    numbers.append(user_input)

print()

# DECLARE user_find: INTEGER
# Variable "user_find" will hold serach value
user_find = input("Please Enter A Number To Find: ")

print()

# If search value is an integer
if user_find.isdigit():

    # "user_find" will be converted to Integer
    user_find = int(user_find)

# If user did not enter an integer number
else:

    # Outputs appropriate message
    print("Please Enter Whole Numbers Only!")

# FUNCTION linear_search(DECLARE ARRAY array: INTEGER, DECLARE user_find: INTEGER)
def linear_search(array, user_find):

    # DECLARE i: INTEGER
    # Loop steps through array
    for i in range(0, len(array)):

        # If value is found
        if array[i] == user_find:

            # Returns the address of "user_find"
            return i

    # If search value has not been found
    return -1

# Calling Function to `main` Program
search_value = linear_search(numbers, user_find)

# Displaying search_value
print(search_value)

```

# [[Arrays - Python#Two Dimensional Arrays ( 2D-Arrays ) | Two Dimensional Arrays]]

Again, it will be of the **same principle** as the *1D-Arrays*. But now, we will have **2 loops** so that we can cycle through the whole *2D-Array*

# Linear Search Code - 2D Arrays

## Template: 2D-Array

### Method 1: Using `enumerate` function

>[!info]
>Using the enumerate function will make it very easy to implement ( *write the code* )
>But I am not accustomed to *enumerate* yet
>- So I it will also be providing [[Linear Search - Python#Method 2 Using *range()* function| using simple range function]] below $\downarrow$.
>- So that you can understand **Linear Search** better

```python

# DECLARE ARRAY array[2, 2]: INTEGER
array = [

    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]

]

print()

# Exception Handling
try:

    # DECLARE user_input: INTEGER
    # Asking the user to enter a value to find
    user_input = int(input("Please Enter A Value To Find: "))

# If user a value of another data type ( except integer values )
except ValueError:

    # Output appropriate message
    print()
    print("Please Enter Integer Values Only!")
    print()

# FUNCTION linear_search(DECLARE ARRAY array: INTEGER, DECLARE value_to_search: INTEGER)
def linear_search(array, value_to_search):

    # DECLARE index_row, row: INTEGER
    # Steps through rows in array
    for index_row, row in enumerate(array):

            # DECLARE index_cols, cols: INTEGER
            # Steps through cols in array
            for index_cols, cols in enumerate(row):

                # If value to search has been found
                if cols == value_to_search:

                    # Return the address of search value
                    return index_row, index_cols

    # If search value has not been found
    return -1

# Calling Function to `main` Program
result = Linear_Search(array, user_input)

# Displaying result
if result != 1:

    # If value has been found
    print(f"Value Has Been Found At: {result}")

else:

    # If value has NOT been found
    print("Value Has NOT Been Found")

print()
print("Displaying Array")
print()

# DECLARE x: INTEGER
# Displaying Array
for x in array:

    print(x)

```

### Method 2: Using `range()` function

This is the [[Functions and Procedures - Python|function]] only and it will **not** run on its own.

```python

# FUNCTION linear_search(DECLARE ARRAY array: INTEGER)
def linear_search(array):

    # Exception Handling
    try:

        # DECLARE array_length: INTEGER
        # Which will hold our length of array
        array_length = len(array)

        # DECLARE user_search: INTEGER
        # Asking the user to input a value to search
        user_search = int(input("Please Enter A Value To Find: "))

        # DECLARE row: INTEGER
        # Loop steps through rows
        for row in range(0, array_length):

            # Loop steps through columns
            # DECLARE cols: INTEGER
            for cols in range(0, array_length):

                # If value has been found
                if array[row][cols] == user_search:

                    # Returns the address of "user_search"
                    return row, cols

        # If value has not been found
        return -1

```

## Example: 2D-Array

### Example 1: Complete Code for 2D-Array

```python

# DECLARE ARRAY array[2, 2]: INTEGER
array = [

    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]

]

print()

# FUNCTION linear_search(DECLARE ARRAY array: INTEGER)
def linear_search(array):

    # Exception Handling
    try:

        # DECLARE array_length: INTEGER
        # Which will hold our length of array
        array_length = len(array)

        # DECLARE user_search: INTEGER
        # Asking the user to input a value to search
        user_search = int(input("Please Enter A Value To Find: "))

        # DECLARE row: INTEGER
        # Loop steps through rows
        for row in range(0, array_length):

            # Loop steps through columns
            # DECLARE cols: INTEGER
            for cols in range(0, array_length):

                # If value has been found
                if array[row][cols] == user_search:

                    # Returns the address of "user_search"
                    return row, cols

        # If value has not been found
        return -1

    # If user inputs other than "integer" values
    except ValueError:

        # Output appropriate message
        print()
        print("Please Enter Integer Values Only")
        print()

# Calling Function to `main` Program
result = linear_search(array)

if result != -1:

    # If value has been found
    print(f"Value Has Been Found At: {result}")

else:

    # If value has NOT been found
    print("Values Has NOT Been Found")

print()
print("Displaying Array")
print()

# DECLARE x: INTEGER
# Displaying Array
for x in array:

    print(x)

```

---

# Socials

- [**Instagram**](https://www.instagram.com/s.sunhaloo/)
- [**YouTube**](https://www.youtube.com/@s.sunhaloo539/streams)
- [**GitHub**](https://www.github.com/Sunhaloo)

---
S.Sunhaloo
Thank You!