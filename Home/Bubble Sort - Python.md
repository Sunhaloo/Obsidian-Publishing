---
Alias: Bubble Sort ( Efficient Sorting Algo )
Tag: python, sorting_algo
Author: S.Sunhaloo
Type: Sorting Algorithm
Date: 2023-09-01
Status: Completed
---

## List of Contents

## [[Arrays - Python#One Dimensional Arrays ( 1D-Arrays )| One Dimensional Array]]

### Bubble Sort ( OPTIMISED )

- [[Bubble Sort - Python#What is Bubble Sort? | What is Bubble Sort?]]
- [[Bubble Sort - Python#Bubble Sort Code - 1D Array | Bubble Sort Code - 1D Array]]
	- [[Bubble Sort - Python#Template - 1D Array| Function Template]]
	- [[Bubble Sort - Python#Examples 1D-Arrays | Examples]]

### Bubble Sort ( UN-OPTIMISED )

- [[Bubble Sort - Python#Bubble Sort ( UN-OPTIMISED ) Code | Bubble Sort ( UN-OPTIMISED ) Code]]
	- [[Bubble Sort - Python#Template - Unoptimised| Function Template]]

---

## [[Arrays - Python#Two Dimensional Arrays ( 2D-Arrays ) | Two Dimensional Arrays]]

- [[Bubble Sort - Python#Bubble Sort Code - 2D Array | Bubble Sort Code - 2D Array]]
	- [[Bubble Sort - Python#Template - 2D Array| Function Template]]
	- [[Bubble Sort - Python#Examples 2D-Arrays | Examples]]

---

My Links

- [[Bubble Sort - Python#Socials | Links to Socials]]

---

# [[Arrays - Python#One Dimensional Arrays ( 1D-Arrays )| One Dimensional Array]]

# What is Bubble Sort?

It is one of the simplest ( maybe the most simplest ) [[Python HSC Data View#Sorting Algorithms| sorting algorithm]] that is out there.

It sorts the array by comparing the values. It will then swap the values as intended ( *ascending* / *descending* order )

>I means that its introduction
>Because it is ( maybe ) the most simplest sorting algorithm out there
>I also need to make the introduction as fucking small as possible

The *calculation* of Bubble Sort is as follows:

1. It will check if the the **length** of array is **greater** than 1
	- If yes, it enters the loop
2. It will have 2 ( "*for*" ) loops
	- One to count how many times it will sort the array
	- Another one to check every value in the array
3. If values at "*x*" ( address ) is **greater** / **smaller** than value at "*y* ( address )
	- It will **swap** the value accordingly
		- Ascending / Descending Order

# Some Advantages

- It is very easy to implement into code
- It consumes less memory than other [[Python HSC Data View#Sorting Algorithms| sorting algorithms]]
- It can detect the array if it is already sorted
	- Meaning does not have to enter loops
		- Thus, making is faster

# Some Disadvantages

- The time complexity is O ( $n2$ )
- Slow for large data sets ( arrays )

> For more advantages and disadvantages; just [Google](https://google.com) them. The thing is that you need to know is:
> - Understand how it works
> - The actually program code

# Bubble Sort Code - 1D Array

## Template - 1D Array

This is only the [[Functions and Procedures - Python#Example 3 Bubble Sort| function]], thus is will **not** run on its own.

```python

# Bubble Sort Function - 1D Array

# Function with identifier name "bubblesort_optimised"

# In this function we need to pass:
# array
def bubblesort_optimised(array):

    # Variable "update" will check if swapping has occured
    update = True

    # Variable "swap" will hold the number of times
    # Algorithm has swapped a value
    swap = 0

    # Condition to enter "while" loop
    while update == True and len(array) > 1:

        # Immediately "update" becomes "False"
        # So that if value has been swapped, it will become "True"
        update = False

        # Number of times it will sort the array
        for x in range(0, len(array) - 1):

            # Checks every value in array
            for y in range(0, len(array) - 1):

                # Sorting in Ascending Order
                if array[y] > array[y +1]:

                    # Swapping Part
                    temp = array[y]
                    array[y] = array[y + 1]
                    array[y + 1] = temp

                    # "swap" increases by one
                    swap += 1

                    # "update" becomes "True"
                    update =True

        # Return the array and number of times "swapped"
        return array, swap

```

## Examples: 1D-Arrays

### Example 1: Complete Code ( 1D-Array )

```python

# Bubble Sort

# Array with identifer name "array" with size = infinite
array = []

print()

# Exception Handling
try:

    # Asking the user to input the size of the array
    array_size = int(input("Please Enter Size Of Array: "))

# If user inputs a character other than an Integer
except ValueError:

    # Display appropriate message
    print()
    print("Please Enter Whole Numbers Only!")
    print()

print()

# Exception Handling
try:

    # Enter "for" loop in the range "array_size"
    for count in range(array_size):

        # Asking the user to enter a value
        user_input = int(input("Please Enter A Value: "))

        # Appending data that user entered into the array
        array.append(user_input)

# If user inputs a character other than an Integer
except ValueError:

    # Display appropriate message
    print()
    print("Please Enter Whole Numbers Only!")
    print()

# Displaying array BEFORE bubblesort
print()
print("Array Before Bubblesort: ")
print()

# Displaying arrays
for index in array:

    # Display values of array on separate lines
    print(index)

# Function with identifier name "bubblesort_optimised"

# In this function we need to pass:
# array
def bubblesort_optimised(array):

    # Variable "update" will check if swapping has occured
    update = True

    # Variable "swap" will hold the number of times
    # Algorithm has swapped a value
    swap = 0

    # Condition to enter "while" loop
    while update == True and len(array) > 1:

        # Immediately update becomes "False"
        # So that if value has been swapped, it will become "True"
        update = False

        # Number of time it will sort the array
        for x in range(0, len(array) - 1):

            # Checks every value in array
            for y in range(0, len(array) - 1):

                # Sorting in Ascending Order
                if array[y] > array[y +1]:

                    # Swapping Part
                    temp = array[y]
                    array[y] = array[y + 1]
                    array[y + 1] = temp

                    # "swap" increases by one
                    swap += 1

                    # "update" becomes "True"
                    update =True

        # Return the array and number of times "swapped"
        return array, swap

# Calling Function
result = bubblesort_optimised(array)

print(result)

```

>[!info]
>The keen eyes of your could have notice that the function name is:
>```python
>def bubbsort_optimised(array):
>...
>```
>Meaning there is a much more simpler way of writing the function
>
>I liked using the **un-optimised** one; but the optimised one is far better with only some 4 to 6 more lines of code

---

# Bubble Sort ( UN-OPTIMISED ) Code

>[!warning]
> I do not recommend using this one

## Template - Unoptimised

```python

# Binary Search Function ( UN-OPTIMISED )

# Function with identifer name "bubble_sort"

# In this function we need to pass:
# array
def bubble_sort(array):

    # Number of times it will sort the array
    for x in range(0, len(array) - 1):

        # Checks every value in array
        for y in range(0, len(array) - 1):

            # Sorting in Ascending Order
            if array[y] > array[y + 1]:

                # Swapping Part
                temp = array[y]
                array[y] = array[y + 1]
                array[y + 1] = temp

```

>[!note]
>To change the sorting **order** ( ascending / descending ). We just need to change the "$>$"  to "$<$" symbol in:
>```python
>if array[y] > array[y + 1]
>```
>- If we want sort in **ascending order**; we use "$>$"
> - If we want sort in **descending order**; we use "$<$"

---

# [[Arrays - Python#Two Dimensional Arrays ( 2D-Arrays ) | Two Dimensional Arrays]]

*Sorting* a **two** dimensional array means that we have to perform the sorting part **twice**.

# Bubble Sort Code - 2D Array

## Template - 2D Array

### Sorting **rows** of 2D-Array **only**

```python

# Bubble Sort Function - 2D Array

# Function with identifier name "bubblesort_optimised_2D"
# In this function we need to pas:
# array
def bubblesort_optimised_2D(array):

    # Variable "array_length" will take the length of array
    array_length = len(array)

    # Variable "update" will check if swapping has occured
    update = True

    # Variable "swap" will hold the number of times
    swap = 0

    # Condition to enter "while" loop
    while update == True and array_length > 1:

        # "update" immediately becomes "False"
        # So that if value has been swapped, it will become "True"
        update = False

        # Number of times it will sort the array
        for x in range(0, array_length - 1):

            # Checks every value in array
            for y in range(0, array_length - x - 1):

                # Sorting in Ascending Order
                if array[y][0] > array[y + 1][0]:

                    # Swapping Part
                    temp = array[y]
                    array[y] = array[y + 1]
                    array[y + 1] = temp

                    # "swap" increases by one
                    swap += 1

                    # "update" becomes "True"
                    update = False

```

### Sorting **rows** and **columns** of 2D-Array

```python

# Bubble Sort Function - 2D Array

# Function with identifier name "bubblesort_optimised_2D"
# In this function we need to pas:
# array
def bubblesort_optimised_2D(array):

    # Variable "array_length_rows" will take the length of rows
    array_length_rows = len(array)

    # Variable "array_length_col" will take the length columns
    array_length_cols = len(array[0])

  
    # Bubble Sort ROWS

  
    # Number of times it will sort the array
    for x in range(array_length_rows):

        # Checks every value in rows
        for y in range(0, array_length_cols - 1):

            # Will check every value
            for i in range(0, array_length_cols - y - 1):

                # Sorting in Ascending Order
                if array[x][i] > array[x][i + 1]:

                    # Swapping Part
                    temp = array[x][i]
                    array[x][i] = array[x][i + 1]
                    array[x][i + 1] = temp

    # "Transpose" the array
    # This means that we will make another array
    # to hold the new values for the rows

    transposed_array = [[array[y][x] for y in range(array_length_rows)] for x in range(array_length_cols)]

  
    # Bubble Sort COLUMNS

  
    # Number of times it will sort the array
    for x in range(array_length_cols):

        # Checks every value in rows
        for y in range(0, array_length_rows - 1):

            # Will check every value
            for i in range(0, array_length_rows - y - 1):

                if transposed_array[x][i] > transposed_array[x][i + 1]:

                    # Swapping Part
                    temp = transposed_array[x][i]
                    transposed_array[x][i] = transposed_array[x][i + 1]
                    transposed_array[x][i + 1] = temp

    # "Transpose" the array
    # In this part, we will take all the new values
    # and input it into the original array

    array[:] = [[transposed_array[y][x] for y in range(array_length_cols)] for x in range(array_length_rows)]

```

## Examples: 2D-Arrays

### Example 1: Complete Code ( 2D-Array )

```python

# Bubble Sort

# Array with identifier name "array" with infinite size
array = [

    [3, 6, 1],
    [8, 2, 4],
    [5, 7, 9],
    [2, 8, 5]

]

print()

# Displaying "array" before Sorting
for x in array:

    print(x)

print()

# Bubble Sort Function - 2D Array

# Function with identifier name "bubblesort_optimised_2D"
# In this function we need to pas:
# array
def bubblesort_optimised_2D(array):

    # Variable "array_length_rows" will take the length of rows
    array_length_rows = len(array)

    # Variable "array_length_col" will take the length columns
    array_length_cols = len(array[0])


    # Bubble Sort ROWS

  
    # Number of times it will sort the array
    for x in range(array_length_rows):

        # Checks every value in rows
        for y in range(0, array_length_cols - 1):

            # Will check every value
            for i in range(0, array_length_cols - y - 1):

                # Sorting in Ascending Order
                if array[x][i] > array[x][i + 1]:

                    # Swapping Part
                    temp = array[x][i]
                    array[x][i] = array[x][i + 1]
                    array[x][i + 1] = temp

    # "Transpose" the array
    # This means that we will make another array
    # to hold the new values for the rows

    transposed_array = [[array[y][x] for y in range(array_length_rows)] for x in range(array_length_cols)]

  
    # Bubble Sort COLUMNS

  
    # Number of times it will sort the array
    for x in range(array_length_cols):

        # Checks every value in rows
        for y in range(0, array_length_rows - 1):

            # Will check every value
            for i in range(0, array_length_rows - y - 1):

                if transposed_array[x][i] > transposed_array[x][i + 1]:

                    # Swapping Part
                    temp = transposed_array[x][i]
                    transposed_array[x][i] = transposed_array[x][i + 1]
                    transposed_array[x][i + 1] = temp

    # "Transpose" the array
    # In this part, we will take all the new values
    # and input it into the original array
    array[:] = [[transposed_array[y][x] for y in range(array_length_cols)] for x in range(array_length_rows)]

# Calling Function
bubblesort_optimised_2D(array)

# Displaying "array" after sorting
for x in array:

    print(x)

```

---

# Socials

- [**Instagram:**](https://www.instagram.com/s.sunhaloo/)
- [**YouTube:**](https://www.youtube.com/@s.sunhaloo539/streams)

---
Thank You!