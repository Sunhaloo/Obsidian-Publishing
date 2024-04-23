---
Alias: Stack ADT ( Cambridge Requirements )
Tag: python, basics, 1D-Array
Author: S.Sunhaloo
Type: ADT
Date: 2023-10-26
Status: Completed
---

## List of Contents

- [[Stack ADT - 1D Array ( Cambridge )#What is a Stack?| What is a Stack?]]
- [[Stack ADT - 1D Array ( Cambridge )#Operations of Stack ADT| Operations of Stack ADT]]
	- [[Stack ADT - 1D Array ( Cambridge )#Push Operation| Push Operation]]
	- [[Stack ADT - 1D Array ( Cambridge )#Pop Operation| Pop Operation]]
- [[Stack ADT - 1D Array ( Cambridge )#Pointer| Pointer]]
- [[Stack ADT - 1D Array ( Cambridge )#Photo| How it works ( Photo )]]
- [[Stack ADT - 1D Array ( Cambridge )#Stack Program Code| Stack Program Code]]
	- [[Stack ADT - 1D Array ( Cambridge )#Functions| Functions]]
		- [[Stack ADT - 1D Array ( Cambridge )#Initialising our Stack | Initialising our Stack]]
		- [[Stack ADT - 1D Array ( Cambridge )#Displaying Array | Displaying Array]]
		- [[Stack ADT - 1D Array ( Cambridge )#Inserting Values | Inserting Values]]
		- [[Stack ADT - 1D Array ( Cambridge )#Pop Function | Pop Function]]
		- [[Stack ADT - 1D Array ( Cambridge )#Delete Specific Element | Deleting Specific Element]]
			- [[Stack ADT - 1D Array ( Cambridge )#With **FOR Loop** | FOR Loop]]
			- [[Stack ADT - 1D Array ( Cambridge )#With **WHILE Loop** | WHILE Loop]]
		- [[Stack ADT - 1D Array ( Cambridge )#Bubble Sort | Bubble Sort]]
		- [[Stack ADT - 1D Array ( Cambridge )#Insertion Sort | Insertion Sort]]
		- [[Stack ADT - 1D Array ( Cambridge )#Linear Search | Linear Search]]
			- [[Stack ADT - 1D Array ( Cambridge )#Displaying the "*result*" of Linear Search | Displaying Result of Linear Search]]
		- [[Stack ADT - 1D Array ( Cambridge )#Binary Search | Binary Search]]
			- [[Stack ADT - 1D Array ( Cambridge )#Displaying the "*result*" of Binary Search | Displaying Result of Binary Search]]

---

- [[Stack ADT - 1D Array ( Cambridge )#Stack Program Code Example | Example]]
	- [[Stack ADT - 1D Array ( Cambridge )#Full Stack Code ( Template ) | Template]]

---

My Links

- [[Stack ADT - 1D Array ( Cambridge )#Socials | Links to Socials]]

---

# What is a Stack?

It forms part of the [[Python Data View#Abstract Data Types| abstract data types ]] family. It is a collection of elements with **2** main *operations* and **1** *pointer*.

It is a **LIFO** data structure. What does "*LIFO*" stands for you ask; well it stands for:

$$Last \ In \ First \ Out$$

## Operations of Stack ADT

1. **PUSH** Operation
	- To **add** elements inside the stack / array
2. **POP** Operation
	- To **remove** elements Inside the stack / array

Think of the **Stack Data Structure** as a *stack of plates*.

### Push Operation

This means that we want to add "*plates*" to our stack. We will place it at the bottom.

- If one will want to add another plate, he will add it on top of the other one.

This means that the *last item* will always be at the **top**.

### Pop Operation

Continuing will our shit explanation from above; if we want to access the **first** plate, then we would need to:

- Remove all other plates in the "*stack*".

That is why is called a **LIFO** structure $\rightarrow$ **LAST IN FIRST OUT**

## Pointer

This [[Python Data View#Abstract Data Types| abstract data types ]] has only **1** pointer, which points to the **last item** in the array

---

# Photo

This is an example of **Stack Data Structure** photo

![[Stack ADT Explanation.png]]

---

# Stack Program Code

I will not write the **full code** for now, I will only write the [[Functions and Procedures - Python|functions]] that make up the *data structure* . This way, it will be easier to learn and understand the code as they are separate.

## Functions

## Initialising our Stack

>[!warning]
>The array will start at **index** *0*.
>>[!tip] Starting at **1**
>>If you want to the array at **index** *1*;
>>- You will have to define **top** like this:
>>```python
>>top = 0
>>```

To create our stack, we need to *initialise* an **array** and a *global* **pointer**.

>[!note]
>In this case ( "*as per Cambridge's Requirements*" ), the array is already filled with values


```python

# Stack Program Code

# DECLARE top: OF INTEGER
# Global pointer "top" will keep track of the last item added
global top

# DECLARE base: OF INTEGER
# Global pointer "base" will be used to check if array is empty
global base

# DECLARE stack: ARRAY[4] OF INTEGER
# Our 1D-Array with identifier name "stack"
stack = [9, 22, 4]

```

## Displaying Array

This will be the function what will be used to **display** the contents of the array.

```python

# Stack Program Code

# FUNCTION display_array RETURNS INTEGER
# Function "display_array" which will display our "stack"
def display_array():

    # DECLARE x: OF INTEGER
    # Variable "x" is a counter that will be used to display our values in "stack"

    # If array is EMPTY
    if not stack:

        # Pointer "top" become "-1"
        top = -1

        # Ponter "base" becomes 0
        base = 0

        # Displays appropriate message
        print()
        print("Array is EMPTY")

        # Displaying pointer top "location"        
        print()
        print(f"Top Pointer ---> {top}")
        print(f"Base Pointer ---> {base}")
        print()

    # IF array is NOT empty
    else:

        # Pointer "top" becomes
        top = len(stack) -1

        # Pointer "base" stays 0
        base = 0

        print()
        print("Displaying Array")

        # Displaying array "stack" ( values on separate lines )
        for x in stack:

            print(x)

        # Diplaying pointer's "location"
        print()
        print(f"Top Pointer ---> {top}")
        print(f"Base Pointer ---> {base}")
        print()

```

## Inserting Values

This function will allow us insert values into the array.

```python

# Stack Program Code

# FUNCTION insert_value(BYVAL input_item: OF INTEGER)
# Function with identifier name "insert_value" will allow us to insert elements in array
def push(input_item):

    # DECLARE array_length: OF INTEGER
    # Variable "array_length" will hold the length of array
        # NOTE: Do not use "len(array)"; programmer need to write the length of array
    array_length = 5

    # Pointer "top" will hold the index of last item in array "stack"
    top = len(stack) -1

    # Check if array is full
    if top == array_length -1:

        # Outputs appropriate message
        print()
        print("Array is FULL!")
        print()

    # If array "stack" is NOT full
    elif top < array_length -1:

        # Pointer "top" increases by 1
        top += 1

        # "Appends" the item to the "stack"
        stack.append(input_item)

```

## Pop Function

As you know, the *pop* function is used to remove values from an array; in this case, we will be using it to remove the last item ( "*added*" ) into the **stack**.

### Method 1: Standard Method

```python

# Stack Program Code

# FUNCTION pop_value()
# Function "pop_value()" will remove the last value ( added ) from "stack"
def pop_value():

    # Pointer "top" will keep of index of last item in "stack"
    top = len(stack) -1

    # Pointer "base" will keep track of the "lower bound" of array
    base = 0

    # Check if "stack" is already EMPTY
    if top == base - 1:

        # Outputs appropriate message
        print()
        print("Array is already EMPTY!")
        print()

    # If array is NOT emtpy
    else:

        # Pointer "top" decreases by 1
        top -= 1

        # Removes the last value ( added ) from "stack"
        stack.pop()

```

### Method 2: My Method

```python

# Stack Program Code

# FUNCTION pop_values_mine
# Function "pop_value_mine" will remove the last value ( added )
def pop_value_mine():

    # Pointer "top" will keep of index of last item in "stack"
    top = len(stack) -1

    # Pointer "base" will keep track of the "lower bound" of array
    base = 0

    # Check if array is NOT empty
        # Thus, if array is not empty, we can remove values
    if top >= 0:

        # top decreases
        top -= 1

        # removes value
        stack.pop()

    # If array "stack" is EMPTY
    elif top == base -1:

        # Output appropriate values
        print()
        print("Array is already EMPTY!")
        print()

```

## Delete Specific Element

The user will be able to choose what number he wants to delete from the *stack*.

### With **FOR Loop**

```python

# Stack Program Code

# FUNCTION specific_delete(BYVAL delete_item)
# Function "specific_delete" will remove a specific value from "stack"
def specific_delete(delete_item):

    # DECLARE x: OF INTEGER
    # DECLARE found: OF BOOLEAN
    # Variable "found" will become "True" is value to be removed has been found
    found = False

    # DECLARE array_length: OF INTEGER
    # Variable "array_length" will hold the length of "stack"
    array_length = len(stack)

    # Pointer "top" will keep track of the last value ( added )
    top = len(stack) -1

    # Pointer "base" will keep track of the "lower bound" of array
    base = 0

    # Check if array "stack" is alredy EMPTY
    if top == base -1:

        # Outputs appropriate message
        print()
        print("Array is already EMPTY")
        print()

    # If array "stack" is NOT Emtpy
    else:

        # Steps through the array "stack"
        for x in range(array_length):

            # If value has been found
            if stack[x] == delete_item:

                # Variable "found" becomes "True"
                found = True

                # Removes value from "stack"
                stack.remove(stack[x])

                # Pointer "top" decreases by 1
                top -= 1

                # Exits "FOR" Loop
                break

        # If value has NOT been found
        if not found:

            # Outputs appropriate message
            print()
            print(f"{delete_item} has NOT been found")
            print()

```

### With **WHILE Loop**

I do not like the while loop so I will be linking this to  *Stack ADT -1D Array ( MIne )* ![[Stack ADT - 1D Array ( Mine )#With **While Loop** | Stack 1D-Array ( Mine )]].

## Bubble Sort

What can I say, it will sort the array; but *remember*, we need to sort the array in **Ascending Order** for [[Stack ADT - 1D Array ( Cambridge )#Binary Search | binary search]] to work.

```python

# Stack Program Code

# FUNCTION bubble_sort()
# Function "bubble_sort" will sort the array in ASCENDING ORDER
    # Ascending Order; because Binary Search will need the array to be in ASC Order
def bubble_sort():

    # DECLARE temp: OF INTEGEr
    # Variable "temp" will store our values being swapped

    # DECLARE swaps: OF INTEGER
    # Variable "swaps" will count how many times values have been swapped
    swaps = 0

    # DECLARE update: OF BOOLEAN
    # Variable "update" will become "True" when values have been swapped
    update = True

    # DECLARE array_length: OF INTEGER
    # Variable "array_length" will hold the length of array
    array_length = len(stack)

    # Condition to enter "WHILE" Loop
    while update == True and array_length > 0:

        # Variable "update" will become False
            # So that I can become true later
        update = False

        # Number of times if will perform "bubble sort"
        for x in range(0, array_length -1):

            #  Number of time it will swap value
            for y in range(0, array_length -1):

                # Sorting in Ascending Order
                if stack[y] > stack[y + 1]:

                    # Swapping Part
                    temp = stack[y]
                    stack[y] = stack[y + 1]
                    stack[y + 1] = temp

                    # Variable "update" becomes "True"
                    update = True

                    # Variable "swaps" increases by 1
                    swaps += 1

```

## Insertion Sort

Similar to [[Stack ADT - 1D Array ( Cambridge )#Bubble Sort | bubble sort]]; it will sort the array for us. Again, we need to sort in **Ascending Order**

```python

# Stack Program Code

# FUNCTION insertion_sort()
# Function "insertion_sort" will sort our array in ASCENDING ORDER
    # Ascending Order; because Binary Search will need the array to be in ASC Order
def insertion_sort():

    # DECLARE x: OF INTEGER

    # DECLARE array_length: OF INTEGER
    # Variable array_length will keep track of length of array
    array_length = len(stack)

    # Stepping through array
    for x in range(1, array_length):

        # DECLARE values: OF INTEGER
        # Variable "values" will hold the values at index "x"
        values = stack[x]

        # DECLARE y: OF INTEGER
        # Variable "y" will keep the index next to "x"
        y = x -1

        # Condition to enter "WHILE" loop
        while y >= 0 and stack[y] > values:

            # Swapping Part
            stack[y + 1] = stack[y]

            # Variable "y" decreases by 1
            y -= 1

        # If "stack" is already sorted
        stack[y + 1] = values

```

## Linear Search

Performs simple [[Linear Search - Python | linear search]] function. Allows the user to find the *address* of a value

```python

# Stack Program Code

# FUNCTION linear_search(BYVAL search_item: OF INTEGER):
# Function "linear_search" will allow us to search a value in the array
def linear_search(search_item):

    # DECLARE array_length: OF INTEGER
    # Variable "array_length" will hold the length of "stack"
    array_length = len(stack)    

    # Stepping through "stack"
        # Searching for "search_item"
    for x in range(0, array_length):

        # If "search_item" has been found
        if stack[x] == search_item:

            # Returns the address of "search_item"
            return x

    # If "search_item" has not been found
    return -1

```

### Displaying the "*result*" of Linear Search

By itself, the [[Stack ADT - 1D Array ( Cambridge )#Linear Search | linear search]] function is *useless*. Hence we need this bit of code below ( $\downarrow$ ).

```python

# Stack Program Code

# Linear Search
result_linear = linear_search(22)

# FUNCTION display_linear(BYVAL result_linear: OF INTEGER)
# Function "display_linear" will display the result of function "linear_search"
def display_linear(result_linear):

    # If "search_item" has been found
    if result_linear != -1:

        # Outputs the appropriate =message
        print()
        print(f"Value is found at address: {result_linear}")
        print()

    # If "search_item" has NOT been found
    else:

        # Outputs the appropriate =message
        print()
        print("Value has NOT been found")
        print()

# Calling the function "display_linear"
display_linear(result_linear)

```

## Binary Search

Will allow the user to find the *address* of a value.

>[!note]
>To be able to use **binary search**, we need to first **sort** the array / stack in *Ascending Order*

```python

# Stack Program Code

# FUNCTION binary_search(BYVAL search_item: OF INTEGER):
# Function "binary_search" will allow us to search a value in the array
    # NOTE: We need to sort our array in ASCENDING ORDER for "binary_search" to work
def binary_search(search_item):

    # FUNCTION binary_search_calc(BYVAL stack, BYVAL 0, BYVAL LENGTH(stack) - 1, BYVAL search_item )
    # Function "binary_search_calc" will be the one to perform the calculation
    return binary_search_calc(stack, 0, len(stack) - 1, search_item)

# FUNCTION binary_search_calc(BYVAL stack, BYVAL 0, BYVAL LENGTH(stack) - 1, BYVAL search_item )
# Function "binary_search_calc" will be the one to perform the calculation
def binary_search_calc(stack, lower, upper, search_item):

    # Condition to enter "WHILE" Loop
    while lower <= upper:

        # DECLARE mid: OF INTEGER
        # Variable "mid" will find the middle of "stack"
        mid = (lower + upper) // 2

        # Finding the value

        # If value is found found in the middle
        if stack[mid] == search_item:

            # Returns the address of "search_item"
            return mid

        # If value at mid-pt is < search value
        elif stack[mid] < lower:

            # Discards the bottom part of array
            lower = mid + 1

        # If value at mid-pt is > search value
        else:

            # Discards the upper part of array
            upper = mid -1

```

### Displaying the "*result*" of Binary Search

By itself, the [[Stack ADT - 1D Array ( Cambridge )#Binary Search | binary search]] function is *useless*. Hence we need this bit of code below ( $\downarrow$ ).

```python

# Stack Program Code

# Binary Search
result_binary = binary_search(9)

# FUNCTION display_binary(BYVAL result_binary: OF INTEGER)
# Function "display_binary" will display the result of function "binary_search"
def display_binary(result_binary):

    # If "search_item" has been found
    if result_binary != -1:

        # Outputs the appropriate message
        print()
        print(f"Value is found at address: {result_binary}")
        print()

    # If "search_item" has NOT been found
    else:

        # Outputs the appropriate message
        print()
        print("Value has NOT been found")
        print()

# Calling the function "display_binary"
display_binary(result_binary)

```

# Stack Program Code Example

Hence, we get an Stack Abstract Data Type as per*Cambridge*'s requirements

## Full Stack Code ( Template )

```python

# Stack Program Code

# DECLARE top: OF INTEGER
# Global pointer "top" will keep track of the last item added
global top

# DECLARE base: OF INTEGER
# Global pointer "base" will be used to check if array is empty
global base

# DECLARE stack: ARRAY[4] OF INTEGER
# Our 1D-Array with identifier name "stack"
stack = [9, 22, 4]

# Functions

# FUNCTION display_array RETURNS INTEGER
# Function "display_array" which will display our "stack"
def display_array():

    # DECLARE x: OF INTEGER
    # Variable "x" is a counter what will be used to display our values in "stack"

    # If array is EMPTY
    if not stack:

        # Pointer "top" become "-1"
        top = -1

        # Ponter "base" becomes 0
        base = 0

        # Displays appropriate message
        print()
        print("Array is EMPTY")

        # Displaying pointer top "location"        
        print()
        print(f"Top Pointer ---> {top}")
        print(f"Base Pointer ---> {base}")
        print()

    # If array is NOT empty
    else:

        # Pointer "top" becomes
        top = len(stack) -1

        # Pointer "base" stays 0
        base = 0

        print()
        print("Displaying Array")

        # Displaying array "stack" ( values on separate lines )
        for x in stack:

            print(x)

        # Diplaying pointer top "location"
        print()
        print(f"Top Pointer ---> {top}")
        print(f"Base Pointer ---> {base}")
        print()

# FUNCTION push_mine(BYVAL input_item: OF INTEGER)
# Function "push_mine" will allow us to insert elements in array
def push_mine(input_item):

    # DECLARE array_length: OF INTEGER
    # Variable "array_length" will hold the length of array
        # NOTE: Do not use "len(array)"; programmer need to write the length of array
    array_length = 5

    # Pointer "top" will hold the index of last item in array "stack"
    top = len(stack) -1

    # Temporary Holder for top
    top_1 = top + 1

    # Check if array is full
    if (top_1) == array_length:

        # Outputs appropriate message
        print()
        print("Array is FULL!")
        print()

    # If array "stack" in NOT full
    elif (top_1) < array_length:

        # Pointer "top" increases by 1
        top_1 += 1

        # "Appends" the item to the "stack"
        stack.append(input_item)

# The function "push_value" below is a better version of the above function "insert_value_top"

# FUNCTION push_value(BYVAL input_item: OF INTEGER)
# Function with identifier name "push_mine" will allow us to insert elements in array
def push_value(input_item):

    # DECLARE array_length: OF INTEGER
    # Constant "array_length" will hold the length of array
        # NOTE: Do not use "len(array)"; programmer need to write the length of array
    array_length = 5

    # Pointer "top" will hold the index of last item in array "stack"
    top = len(stack) -1

    # Check if array is full
    if top == array_length -1:

        # Outputs appropriate message
        print()
        print("Array is FULL!")
        print()

    # If array "stack" is NOT full
    elif top < array_length -1:

        # Pointer "top" increases by 1
        top += 1

        # "Appends" the item to the "stack"
        stack.append(input_item)

# FUNCTION pop_value()
# Function "pop_value()" will remove the last value ( added ) from "stack"
def pop_value():

    # Pointer "top" will keep of index of last item in "stack"
    top = len(stack) -1

    # Pointer "base" will keep track of the "lower bound" of array
    base = 0

    # Check if "stack" is already EMPTY
    if top == base - 1:

        # Outputs appropriate message
        print()
        print("Array is already EMPTY!")
        print()

    # If array is NOT emtpy
    else:

        # Pointer "top" decreases by 1
        top -= 1

        # Removes the last value ( added ) from "stack"
        stack.pop()

# FUNCTION pop_value_mine
# Function "pop_value_mine" will remove the last value ( added )
def pop_value_mine():

    # Pointer "top" will keep of index of last item in "stack"
    top = len(stack) -1

    # Pointer "base" will keep track of the "lower bound" of array
    base = 0

    # Check if array is NOT empty
        # Thus, if array is not empty, we can remove values
    if top >= 0:

        # top decreases
        top -= 1

        # removes value
        stack.pop()

    # If array "stack" is EMPTY
    elif top == base -1:

        # Output appropriate values
        print()
        print("Array is already EMPTY!")
        print()

# FUNCTION specific_delete(BYVAL delete_item)
# Function "specific_delete" will remove a specific value from "stack"
def specific_delete(delete_item):

    # DECLARE x: OF INTEGER

    # DECLARE found: OF BOOLEAN
    # Variable "found" will become "True" is value to be removed has been found
    found = False

    # DECLARE array_length: OF INTEGER
    # Constant "array_length" will hold the length of "stack"
    array_length = len(stack)

    # Pointer "top" will keep track of the last value ( added )
    top = len(stack) -1

    # Pointer "base" will keep track of the "lower bound" of array
    base = 0

    # Check if array "stack" is alredy EMPTY
    if top == base -1:

        # Outputs appropriate message
        print()
        print("Array is already EMPTY")
        print()

    # If array "stack" is NOT Emtpy
    else:

        # Steps through the array "stack"
        for x in range(array_length):

            # If value has been found
            if stack[x] == delete_item:

                # Variable "found" becomes "True"
                found = True

                # Removes value from "stack"
                stack.remove(stack[x])

                # Pointer "top" decreases by 1
                top -= 1

                # Exits "FOR" Loop
                break

        # If value has NOT been found
        if not found:

            # Outputs appropriate message
            print()
            print(f"{delete_item} has NOT been found")
            print()

# FUNCTION bubble_sort()
# Function "bubble_sort" will sort the array in ASCENDING ORDER
    # Ascending Order; because Binary Search will need the array to be in ASC Order
def bubble_sort():

    # DECLARE temp: OF INTEGEr
    # Variable "temp" will store our values being swapped

    # DECLARE swaps: OF INTEGER
    # Variable "swaps" will count how many times values have been swapped
    swaps = 0

    # DECLARE update: OF BOOLEAN
    # Variable "update" will become "True" when values have been swapped
    update = True

    # DECLARE array_length: OF INTEGER
    # Constant "array_length" will hold the length of array
    array_length = len(stack)

    # Condition to enter "WHILE" Loop
    while update == True and array_length > 0:

        # Variable "update" will become False
            # So that I can become true later
        update = False

        # Number of times if will perform "bubble sort"
        for x in range(0, array_length -1):

            #  Number of time it will swap value
            for y in range(0, array_length -1):

                # Sorting in Ascending Order
                if stack[y] > stack[y + 1]:

                    # Swapping Part
                    temp = stack[y]
                    stack[y] = stack[y + 1]
                    stack[y + 1] = temp

                    # Variable "update" becomes "True"
                    update = True

                    # Variable "swaps" increases by 1
                    swaps += 1

# FUNCTION insertion_sort()
# Function "insertion_sort" will sort our array in ASCENDING ORDER
    # Ascending Order; because Binary Search will need the array to be in ASC Order
def insertion_sort():

    # DECLARE x: OF INTEGER

    # DECLARE array_length: OF INTEGER
    # Constant array_length will keep track of length of array
    array_length = len(stack)

    # Stepping through array
    for x in range(1, array_length):

        # DECLARE values: OF INTEGER
        # Variable "values" will hold the values at index "x"
        values = stack[x]

        # DECLARE y: OF INTEGER
        # Variable "y" will keep the index next to "x"
        y = x -1

        # Condition to enter "WHILE" loop
        while y >= 0 and stack[y] > values:

            # Swapping Part
            stack[y + 1] = stack[y]

            # Variable "y" decreases by 1
            y -= 1

        # If "stack" is already sorted
        stack[y + 1] = values

# FUNCTION linear_search(BYVAL search_item: OF INTEGER):
# Function "linear_search" will allow us to search a value in the array
def linear_search(search_item):

    # DECLARE array_length: OF INTEGER

    # Constant "array_length" will hold the length of "stack"
    array_length = len(stack)    

    # Stepping through "stack"
        # Searching for "searzh_item"
    for x in range(0, array_length):

        # If "search_item" has been found
        if stack[x] == search_item:

            # Returns the address of "search_item"
            return x

    # If "search_item" has not been found
    return -1

# FUNCTION binary_search(BYVAL search_item: OF INTEGER):
# Function "binary_search" will allow us to search a value in the array
    # NOTE: We need to sort our array in ASCENDING ORDER for "binary_search" to work
def binary_search(search_item):

    # FUNCTION binary_search_calc(BYVAL stack, BYVAL 0, BYVAL LENGTH(stack) - 1, BYVAL search_item )
    # Function "binary_search_calc" will be the one to perform the calculation
    return binary_search_calc(stack, 0, len(stack) - 1, search_item)

# FUNCTION binary_search_calc(BYVAL stack, BYVAL 0, BYVAL LENGTH(stack) - 1, BYVAL search_item )
# Function "binary_search_calc" will be the one to perform the calculation
def binary_search_calc(stack, lower, upper, search_item):

    # Condition to enter "WHILE" Loop
    while lower <= upper:

        # DECLARE mid: OF INTEGER
        # Variable "mid" will find the middle of "stack"
        mid = (lower + upper) // 2

        # Finding the value
        # If value is found found in the middle
        if stack[mid] == search_item:

            # Returns the address of "search_item"
            return mid

        # If value at mid-pt is < search value
        elif stack[mid] < lower:

            # Discards the bottom part of array
            lower = mid + 1

        # If value at mid-pt is > search value
        else:

            # Discards the upper part of array
            upper = mid -1

# Calling Functions
print()
print("Displaying Initial Array")
display_array()

# Inserting Values
print()
print("Inserting Values")
print()

# Inserting values individually
push_value(3)
push_value(5)
# This will not be added to array "stack"
push_value(90)

print()
print("Displaying Array After Inserting Value")
display_array()

# "Popping Values"
print()
print("Removing Last Values ( Twice )")

# Both of these function below will remove the last value ( added ) into array
pop_value_mine()
pop_value()

print()
print("Displaying Array After Removing 2 Values")
display_array()

print()
print("Deleting -1")
# Trys to delete "-1"
    # Which is obviously going to return "-1" ---> Not Found
specific_delete(-1)

print()
print("Sorting Array")

# Sorts the "stack" in Ascending Order
bubble_sort()

# "Un-Comment" "insertion_sort()" to use insertion sort
#insertion_sort()

print()
print("Displaying Array After Sorting In Ascending Order")
display_array()

# Linear Search
result_linear = linear_search(22)

# FUNCTION display_linear(BYVAL result_linear: OF INTEGER)
# Function "display_linear" will display the result of function "linear_search"
def display_linear(result_linear):

    # If "search_item" has been found
    if result_linear != -1:

        # Outputs the appropriate =message
        print()
        print(f"Value is found at address: {result_linear}")
        print()

    # If "search_item" has NOT been found
    else:

        # Outputs the appropriate =message
        print()
        print("Value has NOT been found")
        print()

# Calling the function "display_linear"
display_linear(result_linear)

# Binary Search
result_binary = binary_search(9)

# FUNCTION display_binary(BYVAL result_binary: OF INTEGER)
# Function "display_binary" will display the result of function "binary_search"
def display_binary(result_binary):

    # If "search_item" has been found
    if result_binary != -1:

        # Outputs the appropriate message
        print()
        print(f"Value is found at address: {result_binary}")
        print()

    # If "search_item" has NOT been found
    else:

        # Outputs the appropriate message
        print()
        print("Value has NOT been found")
        print()

# Calling the function "display_binary"
display_binary(result_binary)

```

>[!info]
>The function "**insertion_sort()**" is not used in this code, though we could remove "*#*" to be able to **use** it.

---

# Socials

- [**GitHub**](https://www.github.com/Sunhaloo)
- [**Instagram**](https://www.instagram.com/s.sunhaloo/)
- [**YouTube**](https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg)

---

S.Sunhaloo
Thank You!