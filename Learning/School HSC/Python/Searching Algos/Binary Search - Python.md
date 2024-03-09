---
Alias: Binary Search In Python
Tag: python, searching_algo, 1D-Array, 2D-Array
Author: S.Sunhaloo
Type: Searching Algorithm
Date: 2023-09-13
Status: Completed
---

## List of Contents:

- [[Binary Search - Python#What is Binary Search? | What is Binary Search?]]

## Binary Search

 ## [[Arrays - Python#One Dimensional Arrays ( 1D-Arrays ) | One Dimensional Arrays]]

- [[Binary Search - Python#Binary Search Code - 1D Array| Binary Search Code - 1D Array]]
	- [[Binary Search - Python#Template - 1D Array ( Non-Recursive )| Function Template ( Non-Recursive )]]
	- [[Binary Search - Python#Examples: 1D-Array ( Non-Recursive ) | Examples]]

## Binary Search Recursive

- [[Binary Search - Python#Binary Search Recursive Code - 1D Array| Binary Search Recursive Code]]
	- [[Binary Search - Python#Template - 1D Array ( Recursive )| Function Template ( Recursive )]]
	- [[Binary Search - Python#Examples:1D-Array ( Recursive ) | Examples]]
	- 

---

## [[Arrays - Python#Two Dimensional Arrays ( 2D-Arrays ) | Two Dimensional Arrays]]

- [[Binary Search - Python#Binary Search Code - 2D Array | Binary Search Code - 2D Array]]
	- [[Binary Search - Python#Template - 2D Array | Function Template]]

---

### My Links

- [[Binary Search - Python#Socials | Links to Socials]]

---

 # [[Arrays - Python#One Dimensional Arrays ( 1D-Arrays ) | One Dimensional Arrays]]

# What is Binary Search?

In simple terms it is just a [[Python HSC Data View#Searching Algorithms| searching algorithm]] that will **find** the required *data* in an **sorted** array.

The **calculation** part works like this:

1. It find the **middle** of the array
	- This is done by finding the **average** of the *length* of the array
2. If the middle value is the one that we are looking for;
	- We then output the **location** / **address** of the value
3. If the middle value is **less** than the search value
	- It will **increase** the *lower bound*
	- Thus, cutting half of the **lower** part of the array
4. If the middle value is **greater** than the search value
	- It will **decrease** the *upper bound*
	- Thus, cutting half of the **upper** part of the array

This means that **binary search** is really *efficient* and *fast*, as it always **cuts** the array in half each time the value is **not** found.

# Some Advantages

- Run time complexity if 0 ( $log N$ )
- Very fast and efficient for large data sets
	- As is cuts the array in half

# Some Disadvantages

- It is error prone
	- *Off-By-One Errors*
		- Occurs when determining the boundary of the next interval
- Caching is poor

> For more advantages and disadvantages; just [Google](https://google.com) them. The thing is that you need to know is:
> - Understand how it works
> - The actually program code

>[!warning]
>The array needs to be **SORTED** for it to work
>Never forget this.

# Binary Search Code - 1D Array

## Template - 1D Array ( Non-Recursive )

This is only the [[Functions and Procedures - Python#Example 5 Binary Search| function]], thus is will **not** run on its own.

```python

# Binary Search Function Non-Recursive 1D-Array

# We need to pass 2 arguments inside the function

# We need to pass the array - In this case our array is called "array"
# We need to pass our search value - In this case our array is called "user_find"
def binary_search(array, user_find):

    # Another function what will perform the calculations for the binary search
    
    # In this function we need to pass the:
    # array
    # Mininum size of array = 0
    # length of array - 1
    # search value ( user_find )
    return binary_search_calc(array, 0, len(array) - 1, user_find)
  
# Our function "binary_search_calc()" will perform the calculations

# In this function we need to pass some values for;
# array
# Minimum siz of array = 0 --> "lower" 
# length of array - 1 --> "upper"
# search value ( user_find )
def binary_search_calc(array, lower, upper, user_find):

    # Condition to enter loop ( need to learn theory to understand why )
    while lower <= upper:

        # Calculating our mid value
        mid = (lower + upper) // 2

        # If value at index "mid" is equal to search value ( user_find )
        if array[mid] == user_find:

            return mid

        # If value at index "mid" is lower than search value ( user_find )
        # If value is found in the upper part of array
        elif array[mid] < user_find:

            # "lower" takes the index to the right of mid
            # Remove the "lower" part of array
            lower = mid + 1
            
        # If value is found in the lower part of array 
        else:

            # "upper" takes the index to the left of mid
            # Remove the "upper" part of array
            upper = mid - 1
            
    # If "user_find" is not found
    return -1

```

## Examples: 1D-Array ( Non-Recursive )

### Example 1: Complete Code for 1D-Array

```python

# Binary Search Non-Recursive 1D-Array

print()

# Array with name "array" and values has already been added
array = [786, 23, 0, 25, 8, 17]

# Ask the user to input a value to find
user_find = int(input("Please Enter A Number To Find: "))

# We need to pass 2 arguments inside the function

# We need to pass the array - In this case our array is called "array"
# We need to pass our search value - In this case our array is called "user_find"
def binary_search(array, user_find):

    # Another function what will perform the calculations for the binary search
    
    # In this function we need to pass the;
    # array
    # Mininum size of array = 0
    # length of array - 1
    # search value ( user_find )
    return binary_search_calc(array, 0, len(array) - 1, user_find)

# Our function "binary_search_calc()" will perform the calculation

# In this function we need to pass some values for;
# array
# Minimum size of array = 0 --> "lower"
# length of array - 1 --> "upper"
# search value ( user_find )
def binary_search_calc(array, lower, upper, user_find):

    # Condition to enter loop ( need to learn theory to understand why )
    while lower <= upper:

        # Calculating our mid value
        mid = (lower + upper) //2

        # If value at index "mid" is equal to search value ( user_find )
        if array[mid] == user_find:

            return mid

        # If value at index "mid" is lower than search value ( user_find )
        elif array[mid] < user_find:

            # lower takes the index to the right of mid
            lower = mid + 1

        else:
  
            # upper takes the index to the left of mid
            upper = mid - 1  

    # If search value has not been found
    return -1

# "result" will take the "answer" from the function "binary_search()"
result = binary_search(array, user_find)

print()

# If the result was not equal to False
if result != -1:

    # Outputs this message
    print(str(user_find) + " has been found at " + str(result))

else:

    # If result was equal to True
    # Outputs this message
    print("Not Found")

print()

# Displaying values of array on separate lines
for i in array:

    print(i)

```

# Binary Search Recursive Code - 1D Array

## Template - 1D Array ( Recursive )

This is only the [[Functions and Procedures - Python | function]], thus is will **not** run on its own.

```python

# Recursive Binary Search Function 1D-Array

# We need to pass 2 arguments inside the function

# We need to pass the array - In this case our array is called "array"
# We need to pass our search value - In this case our array is called "user_find"
def binary_search_recursive(array, user_find):

    # Our function "binary_search_recursive_calc()" will perform the calculations
    
    # In this function we need to pass some values for;
    # array
    # Minimum size of array = 0
    # length of array - 1
    # search value ( user_find )
   return binary_search_recursive_calc(array, 0, len(array) -1, user_find)
   
# Our function "binary_search_recursive_calc()" will perform the calculation

# In this function we need to pass some values for;
# array
# Minimum size of array = 0 --> "lower"
# length of array - 1 --> "upper"
# search value ( user_find )
def binary_search_recursive_calc(array, lower, upper, user_find):

   # Checks if lower is not equal to size of array
   if lower > upper:
   
      # If lower > upper ==> values has NOT been found
      return False

   # Calculating our mid value
   mid = (lower + upper) //2

   # If value at index "mid" is equal to search value ( user_find )
   if array[mid] == user_find:

      return mid

   # If value at index "mid" is greater than search value ( user_find )
   elif array[mid] > user_find:

      # Similar to upper = mid - 1 ( Check "normal" binary search )
      return binary_search_recursive_calc(array, lower, mid - 1, user_find)

   else:

      # Similar to lower = mid + 1 ( Check "normal" binary search )
      return binary_search_recursive_calc(array, mid + 1, upper, user_find)


```

## Examples: 1D-Array ( Recursive )

### Example 1: Complete Code 1D-Array

```python

# Recursive Binary Search 1D-Array

print()

# Array with name "array" and values has already been added
array = [786, 23, 0, 25, 8, 17]

# Ask the user to input a value to find
user_find = int(input("Please Enter A Number To Find: "))

# We need to pass 2 arguments inside the function
# We need to pass the array - In this case our array is called "array"
# We need to pass our search value - In this case our array is called "user_find"
def binary_search_recursive(array, user_find):

    # Our function "binary_search_recursive_calc()" will perform the calculations
    # In this function we need to pass some values for;
    # array
    # Minimum size of array = 0
    # length of array - 1
    # search value ( user_find )
   return binary_search_recursive_calc(array, 0, len(array) -1, user_find)

# Our function "binary_search_recursive_calc()" will perform the calculation

# In this function we need to pass some values for;
# array
# Minimum size of array = 0 --> "lower"
# length of array - 1 --> "upper"
# search value ( user_find )
def binary_search_recursive_calc(array, lower, upper, user_find):

   # Checks if lower is not equal to size of array
   if lower > upper:
   
      # If lower > upper ==> values has NOT been found
      # If you are going to use the "if result != ..." code
      # We need to return -1 instead of False
      # This is due to reserved words in Python
      return -1

   # Calculating our mid value
   mid = (lower + upper) //2

   # If value at index "mid" is equal to search value ( user_find )
   if array[mid] == user_find:

      return mid

   # If value at index "mid" is greater than search value ( user_find )
   elif array[mid] > user_find:

      # Similar to upper = mid - 1 ( Check "normal" binary search )
      return binary_search_recursive_calc(array, lower, mid -1, user_find)

   else:

      # Similar to lower = mid + 1 ( Check "normal" binary search )
      return binary_search_recursive_calc(array, mid + 1, upper, user_find)

# "result" will take the "answer" from the function "binary_search()"
result = binary_search_recursive(array, user_find)

print()

# If the result was not equal to False
if result != False:

  # Outputs this message
  print(str(user_find) + " has been found at " + str(result))

else:

  # If result was equal to True
  # Outputs this message
  print("Not Found")

print()

# Displaying values of array on separate lines
for i in array:

    print(i)

```

# [[Arrays - Python#Two Dimensional Arrays ( 2D-Arrays ) | Two Dimensional Arrays]]

# Binary Search Code - 2D Array

## Template - 2D Array

This is only the [[Functions and Procedures - Python#Example 5 Binary Search| function]], thus is will **not** run on its own.

```python

# Function with identifier name "binary_search"

# In this function we are passing our
# array --> In this case "matrix"
# value to be searched --> In this case "user_input"
def binary_search(matrix, user_input):

    # DECLARE rows: OF INTEGER
    # Variable "rows" will keep the number of rows
    rows = len(matrix)

    # DECLARE cols: OF INTEGER
    # Variable "cols" will keep the number of cols in a single row
    # "finds the length of the first row"
    cols = len(matrix[0])

    # DECLARE left: OF INTEGER
    left = 0

    # DECLARE right: OF INTEGER
    # Variable "right" will keep the "overall / linear" length of array
    right = rows * cols -1

    # Condition to enter "while" loop
    while left <= right:

        # DECLARE mid: OF INTEGER
        # Calculating the middle value of 2D-Array
        mid = (left + right) // 2

        # DECLARE mid_value: OF INTEGER
        # NOTE: "%" means MODULUS
        # This is used to convert a "flat index" back into 2D Array index
            # => 1D --> 2D
        mid_value = matrix[mid // cols][mid % cols]

        # If value at index "mid" is equal to search value
        if mid_value == user_input:

            # Returns the address of "search_value"
            return (mid // cols, mid % cols)

        # If value at index "mid_value" is less than search value
        elif mid_value < user_input:

            # "left" takes the index to the right of mid
            # Remove the lower part of array
            left = mid + 1

        else:

            # "right" takes the index to the left of mid
            # Remove the upper part of array
            right = mid - 1

    # If value has not been found
    return -1

```

## Examples: 2D-Array

### Example: Complete Code 2D-Array

```python

# Binary Search Function 2D-Array

# DECLARE array: ARRAY OF INTEGER
array = [

    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]

]

print()

# Exception Handling
try:

    # Asking the user to enter a value to search
    user_input = int(input("Please Enter A Value To Search: "))

# If user enter any other data types other than "integer"
except ValueError:

    # Outputs appropriate message
    print()
    print("Please Enter Integer Values Only")
    print()

# Function with identifier name "binary_search"

# In this function we are passing our
# array --> In this case "matrix"
# value to be searched --> In this case "user_input"
def binary_search(matrix, user_input):

    # DECLARE rows: OF INTEGER
    # Variable "rows" will keep the number of rows
    rows = len(matrix)

    # DECLARE cols: OF INTEGER
    # Variable "cols" will keep the number of cols in a single row
    # "finds the length of the first row"
    cols = len(matrix[0])

    # DECLARE left: OF INTEGER
    left = 0

    # DECLARE right: OF INTEGER
    # Variable "right" will keep the "overall / linear" length of array
    right = rows * cols -1

    # Condition to enter "while" loop
    while left <= right:

        # DECLARE mid: OF INTEGER
        # Calculating the middle value of 2D-Array
        mid = (left + right) // 2

        # DECLARE mid_value: OF INTEGER
        # NOTE: "%" means MODULUS
        # This is used to convert a "flat index" back into 2D Array index
            # => 1D --> 2D
        mid_value = matrix[mid // cols][mid % cols]

        # If value at index "mid" is equal to search value
        if mid_value == user_input:

            # Returns the address of "search_value"
            return (mid // cols, mid % cols)

        # If value at index "mid_value" is less than search value
        elif mid_value < user_input:

            # "left" takes the index to the right of mid
            # Remove the lower part of array
            left = mid + 1

        else:

            # "right" takes the index to the left of mid
            # Remove the upper part of array
            right = mid - 1

    # If value has not been found
    return -1

# Calling Function
result = binary_search(array, user_input)

print()

# Displaying the "results"
if result != -1:

    # If value to search has been found
    print(f"{user_input} Has Been Found At: {result}")

else:

    # If value to search has NOT been found
    print(f"{user_input} Has Not Been Found")

```

---

# Socials

- [**Instagram:**](https://www.instagram.com/s.sunhaloo/)
- [**YouTube:**](https://www.youtube.com/@s.sunhaloo539/streams)

---
Thank You!