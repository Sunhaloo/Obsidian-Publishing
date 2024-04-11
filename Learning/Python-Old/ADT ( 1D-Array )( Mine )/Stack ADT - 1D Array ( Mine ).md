---
Alias: Stack LIFO
Tag: python, ADT, 1D-Array
Author: S.Sunhaloo
Type: ADT
Date: 2023-08-27
Status: Completed
---

## List of Contents

- [[Stack ADT - 1D Array ( Mine )#What is a Stack?| What is a Stack?]]
- [[Stack ADT - 1D Array ( Mine )#Operations of Stack ADT| Operations of Stack ADT]]
	- [[Stack ADT - 1D Array ( Mine )#Push Operation| Push Operation]]
	- [[Stack ADT - 1D Array ( Mine )#Pop Operation| Pop Operation]]
- [[Stack ADT - 1D Array ( Mine )#Pointer| Pointer]]
- [[Stack ADT - 1D Array ( Mine )#Photo| How it works ( Photo )]]
- [[Stack ADT - 1D Array ( Mine )#Stack Program Code| Stack Program Code]]
	- [[Stack ADT - 1D Array ( Mine )#Functions| Functions]]
		- [[Stack ADT - 1D Array ( Mine )#Initialising our Stack| Initialising our Stack]]
		- [[Stack ADT - 1D Array ( Mine )#Displaying Array| Displaying Array]]
		- [[Stack ADT - 1D Array ( Mine )#Inserting Values| Inserting Values]]
		- [[Stack ADT - 1D Array ( Mine )#Pop Function| Pop Function]]
		- [[Stack ADT - 1D Array ( Mine )#Delete Specific Element| Deleting Specific Element]]
		- [[Stack ADT - 1D Array ( Mine )#Bubble Sort| Bubble Sort]]
		- [[Stack ADT - 1D Array ( Mine )#Insertion Sort| Insertion Sort]]
		- [[Stack ADT - 1D Array ( Mine )#Linear Search| Linear Search]]
			- [[Stack ADT - 1D Array ( Mine )#Displaying the "*result*" of linear search| Displaying Result of Linear Search]]
		- [[Stack ADT - 1D Array ( Mine )#Binary Search| Binary Search]]
			- [[Stack ADT - 1D Array ( Mine )#Displaying the "*result*" of binary search| Displaying Result of Binary Search]]

---

- [[Stack ADT - 1D Array ( Mine )#Stack Program Code Example| Example]]
	- [[Stack ADT - 1D Array ( Mine )#Full Stack Code ( Template )| Template ]]

---

My Links

- [[Stack ADT - 1D Array ( Mine )#Socials| Link to Socials]]

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

>[!note]-
>There will be a global pointer called `top` of type `INTEGER`
>I will not be declaring it every time in functions

## Initialising our Stack

To make our stack, we need to initialise an array and a global pointer.

```python

# DECLARE ARRAY stack: INTEGER
stack = []

# DECLARE top: INTEGER
# Global variable "top" which will be our pointer
global top

```

## Displaying Array

This is a function that can be called to display the array.

```python

# FUNCTION display_array()
def display_array():

    # If array `stack` is EMPTY
    if not stack:

        # If array is EMPTY; then pointer "top" will be "0"
        top = -1

        print()
        print("EMPTY")
        print()
        print("Top = " + str(top))
        print()

    # If NOT empty, prints values line by line
    else:

        print()

        # DECLARE index: INTEGER
        # Prints elements line by line
        for index in stack:  
        
            print(index)
            
        top = len(stack) - 1

        print()
        print("Top: " + str(top))
        print()

```

>[!info]
>If `top = 0`
>This means that the **lower bound** of our array is "*1*"

## Inserting Values

This function will allow the user to enter values in the array

```python

# FUNCTION insert_values()
def insert_values():

    # Exception Handling
    try:

        # Pointer "top" will take size of array
        top = len(stack) -1

        print()

        # DECLARE array_size: INTEGER
        # Ask the user to size of array
        array_size = int(input("Please Enter Size Of Array: "))

        print()

        # DECLARE x: INTEGER
        # Adding values in range of "array_size" to the array
        for x in range(array_size):

            # DECLARE user_input: INTEGER
            # Ask the user to enter values of array
            user_input = int(input("Please Enter A Value: "))

            # Inserting value at the end of array ( LIFO )
            stack.append(user_input)

            # Increment pointer "top" by 1
            top += 1

        # Outputs pointer "top"
        print()
        print("Top : " + str(top))
        print()

    # If user inputs any other character than integer values
    except ValueError:

        print()
        print("Please Enter Integer Values Only")
        print()

```

## Pop Function

What can I say, this is a *built-in* function found in Python natively. It is used to remove the last item.

```python

# FUNCTION pop_operation()
def pop_operation():

    # Removing the last item in array "stack"
    stack.pop()

    print()

```

>[!info]
>```python
>pop()
>```
>- It can also remove an element at any address by passing the address inside the function
>- But in our use case, we only need to remove the last item, so no need to pass any values inside function.

## Delete Specific Element

This function will allow a user to:

- Enter a value
- If the value is found
	- The function will remove the value
- Else
	- The function will output an appropriate message

### With ONLY **For Loop**

```python

# FUNCTIOn remove_value_for()
def remove_value_for():

    # Exception Handling
    try:

        # Pointer "top" take the value of length of array
        top = len(stack) -1 

        # DECALRE array_length: INTEGER
        # Variable "array_length" will take the value of length of array
        array_length = len(stack)

        # DECALRE found_for: BOOLEAN
        # Variable "found" will act as the "finder"
        found_for = False

        # DECLARE value_to_remove_for: INTEGER
        # Ask the user to input a value to remove
        value_to_remove_for = int(input("Please Enter A Value To Remove: "))

        # Removing Value:

        # DECLARE count: INTEGER
        # Steps into array to find value
        for count in range(array_length):

            # If value has been found
            if stack[count] == value_to_remove_for:

                # Function remove value
                stack.remove(stack[count])
                found_for = True
                print(f"{value_to_remove} has been removed!")

                # Decreases pointer by 1
                top -= 1

                # Escaping the loop
                break

        print(f"Top (remove value - for): {top}")

        # When value has NOT been found
        if found_for == False:

            # Outputs appropriate message
            print()
            print(f"{value_to_remove_for} has NOT been found!")
            print()

    except ValueError:

        # If user inputs any other character other than integer values
        print()
        print("Please Enter Integer Values Only!")
        print()

```

## Bubble Sort

This function will allow us to sort the array in ascending order; why *ascending order you make ask?*; This is because **binary search** requires the array to be sorted ( **ascending order** ).

![[Bubble Sort - Python#Template - 1D Array]]

## Insertion Sort

Another method we could have use is ( *drum-roll* ) **insertion sort**. To be honest, just use [[Stack ADT - 1D Array ( Mine )#Bubble Sort| bubble sort]], it is much better to use **bubble sort** as it is more efficient for large data set.

Nevertheless, here is the code.

![[Insertion Sort - Python#Template 1D-Array]]

## Linear Search

This function is a nice and **simple** one; like a good old friend that will help you to find your way.

What else can I say, its just a [[Python Data View#Searching Algorithms| search algorithm]]

![[Linear Search - Python#Template 1D-Array]]

### Displaying the "*result*" of Linear Search

```python

# Calling Function to `main` Program
result_linear_search = linear_search()

# If search value has been found
if result_linear_search != -1:

    # Outputs appropriate message
    print(f"Value has been found at address: {result_linear_search}")

# If search value has NOT been found
else:

    # Outputs appropriate message
    print("Your value has not been found!")

```

## Binary Search

This is another much better way of searching for an element/item. 
This is because it cuts the array every time it does not find the "*value*".

![[Binary Search - Python#Template - 1D Array ( Non-Recursive )]]

### Displaying the "*result*" of Binary Search

```python

# Exception Handling
try:

	# DECLARE search_value: INTEGER
	# Asking user to enter a value to search
    search_value = int(input("Please Enter A Value To Search: "))

except ValueError:

    # Output appropriate message
    print()
    print("Please Enter Integer Values Only")
    print()

# Calling Function `main` Program
result_binary_search = binary_search(stack, search_value)

# If search value has been found
if result_binary_search != -1:

    # Outputs appropriate message
    print(f"Search Value: {search_value}; has been found at {result_binary_search}")

# If search value has NOT been found
else:

    # Outputs appropriate message
    print(f"{search_value} has not been found!")

```

---

# Stack Program Code Example

## Full Stack Code ( Template )

```python

# DECLARE ARRAY stack: INTEGER
stack = []

# DECLARE top: INTEGER
# Global variable "top" which will be our pointer
global top

# FUNCTION display_array()
def display_array():

    # If array "stack" is EMPTY
    if not stack:

        # If array is EMPTY; then pointer "top" will be "0"
        top = 0

        print()
        print("EMPTY")
        print()
        print(f"Top: {top}")
        print()

    # If NOT empty, prints values line by line
    else:

        print()

        # DECLARE index: INTEGER
        # Prints elements line by line
        for index in stack:  

            print(index)

        top = len(stack)

        print()
        print(f"Top: {top}")
        print()

# FUNCTION insert_values
def insert_values():

    # Exception Handling
    try:

        # Pointer "top" will take size of array
        top = len(stack)

        print()

        # DECLARE array_size: INTEGER
        # Ask the user to size of array
        array_size = int(input("Please Enter Size Of Array: "))

        print()

        # DECLARE x: INTEGER
        # Adding values in range of "array_size" to the array
        for x in range(array_size):

            # DECLARE user_input: INTEGER
            # Ask the user to enter values of array
            user_input = int(input("Please Enter A Value: "))

            # Inserting value at the end of array ( LIFO )
            stack.append(user_input)

            # Increment pointer "top" by 1
            top += 1

        # Outputs pointer "top"
        print()
        print(f"Top: {top}")
        print()

    # If user inputs any other character other than integer values
    except ValueError:

        print()
        print("Please Enter Integer Values Only")
        print()

# FUNCTION pop_operation()
def pop_operation():

    # Removing the last item in array "stack"
    stack.pop()
    print()

# FUNCTION remove_value_while()
def remove_value_while():

    # Exception Handling
    try:

        # Pointer "top" will take size of array
        top = len(stack)

        # DECLARE array_length: INTEGER
        # Variable "array_length" will hold the length of array
        array_length = len(stack)

        # DECLARE found: BOOLEAN
        # Variable "found" will act as a "finder"
        found = False

        # DECLARE value_to_remove: INTEGER
        # Ask the user for a value to remove
        value_to_remove = int(input("Please Enter A Value To Remove: "))

        # Condition to enter array "stack"
        while not found:

            # Steps into array to find value
            # DECLARE i: INTEGEr
            for i in range(array_length):

                # If value has been found
                if stack[i] == value_to_remove:

                    # Function remove value
                    stack.remove(stack[i])
                    found = True

                    print(f"{value_to_remove} has been removed!")

                    # Decreases pointer by 1
                    top -= 1

                    # Escaping for loop ( found )
                    break

            # Escaping while loop ( NOT found )
            break

        # Outputs pointer "top" value
        print()
        print(f"Top ( remove function - while ): {top}")

        # When value has NOT been found
        if found == False:

            # Outputs appropriate message
            print()
            print(f"{value_to_remove} has NOT been found!")
            print()

    except ValueError:

    # If user inputs any other character other than integer values
        print()
        print("Please Enter Integer Values Only")
        print()

# FUNCTION remove_value_for()
def remove_value_for():

    # Exception Handling
    try:

        # Pointer "top" take the value of length of array
        top = len(stack)

        # DECLARE arrary_length: INTEGER
        # Variable "array_length" will take the value of length of array
        array_length = len(stack)

        # DECLARE found: BOOLEAN
        # Variable "found" will act as the "finder"
        found_for = False

        # Ask the user to input a value to remove
        # DECLARE value_to_remove_for: INTEGER
        value_to_remove_for = int(input("Please Enter A Value To Remove: "))

        # DECLARE count: INTEGER
        # Removing Value:
        for count in range(array_length):

            # Steps into array to find value
            if stack[count] == value_to_remove_for:

                # Function remove value
                stack.remove(stack[count])
                found_for = True
                print(f"{value_to_remove_for} has been removed!")

                # Decreases pointer by 1
                top -= 1

                # Escaping the loop
                break

        print(f"Top (remove value - for): {top}")

        # When value has NOT been found
        if found_for == False:

            print()
            # Outputs appropriate message
            print(f"{value_to_remove_for} has NOT been found!")
            print()

    except ValueError:

        # If user inputs any other character other than integer values
        print()
        print("Please Enter Integer Values Only!")
        print()

# FUNCTION bubble_sort()
def bubble_sort():

    # Pointer "top" will hold the length of the array
    top = len(stack)

    # DECLARE array_length: INTEGER
    # Variable "array_length" will also hold the length of array
    array_length = len(stack)

    # DECLARE swaps: INTEGER
    # Variable "swaps" will hold how many times, values have been swapped
    swaps = 0

    # DECLARE update: BOOLEAN
    # Variable "update" will become true if array has been sorted
    update = True

    while update == True and array_length > 1:

        # Variable "update" become "false" as it need to become updated after swap
        update = False

        # DECLARE x: INTEGER
        for x in range(0,array_length - 1):

            # DECLARE y: INTEGER
            for y in range(0, array_length -1):

                # Ascending Order
                # This is because "Binary Search" will need to be in ascending order
                if stack[y] > stack[y + 1]:

                    # DECLARE temp: INTEGER
                    # Swapping Part
                    temp = stack[y]
                    stack[y] = stack[y + 1]
                    stack[y + 1] = temp

                    # "swaps" increments by 1
                    swaps += 1
                    # "update" becomes true has value has been swapped
                    update = True

# FUNCTION insertion_sort(
def insertion_sort():

    # DECLARE array_length: INTEGER
    # Variable "array_length" will hold the length of array "stack"
    array_length = len(stack)

    # DECLARE i: INTEGER
    # Sorting part of algorithm
    for i in range(1, array_length):

        # Variable "values" will hold the values at address "i"
        values = stack[i]

        # DECLARE j: INTEGER
        # Variable "j" will hold the value to the left of "values"/"i"
        j = i - 1

        # Condition to enter while loop
        # The part "stack[j] > values" ( ascending order )
        # It checks if for example: index 0's value is > than index 1's value
        # If "yes" then it swaps
        while j >= 0 and stack[j] > values:

            # Swapping Part
            stack[j + 1] = stack[j]

            # Decrease "j" by 1
            j -= 1

        # If already sorted
        stack[j + 1] = values

# FUNCTION linear_search()
def linear_search():

    # Exception Handling
    try:

        # DECLARE array_length: INTEGER
        # Variable "array_length" will hold the length of the array
        array_length = len(stack)

        # DECLARE search_value: INTEGER
        # Ask user for a value to search
        search_value = int(input("Please Enter A Value To Search: "))

        # DECLARE i: INTEGER
        # Steps through array "stack"
        for i in range(0,array_length):

            # If value to be searched has been found
            if stack[i] == search_value:

                # Returns address of "search_value"
                return i

        # Else if NOT found
        return - 1

    # If user enters any other character except integer values

    except ValueError:

        # Outputs appropriate message
        print()
        print("Please Enter Integer Values")
        print()

# Binary Search

# Exception Handling
try:

	# Asking user to enter a value to search
    search_value = int(input("Please Enter A Value To Search: "))

except ValueError:

    # Output appropriate message
    print()
    print("Please Enter Integer Values Only")
    print()

# FUNCTION binary_search(DECLARE ARRAY stack: INTEGER, DECLARE search_value: INTEGER)
def binary_search(stack, search_value):

    # Return Function that perform the binary search calculations
    return binary_search_calc(stack, 0, len(stack) - 1, search_value)

# FUNCTION binary_search_calc(DECLARE ARRAY stack: INTEGER, DECLARE lower: INTEGER, DECLARE upper: INTEGER, DECLARE search_value: INTEGER)
def binary_search_calc(stack, lower, upper, search_value):

    # Condition to perform binary search
    while lower <= upper:

        # DECLARE mid: INTEGER
        # Calculates the mid-point of array
        mid = (lower + upper) //2

        # If at mid-point, search value  is there; we return the address
        if stack[mid] == search_value:

            return mid

        # if value at mid-point is less than search value; then we cut bottom part of "stack"
        elif stack[mid] < search_value:

            lower = mid + 1

        else:

            # If value at mid-point is greater than search value: then we cut the upper part of array
            upper = mid - 1

    # If value has not been found
    return - 1

# Calling Functions

display_array()

print()
print("INSERT VALUES IN ARRAY")

insert_values()

print("REMOVING ONE ( LAST ) VALUE")

pop_operation()

print("DISPLAYING ARRAY AFTER POP OPERATION")

display_array()

print("USER DELETE ITEM - WHILE")

remove_value_while()

print("DISPLAYING ARRAY AFTER USER REMOVE ITEM")

display_array()

print("USER DELETE ITEM - WHILE")

remove_value_for()

display_array()

print("BUBBLE SORT:")

bubble_sort()

#insertion_sort()

display_array()

print("LINEAR SEARCH")

# Linear Search Result
result_linear_search = linear_search()

# If search value has been found
if result_linear_search != -1:

    # Outputs appropriate message
    print(f"Has been found at {result_linear_search}")

# If search value has NOT been found
else:

    # Outputs appropriate message
    print("Has not been found!")

print()
print("BINARY SEARCH")
print()

# Binary Search Result
result_binary_search = binary_search(stack, search_value)

# If search value has been found
if result_binary_search != -1:

    # Outputs appropriate message
    print(f"Search Value: {search_value} has been found at {result_binary_search}")

# If search value has NOT been found
else:

    # Outputs appropriate message
    print(f"{search_value} has not been found!")

print()

```

>[!info]
>The function "**insertion_sort()**" is not used in this code, though we could remove "*#*" to be able to **use** it.

---

# Socials

- [**Instagram**](https://www.instagram.com/s.sunhaloo/)
- [**YouTube**](https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg)
- [**GitHub**](https://www.github.com/Sunhaloo)

---

S.Sunhaloo
Thank You!