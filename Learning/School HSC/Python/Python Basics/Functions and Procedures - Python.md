---
Aliases: Functions and Procedure Python
Tag: python, basics
Author: S.Sunhaloo
Type: Function / Procedures
Date: 2023-10-01
Status: Completed
---

## List of Contents

- [[Functions and Procedures - Python#What is a Function / Procedure?| What is a Function / Procedure?]]
	- [[Functions and Procedures - Python#What are Built-In Functions | What are Built-In Functions]]
	- [[Functions and Procedures - Python#Calling a Function / Procedure| Calling a Function / Procedure]]
	- [[Functions and Procedures - Python#Advantages of Functions / Procedures| Advantages]]
	- [[Functions and Procedures - Python#Functions| Functions]]
	- [[Functions and Procedures - Python#Procedures| Procedures]]
		- [[Functions and Procedures - Python#Arguments and Passing of Values| Arguments and Passing of Values]]
	- [[Functions and Procedures - Python#Parameters | Parameters]]
		- [[Functions and Procedures - Python#Examples Passing our *parameters* | Examples]]
- [[Functions and Procedures - Python#Differences between Functions and Procedures| Differences between Functions and Procedures]]
	- [[Functions and Procedures - Python#Pseudocode| Pseudocode]]
	- [[Functions and Procedures - Python#Programming Languages| Programming Languages]]
		- [[Functions and Procedures - Python#Python Data View Python| Python Data View Python]]
		- [[Functions and Procedures - Python#Visual Basic Data View Visual Basic| Visual Basic]]
- [[Functions and Procedures - Python#Simple Functions / Procedures in Python | Simple Functions / Procedures in Python]]
- [[Functions and Procedures - Python#Useful Example Of Functions | Useful Example Of Functions]]

---

My Links

- [[Functions and Procedures - Python#Socials | Link to Socials]]

---

# What is a Function / Procedure?

My understand of function / procedure is that is a piece of code that has been written inside a main code.

Think of it this way; when we write notes ( general daily notes ), we have a:

- Header ( Main Point )
	- Sub Header(s) ( Breaking Down the Main Point )

Thus, we could say that, functions / procedures **make up** the *main code*  ( Main Point ).
In modern programming, it would be very **difficult** *without* using functions or procedures. This is because they offer so many advantages.

## Calling a Function / Procedure

Functions and Procedures can be **called** many times.

- "*Calling*" means to use the "*sub-headers*" / functions / procedure into the main program
	- Thus the **main program** can *execute* the function / procedure and output the necessary information.

---

# What are Built-In Functions

The built-in function are the functions that already exists in the Programming Language.
Here are some examples of Built-In Function in Python:

1. [[String Manipulation - Python#Capitalize Function | capitalize()]]
2. [[Stack ADT - 1D Array ( Mine )#Pop Function| pop()]]

Here are all the Built-In Functions in Python, Click [Here](https://www.w3schools.com/python/python_ref_functions.asp)

---

# Advantages of Functions / Procedures:

Here are some advantages of **function** / **procedures**:

1. Increases program readability

- These ( $\downarrow$ ) ones are a bit similar to [[Subroutines]]

2. Reduces errors as each functions / procedure can be tested
3. Increases productivity as many people can work on the same project at once
	- Then the program can be created by adding all other functions into the main code
4. Can use the functions / procedure more than once

>You can [google](https://www.google.com) other advantages. I did not wanted to include this part actually. But here I am, writing this part.

---

## Functions

A **function** / **subroutine** / **method**( in OOP ) is a *sequence of program instructions* that performs a **specific task**.

Again it can be [[Functions and Procedures - Python#Calling a Function / Procedure| called]] into the *main program* to be executed.

## Procedures

A procedure / subroutine is also defined as a *sequence of program instructions* that performs a **specific task**.

Same as function; it can be [[Functions and Procedures - Python#Calling a Function / Procedure| called]] into the main program to executed. But it has some differences and some as wee say "*quirks and features*".

> See below ( $\downarrow$ )  for the differences between functions and procedures.

### Arguments and Passing of Values ( see *[[Functions and Procedures - Python#Parameters | parameters]]* below )

#### Arguments

A **function** or a **procedure** can *take* a value from a user / programmer ( writing the code ). This is called an **argument**. 

> The function takes in an argument.
> Like for example to measure volume of square, we need the *length*;
> Thus we could say, *length* is an **argument** of the function.

#### Passing Of Values

Thus, to *use* the function / procedure properly, we need to **pass**

> Hence to calculate the volume; us, users need to **pass** the value of *length*

---

# Parameters

Parameters are very simple. The **purpose** of a parameter is to take a value from the *main* program and "*pass*" it into the function; so that the function can operate.

## Examples: Passing our *parameters*

### Example 1: Displaying User's Name

```python

# Displaying User's Name

print()

# Asking the user to input his name
user_name = str(input("Please Enter Your Name: "))

# Function with identifier name "display_name"

# In this function we are passing our
# user_name
def display_name(user_name):

    print()
    print(f"Your Name: {user_name}")
    print()

# Calling Function
display_name(user_name)

```

>[!tip] Note
>The value inside the *brackets* of the **function** does not need to be the same as the **variable** or **constant** that we are using the the main program

### Example 2: Calculating the Volume of Cylinder

```python

# Volume of Cylinder Calculator

# Exception Handling
try:

    # Ask the user to input radius
    radius = float(input("Please Enter Radius: "))

    # Ask the user to input height
    height = float(input("Please Enter Height: "))

# If user enter any other data types than "real" numbers
except ValueError:

    # Outputs the appropriate message
    print()
    print("Please Enter Real Numbers Only!")
    print()

# Function with the identifier name "vol_calc"

# In this function we pass our
# Radius; in this case ---> x
# Height; in this case  ---> y
def vol_calc(x, y):

    # Calculating the volume of cylinder
    volume = float((2 * (22 / 7)) * x * y)

    print()
    print(f"Volume Of Cylinder = {volume}")
    print()

# Calling Function
vol_calc(radius, height)

```

>[!info]
>See how the above ( $\uparrow$ ) code does have **different** "*variables*" inside the function's bracket.

---

# Differences between Functions and Procedures

- A **function**  is code that can **either** *return a value* or *not return a value $\Rightarrow$ returns nothing*.

- A **procedure** can return *one value* or *multiple values* or even *not return a value $\Rightarrow$ returns nothing*.

The above differences are the main differences between the two.

## Pseudocode

In **pseudocode**, to write a:

- Function, we do: FUNCTION
- Procedure, we do: PROCEDURE

## Programming Languages

### [[Python HSC Data View| Python]]

In python, to write a *function* **and / or** *procedure*; we start with the same "*syntax*"; i.e:

>[!tip] Python Functions
>```python
>def procedure():
>```

### [[Visual Basic Data View | Visual Basic]]

As you know, Visual Basic is a fucked up language ( "*in my opinion*" ). Here the way we write *functions* and *procedures* is different.

>[!tip] Visual Basic Function
>```vbnet
>Function Function_Name As Datatype
>```

>[!tip] Visual Basic Procedure
>```vbnet
>Sub Procedure_Name As Datatype
>```

>[!warning]
>This document is only showing **Functions** and **Procedures** for *Python*. I have only wrote "*[[Functions and Procedures - Python#Visual Basic Data View Visual Basic| Visual Basic]]*"
>**This is to show you the difference between *functions* and *procedures***.

---

# Simple Functions / Procedures in Python

>[!info]
>As as said again, in *Python*, both are written the same way. **Nevertheless**, you must know the [[Functions and Procedures - Python#Differences between Functions and Procedures| differences]] between the two. xD!

## Simple Examples

### Example 1: Basic Function

```python

# Functions / Procedures

# Function with identifier name "hello"
# Which takes 1 argument
# We have not defined the datatype of "name"
# But as you know, we can only concaternate data of the type "String"
def hello(name):

    print()
    # Prints the following messages with the "argument"
    print("Hello " + name)
    print("Have a nice day ahead!")
    print()

# Calling Functionss
# 1st Method:
# Writing "name" DIRECTLY into Function

hello("Mate")

hello("my friend")

# 2nd Method
# Writing "name" in a variable
# I recommend this one, then we could use the the "variable" again
user_name = str(input("Please Enter A Name: "))

print("Displaying Name")
hello(user_name)

```

In this [[Functions and Procedures - Python#Example 1| example]], we see that the function takes in one **[[Functions and Procedures - Python#Arguments| arguments]]**. Thus to *use* the function, we need to **[[Functions and Procedures - Python#Passing Of Values| pass]]** values into the function.

### Example 2: The **return** statement

```python

# Functions / Procedures

# Function with identifier name "multiply"
# This function will take 2 arguments
# We could write it better by making the user enter "integer" values
# Because if we input "strings", it will "glue" the text together
def multiply(number1, number2):

    # Multiplies the 2 numbers together
    result = number1 * number2

    # It will output the result of the multiplication
    return result

# Calling the function and passing 2 values
print()
print("Calling Function | Note: Will NOT Display")
print()

multiply(5, 5)

# Heh! what happened nothing showed up!
# This is because the we need to print the function
# Hence, we do:

print()
print("Calling Function | Will Display")
print()

# Calling Function and Displaying result
print("Mutiplication: " + str(multiply(6, 6)))

# 2nd Method to do this
# What if we need to multiply 12 with 90 a lot
# Then we could make a "variable" what will take our function and
# Thus we can you it multiple time
times_12_90 = multiply(12, 90)

# Display the answer
print()
print(times_12_90)

print()

print("12 times 90 is: " + str(times_12_90))
print()

```

### Example 3: Function inside another function

The title I think is simple enough to understand. Like what can I say: It's just a function *inside* another function

```python

# Functions / Procedures

array = []

# Function with identifier name will "display" our array.
def display():

    # If there is nothing in the array
    if not array:

        print()
        print("Nothing In Array!")
        print()

    else:

        # If there is something in the array
        for x in array:

            # Prints values inside array on separate lines
            print(x)

# Function with idenfier name "main" that will allow us to use the program
def main():

    # Calling Function "display"
    display()

    # Exception Handling - Will Explain Later; It's the simplest thing
    try:

        # Asking the user to enter size of array
        array_size = int(input("Please Enter Size Of Array: "))

        # Asking the user to enter data into array of his specific size
        for i in range(array_size):

            # Prompts user to enter value
            user_input = int(input("Please Enter A Value: "))

            # "Appends" data to array
            array.append(user_input)

    except ValueError:

        print()
        print("Please Enter Integer Values Only")
        print()

    print()

    # Calling Function "display" Again to see changes
    display()

    print()

# Calling Main Function
main()

```

# Useful Example Of Functions

>[!warning]-
>These next examples will **not** run on its *own*. This is because it is the *function* **only**!

## Example 1: Displaying an array

What can I say about it, see yourself, the code is easy enough for a 2 year old to understand :)

```python

# Displaying An Array

# Function with identifier name "display_anime" which will display array "anime"
def display_anime():

    # If array is empty
    if not anime:

        print()
        print("Array Is Empty!")
        print()

    else:

        for x in anime:  

            # Outputs the value of array on separate lines
            print(x)

```

## Example 2: Insertion Sort

This [[Python HSC Data View#Sorting Algorithms| sorting algorithm]] will sort an array, it is a simple function.

```python

# Insertion Sort

# Function with identifier name "insertion_sort"
# It will take 1 argument, i.e our array
def insertion_sort(array):

    # Calculate length of array
    length_array = len(array)

    # "for" loop that starts at index 1 instead of 0
    for i in range(1, length_array):

        # Values at address "i"
        values = array[i]

        # Values to the left of "i" (  one before "i")
        j = i - 1

        # Condition to enter "while" loop
        while j >= 0 and array[j] > values:

            # Sorting Part
            # Swapping values
            array[j + 1] = array[j]

            # Decrease "j" by 1
            j = j - 1
            
        # Already sorted
        array[j + 1] = values

```

## Example 3: Bubble Sort

This is another [[Python HSC Data View#Sorting Algorithms| sorting algorithm]], it is also simple, but *I* think it works better compared to [[Functions and Procedures - Python#Example 2 Insertion Sort | insertion sort]]

```python

# Bubble Sort

# We have to pass the array into the procedure/function
# Let our array be called "array" 
def bubblesort_optimised(array):

	# We will have some other variables
	# "update" will check if the value has moved from original place
    update = True

	# "swaps" will keep track of the number of times that value has been swapped
    swaps = 0

	# Conditin to enter while loop
    while update == True and len(array) > 1:


        update = False

		# Number of times it will sort the array
        for x in range(0, len(array) - 1):

			# Checks every value in array
            for y in range(0, len(array) - 1):

                if array[y] > array[y +1]:

					# Swapping part of algorithm
                    temp = array[y]
                    array[y] = array[y + 1]
                    array[y + 1] = temp
                    
                    swaps += 1
                    update =True
    # This line of code below is NOT necessary to use, as it will still sort the array
    return array, swaps
```

## Example 4: Linear Search

[[Python HSC Data View#Searching Algorithms| Searching algorithm]] that does not need the array to be sorted to find the required values.

```python

# Linear Search Function

# Function with identifier name "linear_search"
# 2 "Arguments" need to be passed in function
# These arguments are: 1. Array and 2. Variable that hold the value to be searched
def linear_search(array, value_to_be_searched):

	# Stepping into array ( from 0 to end/length of array )
	for i in range(0, len(array)):

		# Checks if value at index is equal to value to be searched
		if array[i] == value_to_be_searched:

			# If value has been found, then it will return the address of the data/value
			return i

	# If value has NOT been found, it will return "-1"
	return -1 

```

## Example 5: Binary Search

This [[Python HSC Data View#Searching Algorithms| searching algorithm]] does need the array to be sorted before applying this function ( "*binary search*" ).

```python

# Binary Search

# We need to pass 2 arguments inside the function
# We need to pass the array - In this case our array is called "array"
# We need to pass our search value - In this case our array is called "user_find"
def binary_search(array, user_find):

    # Another function what will perform the calculations for the binary search
    # In this function we need to pass the;
    # array
    # length of array - 1
    # search value ( user_find )
    return binary_search_calc(array, 0, len(array) - 1, user_find)
  
# Our function "binary_search_calc()" will perform the calculations
# In this function we need to pass some values for;
# array
# length of array - 1
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
        elif array[mid] < user_find:

            # lower takes the index to the right of mid
            lower = mid + 1

        else:

            # upper takes the index to the left of mid
            upper = mid - 1
            
    # If not found
    return -1

```

## Example 6: Removing selected value in array

This function will allow the user to remove a value from an array

```python

# Removing selected value in array

def remove_values():

    # "top" calculates the length of array
    top = len(array)

    # "array_length" calculates the length of array
    array_length = len(array)

    # "found" will become "True" if value has been found
    found = False

    # Exception Handling
    try:

        # Ask the user to enter a value to remove
        user_remove = int(input("Please Enter A Value To Remove: "))

    # If user enters a value other than integer values
    except ValueError:

        # Outputs appropriate message
        print()
        print("Please Enter Integer Values Only!")
        print()

    # Conditions to enter loop
    while not found:

        # Checks the value at every index ( address ) of array
        for count in range(array_length):

            # If value at specific index in = to value to remove
            if array[count] == user_remove:

                # Removes "value to remove"
                array.remove(array[count])

                # "top" decreases by 1
                top -= 1

                # "found" becomes true as values has been found
                found = True

        # Escaping "for loop"
        break  

    # When "found" is still "False"
    if found == False:

        # Outputs appropriate message
        print()
        print(str(user_remove) + " has not been found!")

```

---

# Socials

- [**Instagram**](https://www.instagram.com/s.sunhaloo/)
- [**YouTube**](https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg)
- [**GitHub**](https://www.github.com/Sunhaloo)

---

S.Sunhaloo
Thank You!