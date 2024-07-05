---
Alias: Arrays - Tuples - Sets In Python
Tag: python, basics, 1D-Array, 2D-Array
Author: S.Sunhaloo
Type: Arrays ( 1D / 2D )
Date: 2023-08-16
Status: Completed
---

## List of Contents

- [[Arrays, Tuples, Sets - Python#What is an Array/List?| What is an Array/List?]]
- [[Arrays, Tuples, Sets - Python#What can Arrays Do?| What can Arrays Do?]]
- [[Arrays, Tuples, Sets - Python#What can we do with Arrays?| What can we do with Arrays?]]

---

- [[Arrays, Tuples, Sets - Python#Arrays in Algorithms| Arrays in Algorithms]]
- [[Arrays, Tuples, Sets - Python#Arrays in Data Structures| Arrays in Data Structures]]
---

## One Dimensional Arrays

- [[Arrays, Tuples, Sets - Python#One Dimensional Arrays ( 1D-Arrays )| One Dimensional Arrays ( 1D-Arrays )]]
	- [[Arrays, Tuples, Sets - Python#Creating 1D-Arrays| Creating 1D-Arrays]]
	- [[Arrays, Tuples, Sets - Python#Displaying 1D-Array| Displaying 1D-Array]]
		- [[Arrays, Tuples, Sets - Python#Displaying Empty Arrays| Displaying Empty 1D-Arrays]]
		- [[Arrays, Tuples, Sets - Python#Displaying Non-Empty Arrays| Displaying Non-Empty 1D-Arrays]]
	- [[Arrays, Tuples, Sets - Python#Adding Elements into 1D-Array| Adding Elements into 1D-Array]]
		- [[Arrays, Tuples, Sets - Python#Inserting Elements in 1D-Array| Inserting Elements in 1D-Array]]
		- [[Arrays, Tuples, Sets - Python#Appending Elements into 1D-Array| Appending Elements into 1D-%%  %%Array]]
	- [[Arrays, Tuples, Sets - Python#Deleting Elements From 1D-Array| Deleting Elements From 1D-Array]]
		- [[Arrays, Tuples, Sets - Python#Popping Element From 1D-Array| Popping Element From 1D-Array]]
		- [[Arrays, Tuples, Sets - Python#Removing Element From 1D-Array| Removing Element From 1D-Array]]
		- [[Arrays, Tuples, Sets - Python#Deleting Element Using `del`| Deleting Element Using `del`]]
		- [[Arrays, Tuples, Sets - Python#Clearing  A 1D-Array| Clearing An 1D-Array]]
	- [[Arrays, Tuples, Sets - Python#Copy Contents of One 1D-Array to Another 1D-Array| Copying contents of Arrays]]

---

## Two Dimensional Arrays

- [[Arrays, Tuples, Sets - Python#Two Dimensional Arrays ( 2D-Arrays )| Two Dimensional Arrays ( 2D-Arrays )]]
	- [[Arrays, Tuples, Sets - Python#Creating 2D-Arrays| Creating 2D-Arrays]]
	- [[Arrays, Tuples, Sets - Python#Displaying 2D-Arrays| Displaying 2D-Arrays]]
		- [[Arrays, Tuples, Sets - Python#Displaying Empty 2D-Arrays| Displaying Empty 2D-Arrays]]
		- [[Arrays, Tuples, Sets - Python#Displaying Non-Empty 2D-Array| Displaying Non-Empty 2D-Array]]
	- [[Arrays, Tuples, Sets - Python#Adding Elements Into 2D-Array| Adding Elements Into 2D-Array]]
		- [[Arrays, Tuples, Sets - Python#Inserting Elements into 2D-Array| Inserting Elements into 2D-Array]]
		- [[Arrays, Tuples, Sets - Python#Appending ( adding ) Elements into 2D-Array| Appending ( adding ) Elements into 2D-Array]]
	- [[Arrays, Tuples, Sets - Python#Deleting Elements From A 2D-Array| Deleting Elements From A 2D-Array]]
		- [[Arrays, Tuples, Sets - Python#Popping Elements From 2D-Array| Popping Element From 2D-Array]]
		- [[Arrays, Tuples, Sets - Python#Removing Element From 2D-Array| Removing Element From 2D-Array]]

---

## Tuples in Python

- [[Arrays, Tuples, Sets - Python#Tuples| Tuples]]

---

## Sets in Python

- [[Arrays, Tuples, Sets - Python#Sets | Sets]]
	- [[Arrays, Tuples, Sets - Python#Creating A Set | Creating A Set]]
	- [[Arrays, Tuples, Sets - Python#Convert Arrays and Tuples into Sets | Converting Arrays and Tuples into Sets]]
	- [[Arrays, Tuples, Sets - Python#Add Values / Items to Sets | Add Values / Items to Sets]]
	- [[Arrays, Tuples, Sets - Python#Remove Values / Items from Sets | Remove Values / Items from Sets]]
	- [[Arrays, Tuples, Sets - Python#Removing Duplicate Values | Removing Duplicate Values]]

---

### My Links

- [[Arrays, Tuples, Sets - Python#Socials| Links to Socials]]

---

# What is an Array/List?

An *array* or *list* is a data structure that can store **values** of the **same** *data type*.

# What can Arrays Do?

In programming terms, arrays are usually used to store a **collection of similar data**; the *elements* or *items* in the array have the same **data type**.

This means that we can $\downarrow$ :

# What can we do with Arrays?

In computer science, we could be asked to:

1. Enter elements
2. Organise elements
3. Remove elements
4. Find elements

# Arrays in Algorithms

Some algorithms that relies on *arrays* are:

## Sorting Algorithms

Algorithms that will **sort/organise** the elements in an array. 

- [[Bubble Sort - Python]]
- [[Insertion Sort - Python]]

## Searching Algorithms

Algorithms that will **search/find** an/many elements in an array.

- [[Linear Search - Python]]
- [[Binary Search - Python]]

# Arrays in Data Structures

Data structures that uses arrays to work

- [[Stack ADT - 1D Array ( Mine )]]
- [[Queue ADT - 1D Array ( Mine )]]
- [[Link List ADT - 1D Array]]

# Types of Arrays

There are many types of arrays:

1. One Dimensional Arrays ( 1D-Array ) 
2. Two Dimensional Arrays ( 2D-Array )
3. Multidimensional Arrays ( $>$ 2D-Array )

---

# One Dimensional Arrays ( 1D-Arrays )

**Simplest** form of an array, in which *elements* are stored linearly. These *elements* can be accessed by specifying the **index value** ( *address* ) of each element.

# Creating 1D-Arrays

```python

# Creating 1D-Arrays

# DECLARE ARRAY cars[8]: STRING
cars = ["Rx-7", "Supra", "AE-86","GT-86", "GTR-R32", "McLaren-P1", "Porsche-918-Spyder", "Koenisegg-Regera-R", "Lancer-MR9"]

# DECLARE ARRAY numbers[4]: INTEGER
numbers = [1, 2, 3, 4, 5]

# DECLARE ARRAY float_numbers[4]: REAL
float_numbers = [1.2, 2.3, 3.4, 4.5, 5.6]

```

>[!note]
>We could check the "type" ( data type ) of the arrays about by using the "type" function:
>```python
print(type(car))
print(type(numbers))
print(type(float_numbers))

# Displaying 1D-Array

What if we want to display the array. Thus, there are several methods that we could approach this.

## Displaying Empty Arrays

>I will include all the methods in the same code.

```python

# Displaying Empty 1D-Arrays

# DECLARE ARRAY num[5]: INTEGER
num = [None for x in range(6)]

# DECLARE ARRAY cars[3]: STRING
cars = [0 for i in range(4)]

# DECLARE ARRAY bikes[1]: STRING
bikes = ["Kawasaki H2R", "Panigale V4R"]

# Method 1:

# Displaying Arrays
print()
print(num)
print()

# Method 2:

# Outputs "EMPTY" if array is empty

# If "cars" is "empty"
if not cars:

    # Outputs: Array is EMPTYs
    print("Array is EMPTY!")
    print()

# If array is not empty
else:

    print(cars)

# If "bikes" is "empty"
if not bikes:

    # Outputs: Array is EMPTY
    print()
    print("Array is EMPTY!")
    print()

# If array is not empty
else:

    print(bikes)

print()

```

## Displaying Non-Empty Arrays

### Method 1: This will not print the "*index*" of values

>I will include all the methods in the same code.

```python

# Displaying 1D-Array

# DECLARE ARRAY cars[8]: STRING
cars = ["Rx-7", "Supra", "AE-86","GT-86", "GTR-R32", "McLaren-P1", "Porsche-918-Spyder", "Koenisegg-Regera-R", "Lancer-MR9"]

# DECLARE ARRAY numbers[4]: INTEGER
numbers = [1, 2, 3, 4, 5]

# DECLARE ARRAY float_numbers[4]: REAL
float_numbers = [1.2, 2.3, 3.4, 4.5, 5.6]

print()

# Method 1:

# Display with "[]"
print(float_numbers)
  
print()
print("----------")
print()

# Method 2:

# Displaying on Separate Lines:
for x in cars:

    print(x)

print()
print("----------")
print()

# Method 3:

# Displaying at Specific Locations:
print("Number 1: " + str(numbers[0]))
print("Number 1: " + str(numbers[2]))
print("Number 1: " + str(numbers[4]))

```

### Method 2: Printing values together with "*index*"

```python

# Displaying Arrays with Index

# DECALRE ARRAY motocycles[2]: STRING
motocycles = ["Kawsaki H2R", "Ducati Panigale V4R", "Yamaha M1"]

# DECLARE ARRAY numbers[4]: INTEGER
numbers = [1, 2, 3, 4, 5]

# DECLARE ARRAY Boolean[1]: BOOLEAN
Boolean = [True, False]

print()
print("Boolean Values in Array")
print()

# Method 1: No Index

# DECLARE x: INTEGER
for x in Boolean:

    print(x)

print()
print("Displaying Motocycles")
print()

# Method 2: Index outside array

# DECLARE index: INTEGER
index = 0

# DECLARE y: INTEGER
for y in motocycles:

    print(y, index)
    # Increase `index` by '1'
    index += 1

print()
print("Displaying Numbers")
print()

# Method 3: Index inside array ( Most Used )
for index, numbers in enumerate(numbers, start = 0):
    print(f"Index: {index} => Value = {numbers}")

```

# Adding Elements into 1D-Array

## Inserting Elements in 1D-Array

>[!warning]
>The `.insert()` function will add elements at **specific locations**.

>[!tip] Usage
>To "*insert*" elements into array; we use:
>```python
array.insert(index, element)
>```

```python

# Inserting Elements at Specific Location

# DECLARE ARRAY f1_drivers[3]: STRING
f1_drivers = ["Senna", "Hamilton", "Leclerc", "Bottas"]

# Displaying Array
print(f1_drivers)

# Inserting "Raikonnen" at index "0"
print()
f1_drivers.insert(0, "Raikonnen")
print()

# Displaying Array again to show changes
print(f1_drivers)

print()

```

## Appending Elements into 1D-Array

>[!warning]
>The `.append()` function will add elements at the **end** of an array

There are several methods we could go about. Below you will find these methods.

>[!tip] Usage
>To "append" elements into array; we use:
>```python
array.append(element)
>```

### Method 1: Adding the element when writing the code.

```python

# Appending Elements inside Code

# DECLARE ARRAY array[]: INTEGER
array = []

# Displaying Array
print(array)

# Appending value to "array"

print()
# array[0] <--- 1
array.append(1)
print()

# Display `array` After appending data
print(array)

```

### Method 2: Ask the **user** to enter data into array

- With an array in which the *size* is **already** defined

```python

# Users Appends Elements into Array

# DECLARE ARRAY name[2]: STRING
name = []

print()

# DECLARE x: INTEGER
for x in range(3):

    # DECLARE user_input: STRING
    # Ask User to enter a name
    user_input = input("Please Enter A Name: ")
    # Appends user input into "name"
    name.append(user_input)

print()
print("Displaying Array After User Input")
print()

# Displaying result after appending into `name`
print(name)

print()

```

- With an array in which the *size* is **not** defined

```python

# Users Appends Elements into Array

# DECLARE array_size: INTEGER
# Ask user to enter size of array
array_size = int(input("Please Enter Size Of Array: "))

# DECLARE ARRAY age[array_size]: INTEGER
age = []

print()

# DECLARE x: INTEGER
# Appending Elements in "range ( array_size )"
for x in range(array_size):

    # Ask the user to enter a value / age
    # DECLARE user_age: INTEGER
     = int(input("Please Enter Age: "))
    age.append(user_age)

print()
print("Displaying Array After User Input")
print()

# DECLARE y: INTEGER
# Displaying Elements On Separate Lines
for y in age:

    print(y)

print()

```

# Adding None Repeating Values in Array ( No Duplicate Value )

## Array does not have  a specific size

In the code below, the user will be able to:

- Enter values as much as he likes
	- If user enter a value that is **already** in array
		- The code will output an appropriate message and then continue to input
- To stop entering values in array
	- The user can press **any** *non-integer* value

```python

# Array does not have a size

# DECLARE ARRAY list: INTEGER
list = []

# FUNCTION display()
def display():

    # If array is empty
    if not list:

        print()
        print("ARRAY IS EMPTY!")
        print()

    # If array is NOT empty
    else:

        # DECLARE x: INTEGER
        # Print all values of array in separate lines
        for x in list:

            # Output the values
            print(x)

        print()

# Calling Function `display` into `main` Program
display()

# Telling the user how to exit "while" loop
print("To exit program, press any Non-Integer Value!")
print()

# Condition to enter values in array
# It will keep entering the "while" loop until we "break" from it
# See code below to see how to "break"
while True:

    # Exception Handling
    try:

        # DECLARE user_input: INTEGER
        # Ask the user to enter a value in array "list"
        user_input = int(input("Please Enter A Value: "))

        # Adding the values in array
        # The code will see if "user_input" is already in "list"
        if user_input not in list:

            # Appends the value "user_input" into the array
            list.append(user_input)

        # If user enter a value that is already in array
        else:

            print("Value is already added!")

    # If user want to exit the program
    # Or user want to exit the "while" loop
    except ValueError:

        print()
        # Output appropriate message
        print("Stopping Input")
        print()
        
        # Exits the program
        break

# Calling function `display` into `main` to show changes
display()

```

## Array have a specific size

It is just the same as above, but now the array will have a **specific size**.

```python

# Array with specific size

# DECLARE ARRAY list: INTEGER
list = []

# DECLARE array_size: INTEGER
# Variable to keep track of size of array
# In this case the array size is 5
array_size = 5

# FUNCTION display()
def display():

    # If array is empty
    if not list:

        print()
        print("ARRAY IS EMPTY!")
        print()

    # If array is NOT empty
    else:

        print()

        # DECLARE x: INTEGER
        # Print all values of array in separate lines
        for x in list:

            # Output the values
            print(x)

        print()

# Calling Function `display` into `main` Program
display()

# Telling the user how to exit "while" loop
print("To exit program, press any Non-Integer Value!")
print()

# Condition to enter values in array
# It will keep entering the "while" loop until we "break" from it
# See code below to see how to "break"
while len(list) < array_size:

    # Exception Handling
    try:

        # DECLARE user_input: INTEGER
        # Ask the user to enter a value in array "list"
        user_input = int(input("Please Enter A Value: "))

        # Adding the values in array
        # The code will see if "user_input" is already in "list"
        if user_input not in list:

            # Appends the value "user_input" into the array
            list.append(user_input)

        # If user enter a value that is already in array
        else:

            print("Value is already added!")

    # If user want to exit the program
    # Or user want to exit the "while" loop
    except ValueError:

        # Output appropriate message
        print()
        print("Stopping Input")
        print()
        
        # Exits the program
        break

# Calling function `display` to show changes
display()

```

>[!note]-
>There was another code in which after entering a **repeated value**, the array will **diminished** in *size*.
>Now tell me, who the fuck would want that.

# Deleting Elements From 1D-Array

## Popping Element From 1D-Array

>[!warning]
>The `.pop()` function will remove the last element

>[!tip] Usage
>To "pop" an element from the array; we use:
>```python
>array.pop()
>```

```python

# "Popping" Element From Array

# DECLARE ARRAY food[3]: STRING
food = ["Briani", "Sushi", "Pizza", "Bougir"]

# Displaying Array
print()
print(food)
print()

# Removing Last Element
food.pop()

# Displaying Array After Changes
print(food)

print()

```

>[!note] We can remove any element
>We can simply add the **index** of an element inside the function `pop()` like so:
>`pop(x)`; where `x` is the **index**!

## Removing Element From 1D-Array

>[!warning]
>The `.remove()` function will remove elements found in an array at any location

>[!tip] Usage
>To "remove" an element; we use:
>```python
>array.remove(element)
>```

```python

# Removing Element From Array

# DECLARE ARRAY food[3]: STRING
food = ["Briani", "Sushi", "Pizza", "Bougir"]

# Displaying Array

print()

print(food)

print()

# Removing Element "Briani"
food.remove("Briani")

# Displaying Array After Changes
print(food)

print()

```

## Deleting Element Using `del`

We have another way to delete an element at a **specific** *index*. This is done by using the `del` 
"*function*".

>[!tip] Usage
>To `del` an element from the array; we use:
>```python
>del array_name[index]
>```

>Its not really a function!

Check out the code below $\downarrow$

```python

# Deleting Elements From Array

# DECLARE ARRAY numbers[4]: INTEGER
numbers = [1, 2, 3, 4, 5]

# Display Original Array
print("Original Array")
print()
print(numbers)
print()

# Delete Some Elements

# Delete Value At Index '0'
del numbers[0]

# Delete Value At Index '1'
del numbers[1]

# Delete Value At Index '4'
# NOTE: This will result in error
    # Because Size of Array has DECREASED
del numbers[4]

# Display Modified Array
print("Modified Array")
print()
print(numbers)
print()

```

## Clearing A 1D-Array

>[!warning]
>The `.clear()` will remove **all** elements from array

>[!tip] Usage
>To "clear" an array; we use:
>```python
>array.clear()
>```

```python

# Clearing An Array

# DECLARE ARRAY countries[2]: STRING
countries = ["America", "England", "Japan"]

# Displaying Array
print()
print(countries)
print()

# Clearing The Array
# Removing All Items From Array
countries.clear()

# Displaying Array After Changes
print(countries)
print()

```

# Copy Contents of One 1D-Array to Another 1D-Array

>[!tip] Usage
>To "copy" the **contents** of an array; we use:
>```python
>array.copy()
>```

To copy the contents of one array to another; we need to use the function `copy()`. Check below $\downarrow$ for a sample code.

```python

# DECLARE ... ==> This array is fucked
array_full = [1, 2, 3, "car", 4, "yeet"]

# DECLARE ...
# Empty Array
array_empty = []

# Copy contents of `array_full` to `array_empty`
array_empty = array_full.copy()

```

>[!note]
>If we were to print both `array_full` and `array_empty`.
>We would found that both has the **same** contents.

---

# Two Dimensional Arrays ( 2D-Arrays )

It is a collection of data elements arranged in a grid-like structure. The grid has *rows* and *columns*; meaning that we have **2 indexes**. So when we are accessing our element at a certain point, think of a *cartesian plane*.

What I am trying to say is that, we need to use a **coordinate system** ($x,y$) to find our element.

# Creating 2D-Arrays

The code below will create arrays with the identifier name:

## Method 1: Array have indefinite ( $\infty$ ) size

```python

# Creating 2D-Arrays

# DECLARE ARRAY food[3, 20]: OF STRING
food = [

    ["Water", "Soda"],
    ["Burger", "Sushi"],
    ["Ice-Cream", "Waffles"]
    
]

# Displaying Array "food"
print()
print(food)
print()

# DECLARE ARRAY cars[2, 5]: STRING
cars = [

    ["Pagani", "Koenigsegg"]+
    ["Supra", "GTR-R32", "RX-7", "MR-9"]

]

# Displaying Array "cars"
print(cars)

print()

```

## Method 2: Array has a definite size

I will be including all examples in a single *code box*

```python

# Creating 2D-Arrays

# DECLARE ARRAY Numbers[4, 4]: STRING
Numbers = [[0 for x in range(4)] for x in range(4)]

# DECLARE rows: INTEGER
rows = 25
# DECLARE cols: INTEGER
cols = 2

# DECLARE ARRAY analysis[25, 2]: INTEGER
analysis = [[None for y in range(cols)] for y in range(rows)]

```

>[!note]
>The above array in [[Arrays, Tuples, Sets - Python#Method 2 Array has a definite size| method 2]] has a definite size.

>[!warning]
>For example if we write
>`ARRAY[25, 2]`; this means that:
>- The array "ARRAY" has 25 **rows** and 2 **cols**
>
>But in Python, it is the reversed; see example above $\uparrow$ for array "*analysis*"

# Displaying 2D-Arrays

There are several way that we can outputs the elements of a 2D-Array

## Displaying Empty 2D-Arrays

## Method 1: Array does not have an actual size

```python

# Displaying Empty 2D-Array

# DECLARE ARRAY planes[2, 3]: STRING
planes = [

    [],
    []

]

# DECLARE ARRAY road_names[3, 2]: STRING
road_names = []

# Displaying Array "planes"
print()
print(planes)
print()

# If array is empty
if not road_names:

    #Outputs "EMPTY"
    print("EMPTY")
    print()

# If array in not empty
else:

    # Prints Array "road_names"
    print(road_names)
    print()

```

>[!warning]
>Do not put **[]** inside an *empty* 2D-Array
>**[]** $\rightarrow$ counts as an element
>Example: "**road_names**"
>>Why did I write this?

## Method 2: Array have a set size

I will be using the same example from [[Arrays, Tuples, Sets - Python#Method 2 Array has a definite size| here]]

```python

# Displaying Empty Arrays

# DECLARE ARRAY Numbers[4, 4]: STRING
Numbers = [[0 for x in range(4)] for x in range(4)]

# FUNCTION display_numbers()
def display_numbers():

    # DECLARE i: INTEGER
    for i in Numbers:

        # Displays values ( each 1D-Array ) of array "Numbers" on separate lines
        print(i)

    print()

# DECLARE rows: INTEGER
rows = 25
# DECLARE cols: INTEGER
cols = 2

# DECLARE ARRAY analysis[25, 2]: INTEGER
analysis = [[None for y in range(cols)] for y in range(rows)]

# FUNCTION display_anal()
# Name plays an important part ( remember boys ... and girls )
def display_anal():

    # DECLARE j: INTEGER
    for j in analysis:

        # Displays values ( each 1D-Array ) of array "analysis" on separate lines
        print(j)

    print()

# Calling Functions
print()
print("Example 1:")
print()
print("Displaying array Numbers!")

# Calling Function `display_numbers` to `main` Program
display_numbers()

print()
print("Example 2: I recommend using this one!")
print()
print("Displaying array analysis")

# Calling Function `display_anal` to `main` Program
display_anal()

```

# Displaying Non-Empty 2D-Array

> I will include all the methods in the same code

```python

# Displaying Non-Empty Arrays

# DECLARE ARRAY smart_phones[2, 1]: STRING
smart_phones = [

    ["Pixel"],
    ["Samsung"]

]

# DECLARE ARRAY decimal_numbers[3, 2]: REAL
decimal_numbers = [

    [5.5, 2.0],
    [6.9, 2.9],
    [100.2, 72.6]

]

# DECLARE ARRAY marks[3, 3]: INTEGER
marks = [

    [100, 88, 50],
    [69, 40, 90],
    [100, 64, 40]

]

# Method 1: Same Line

# Displaying Array "smart_phones"
print()
print(smart_phones)

print()
print("-----")
print()

# Method 2: Separate Lines

# DECLARE rows: INTEGER
# Displaying Array "decimal_numbers"
for rows in decimal_numbers:

    # DECLARE cols: INTEGER
    for cols in rows:

        print(cols)

print()
print("-----")
print()

# Method 3: Specific Location

# Displaying Array `marks`

# NOTE: Remember Cartesian Map
print("At Position (3,1): " + str(marks[0][2]))
print("At Position (0,2): " + str(marks[1][0]))
print("At Position (2,3): " + str(marks[2][1]))

print()

```

# Adding Elements Into 2D-Array

## Inserting Elements into 2D-Array

>[!warning]
>The `.insert()` function will add elements at **specific locations**
>
>In addition, this is **not** like a *1D-Array*; as it will be very **tricky** to insert an item at a **specific location** using the `.insert()` function
>
>Hence, we use **create** a function to use. But we **still use** the `.insert()` function

>[!info]
>[!tip] Usage
>To "insert" elements into array; we use:
>```python
array.insert(index, value)
>```

```python

# Inserting Elements at Specific Location

# DECLARE ARRAY array[2, 2]: INTEGER
array = [

    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]

]

# Displaying "array"
print()
print("Array BEFORE Insering New Item")
print()

# DECLARE x: INTEGER
for x in array:

    print(x)

print()

# FUNCTION insert_element(DECLARE ARRAY array: INTEGER, DECLARE index_row: INTEGER, DECLARE index_col: INTEGER, DECLARE value_to_insert: INTEGER)
def insert_element(array, index_row, index_col, value_to_insert):

    # We need to check the "index_row" is in range of "array"
    if 0 <= index_row < len(array):

        # We also need to check the "index_col" is in range of "array"
        if 0 <= index_col < len(array[0]):

            # Insert the desired value at that specific location
            array[index_row].insert(index_col, value_to_insert)

        else:

            # If bounds of array are not in range
            # For "columns"
            print("Invalid column index")

    else:

        # If bounds of array are not in range
        # For "rows"
        print("Invalid row index")

# Calling Function into `main` Program
insert_element(array, 1, 1, 99)

# Displaying "array" after "inserting" element
print("Array AFTER Inserting New Item")
print()

# DECLARE x: INTEGER
for x in array:

    print(x)

```

## Appending ( adding ) Elements into 2D-Array

>[!warning]
>The `.append()` function will add elements at the **end** of an array

There are several methods we could go about. Below you will find these methods.

>[!tip] Usage
>To "append" elements into array; we use:
>```python
array.append(element)
>```

### Method 1: Using a **function** to *append* data into the array

#### Method 1.1: Using a function **made** by us

>[!note]
>Will add the new values ( *row* ) at the **bottom** of array

```python

# Appending Elements into Array

# DECLARE ARRAY array[2, 2]: INTEGER
array = [

    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]

]

# Displaying "array"
print()
print("Array BEFORE Appending New Item")
print()

# DECLARE x: INTEGER
for x in array:

    print(x)

print()

# FUNCTION append_element(DECLARE ARRAY array: INTEGER, DECLARE row_to_add: INTEGER)
def append_element(array, row_to_add):

    array.append(row_to_add)

# DECLARE ARRAY new_row[2]: INTEGER
new_row = [10, 2, 1]

# Calling Function to `main` Program
append_element(array, new_row)

# Displaying "array" after "appending" element
print("Array AFTER Appending New Item")
print()

# DECLARE y: INTEGER
for y in array:

    print(y)

```

### Method 2: Another way to use the `.append()` function is to let the user enter data into the array.

```python

# User Appends Element into Array

# DECLARE ARRAY array[2, 2]: INTEGER
array = []

# FUNCTION user_insert_value()
def user_insert_value():

    # DECALRE num_of_rows: INTEGER
    # Ask the user to input the number of rows
    num_of_rows = int(input("Please Enter Number Of Rows: "))

    # DECALRE num_of_cols: INTEGER
    # Ask the user to input the number of columns
    num_of_cols = int(input("Please Enter Number Of Columns: "))

    # DECALRE x: INTEGER
    # Adding data into 2D-Array
    for x in range(num_of_rows):

        # DECLARE row: INTEGER
        # Array "row" will keep the values in each row
        row = []

        # DECLARE y: INTEGER
        # Steps through the number of columns
        for y in range(num_of_cols):

            # DECLARE value: INTEGER
            # Asking the user to enter a value
            value = int(input("Enter Value At Position [ " + str(x + 1) + " : " +  str(y + 1) + " ] : "))

            # Adds the value to the array "row"
            row.append(value)

        # Adds the value to to original array "array"
        array.append(row)

# Calling Function to `main` Program
user_insert_value()

# Displaying Array
print()
print("Array AFTER Adding Values")
print()

# DECLARE x: INTEGER
for x in array:

    print(x)

```

#### Method 2.2: Using the `.append()` function at specific locations

```python

# Appending Elements at Specific Location

# DECLARE ARRAY array[2, 2]: INTEGER
array = [

    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]

]

# Displaying "array"
print()
print("Array BEFORE Insering New Item")
print()

# DECLARE x: INTEGER
for x in array:

    print(x)

print()

# "Appending" new element directly
array[0].append(99)

# Displaying "array" after "appending" new valeu

print()
print("Array AFTER Appending New Item")

# DECLARE y: INTEGER
for y in array:

    print(y)

```

>[!info]
>In this case, it will append the new value on the **first** *row*

>[!note]
>Some of you might have noticed "*Array[]*" $\Rightarrow$ "*No Size*"
>This is because the size is... "*dynamic*".
>- I do not know how to explain it but you just need to know that it changes the number of columns!

# Deleting Elements From A 2D-Array

## Popping Elements From 2D-Array

>[!warning]
>The `.pop()` function will remove the last element

>[!tip] Usage
>To "*pop*" an element from the array; we use:
>```python
>array.pop()
>```

```python

# DECLARE ARRAY vehicles[3:2]: STRING
vehicles = [

    ["RX-7", "H2R"],
    ["SR-71", "USS Princeton"],
    ["Bus", "Boat"]

]

# Displaying Array "vehicles"
print()
print("Array BEFORE Changes")
print()

# DECLARE x: INTEGER
for x in vehicles:

    print(x)

# Removing last ROW of array "vehicles"
vehicles.pop()

# Displaying Array "vehicles" after removing last row
print()
print("Array AFTER Changes")
print()

# DECLARE y: INTEGER
for y in vehicles:

    print(y)

```

## Removing Element From 2D-Array

### Method 1: Removing a **specific** value from the **entire** 2D-Array

```python

# Removing a specific value from entire 2D-Array

# DECLARE ARRAY array[2:2]: INTEGER
array = [

    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]

]

# FUNCTION remove_value(DECLARE ARRAY array: INTEGER, DECLARE value_to_remove: INTEGER)
def remove_value(array, value_to_remove):

    # DECLARE updated_array: INTEGER
    # new_array = [[checks each value in "one" row] check for every other row]
    updated_array = [[x for x in row if x != value_to_remove] for row in array]

    # Returns the new array "new_array"
    return updated_array

# Displaying array
print()
print("Array BEFORE Removing Value")
print()

# DECLARE x: INTEGER
for x in array:

    print(x)

# Calling Function
new_array = remove_value(array, 5)

print()
print("Array AFTER Removing Value")
print()

# DECLARE y: INTEGER
for y in new_array:

    print(y)

```

## Clearing A 2D-Array

>[!warning]
>The `.clear()` will remove **all** elements from array

>[!info]
>To "clear" an array; we use:
>```python
>array.clear()
>```

```python

# Clearing A 2D-Array

# DECLARE ARRAY brands[3:3]: STRING
brands = [

    ["McDonalds", "KFC", "Pizza Hut"],
    ["Porsche", "Mazda", "Toyota"],
    ["Lockheed", "Boeing", "Airbus"],
    ["Body&Soul", "Supreme", "Nike"]

]

print()

# DECLARE x: INTEGER
# Displaying Array "brands"
for x in brands:

    print(x)

# Clearing Array "brands"
brands.clear()

# Displaying Empty array "brands"

print()
print("EMPTY ARRAY")

print(brands)

```

---

# Tuples

## What are Tuples?

They are basically the same as **lists** / **arrays** in Python; but the main difference is that once a tuple has been set ( *values are added to tuple* ); the values <span style="color: red;">cannot</span> be changed!!!

>[!note]
>Its the fucking same thing as *Arrays*.
>We can perform algorithms like:
>1. [[Bubble Sort - Python | Bubble Sort]]
>2. [[Binary Search - Python | Binary Search]]
>>[!bug] But we CANNOT *change* its Values!!!

# Create Tuples

Below $\downarrow$ we are going to create some Tuples.

```python

# Create Tuples

# DECLARE TUPLE NAMES[2]: STRING
NAME = ("Charles Leclerc", "Lewis Hamilton", "Fred Vasseur")

# DECLARE TUPLE NUMBERS[4]: STRING
NUMBERS = (1, 2, 3, 4, 5)

```

>[!warning] NOTE
>Except from **Adding** or **Removing** data from tuples; we can pretty to the same things as Arrays, so just scroll up if you need anything!

---

# Sets

Similarly to Arrays and Tuples in Python; sets are another data type that ( *again* ) **_resembles_** like **lists**.

## What are Sets?

- It is a collection of data which is **unordered**, *unchangeable* and **unindexed** ( *meaning it is does not have index like arrays and tuples does*! )

They are used to store a collection of data of similar data types or different data types ( *just like arrays and tuples* ).

Even though, we wrote "*unchangeable*"; we **can** *add* or *remove* items from the set. But once a **set** has been "*set*" ( *haha* ); we **cannot** change it.

>[!tip] Summary
>We can add or remove items from a Set unlike Tuples.
>But like Tuples, once the Set has been initialised; we cannot change the contents of it.
>- <span style="color: green;">It does <em>not</em> contain <span style="color: red;">repeated</span> data</span>.

### Creating A Set

- To create an Array, we use square braces $\rightarrow$ `[]`
- To create a Tuple, we use normal curved braces $\rightarrow$ `()`

Then how do we create a Set? You ask... with *Curly Braces* $\rightarrow$ `{}` Yippee!

There are several methods to create a set.

1. Create a set with the Curly Braces `{}`
2. Convert an Array into a Set
3. Convert a Tuple into a Set

```python

# Sets

# DECLARE SET numbers[4]: INTEGER
numbers = {1, 2, 3, 4, 5}

# DECLARE SET conditions[3]: BOOLEAN
conditions = {True, False, True, False}

# DECLARE SET names[3]: STRING
names = {"Lewis Hamilton", "Valterri Bottas", "George Fucking Russell", "Toto Wolff"}

# Output the contents of Sets
print()
print(numbers)
print()
print(conditions)
print()

for i, x in enumerate(names):
    print(i,x)

```

>Even though Sets are **unindexed**; when we use the function `enumerate()`. It will automatically give it and index.
>But sets do **not** have indices ( *index* ) in the traditional sense.

#### Convert Arrays and Tuples into Sets

To convert an Array or Tuple into a *Set*. We need to use the `set()` function.

```python

# Convert Arrays and Tuples into Sets

# DECLARE ARRAY int_array[4]: INTEGER
int_array = [1, 2, 3, 4, 5]
# DECLARE TUPLE float_tuple[4]: REAL
float_tuple = (1.2, 2.0, 4.3, 4.5, 5.0)

# Convert Arrays into Sets
int_set = set(int_array)
print(int_set)

# Convert Tuples into Sets
float_set = set(float_tuple)
print(float_set)

```

### Add Values / Items to Sets

#### Add A Single Value

>[!tip] Usage
>```python
>set.add(value)
>```

To add a value to a set; simple use the function above $\uparrow$ ( *it is similar to [[Arrays, Tuples, Sets - Python#Appending Elements into 1D-Array | append]] function* )

```python

# Add A Single Value to Set

# DECLARE SET set_numbers[4]: INTEGER
set_numbers = {1, 2, 3, 4, 5}

print("\nOriginally:")
print(set_numbers)

# Add 6, 7 and 8 to set
# DECLARE x: INTEGER
x = 6

while x > 5 and x < 9:
    
    # "Appends" the value to set
    set_numbers.add(x)
    # 'x' increases by 1
    x += 1

print("\nAfter Adding Values:")
print(set_numbers)

print()

```

In the code above $\uparrow$; we are still adding a single, **unique** value and the values are: 6, 7 and 8. But we are using a `while` loop to keep adding them, instead of writing like:

```python

set_number.add(6)
set_number.add(7)
set_number.add(8)

```

#### Add Multiple Values / Items to Sets

>Let me show you the code first!

```python

# Add A Single Value to Set

# DECLARE SET set_numbers[4]: INTEGER
set_numbers = {1, 2, 3, 4, 5}
# DECLARE ARRAY nums_to_add[2]: INTEGER
nums_to_add = [6, 7, 8]

print("\nOriginally:")
print(set_numbers)

# Add 6, 7 and 8 to set
set_numbers.update(nums_to_add)


print("\nAfter Adding Values:")
print(set_numbers)

print()

```

In this example, we have a set named `set_numbers` and we have an *array* in which we have the number to add to the set. We use the `.update()` function and pass in the array so that it can add them to the set!

>We could have passed the array directly like so:
>```python
>set_numbers.update([6, 7, 8])
>```

### Remove Values / Items from Sets

#### Remove a Single Value

>[!tip] Usage
>```python
>set.remove(value)
>```

>[!tip] Usage
>```python
>set.discard(value)
>```

To remove values from a set; we can use 2 types of function as mentioned above $\uparrow$.

>[!note]
>The `.remove()` and `.discard()` function does the **same** thing!
>But the `.discard()` function will **not** raise any *error* if it does **not** find the value that it needs to remove.

```python

# Remove Value From Set

# DECLARE SET cars: STRING
cars = {"AMG One", "R32 GTR", "RX-7", "Dacia Sandero", "Nissan Juke", "Lancer Evo 9"}

print("\nOriginal Array:")
print(cars)

# "remove" 'Nissan Juke'
cars.remove("Nissan Juke")

# "discard" 'Dacia Sandero'
cars.discard("Dacia Sandero")

print("\nArray After Removing Values")
print(cars)

print()

```

#### Emulate the [[Arrays, Tuples, Sets - Python#Popping Element From 1D-Array| pop]] Function

```python

# What did you think that there would be code here...
# Do not trust everything on the internet... why did I say that

```

**No**! You cannot `pop()` values from a Set. This is because the `pop` function requires an index to work and as Sets do not have indices; It simple does not work

### Removing Duplicate Values

>[!info]
>Why the fuck am I saying that we need to remove duplicate values... First of all, go fuck yourself and secondly this is my fucking notes. But you can still use it... Please stay!!!
>The reason that I am doing this is because if you are going to **remove** duplicate values / items / data from an array, we normally ( _by normally I am saying how **I** would normally do it_! ) have to
>1. Create another array
>2. Iterate through the array with duplicated values
>3. Append the values of array ( *with duplicated value* ) into the new array while checking if its already in array
>```python
># Remove Duplicated Values
>print()
>
># DECLARE ARRAY duplicated_values: INTEGER
>duplicated_values = [1, 1, 2, 3, 3, 4]
>
># DECLARE ARRAY unique_values: INTEGER
>unique_values = []
>
># Iterate through the array with duplicated values
>
># DECLARE x: INTEGER
>for x in duplicated_values:
>    # If value is NOT already in  'unique_values' add that value
>    if x not in unique_values:
>        # Add the value to the array 'unique_values"
>        unique_values.append(x)
>
>    # If value exists in array 'unique_values'
>    else:
>        print(f"Value {x} is Already in Array\n")
>
># Output the contents of each Array
>print("-"*25)
>print("\nOriginal Array:")
>print(duplicated_values)
>
>print("\nNew Array:")
>print(unique_values)
>print("-"*25)
>
>```

#### Remove Duplicate Values from Array / Tuples

```python

# Remove Duplicate Values from Array

# DECLARE ARRAY array: INTEGER
array = [1, 2, 2, 3, 4, 5, 5]

print("\nOriginal Array:")
print(array)

# Convert the Array into a Set
# Array ---> Set
array = set(array)

# Convert that Set back into Array
# Set ---> Array
array = list(array)

print("\nRemoved Duplicates:")
print(array)
print()

```

Or simply

```python

# Remove Duplicate Values from Array

# DECLARE ARRAY array: INTEGER
array = [1, 2, 2, 3, 4, 5, 5]

print("\nOriginal Array:")
print(array)

# Convert the Array into a Set then into Array again
# Array ---> Set
array = list(set(array)) # ---> One Liner

print("\nRemoved Duplicates:")
print(array)
print()

```

>Much much fucking simpler than that shitty code above $\uparrow$ Right? Right! Right!!!

### Operations of Sets

>[!info]
>I have been writing a lot of things without telling you what Sets are!
>### What are Sets?
>Mathematics, Mathematics and Mathematics!
>Remember the "*sets*" in maths that you did at your shitty school with your shitty school teacher... yeah, that the maths "*thing*" that we are talking about from the beginning.
>
>Normally, we use this with [Venn Diagrams](https://en.wikipedia.org/wiki/Venn_diagram) and hence, we get operations like:
>1. Intersection
>2. Union
>This is what we are going to learn below $\downarrow$.

#### Intersection

We are going to find the "*intersection*" of some sets.

>Returns everything that is in **common** from the sets.

```python

# DECLARE SET set1[2]: INTEGER
set1 = {1, 2, 3}
# DECLARE SET set2[2]: INTEGER
set2 = {2, 3, 4}
# DECLARE SET set3[2]: INTEGER
set3 = {3, 4, 5}

print("Display Sets\n")

# output our sets
print(f"Set 1 = {set1}")
print(f"Set 2 = {set2}")
print(f"Set 3 = {set3}")

print("\nIntersection of `set1` with `set2`\n")
print(f"Intersection: {set1.intersection(set2)}")

print("\nIntersetion of `set1` with `set2` and `set3`\n")
print(f"Intersection: {set1.intersection(set2, set3)} <--- Because we only have '3' that are common in both")

```

#### Difference

Now we are going to find the difference between the sets given. In this scenario ( *ahh! a word that I do not use that often* ); we are going to get the "*items*" that are different from the sets

```python

# DECLARE SET set1[2]: INTEGER
set1 = {1, 2, 3}
# DECLARE SET set2[2]: INTEGER
set2 = {2, 3, 4}
# DECLARE SET set3[2]: INTEGER
set3 = {3, 4, 5}

print("Display Sets\n")

# output our sets
print(f"Set 1 = {set1}")
print(f"Set 2 = {set2}")
print(f"Set 3 = {set3}")

# only returns 1
print("\nDifference of `set1` with `set2`\n")
print(f"Intersection: {set1.difference(set2)}")

# not difference between `set2` with `set1` and `set3`
print("\nDifference of `set2` with `set1` and `set3`\n")
print(f"Intersection: {set2.difference(set1, set3)} <--- Should be Empty")

```

What the fuck! If I said that I will return the difference of the items in the set; i.e the items that are **not** found in *both* sets. Then why the fuck did it not output '*4*' also?

This is because we used `set1.difference(set2)`. But if we would have used `set2.difference(set1)` then you will the '*4*' as output

##### Solution to Problem Above $\uparrow$

To not have to calculate if you get '*1*' or '*4*' as answer; we are going to use the function `symmetric_difference`.

```python

# DECLARE SET set1[2]: INTEGER
set1 = {1, 2, 3}
# DECLARE SET set2[2]: INTEGER
set2 = {2, 3, 4}
# DECLARE SET set3[2]: INTEGER
set3 = {3, 4, 5}

print("Display Sets\n")

# output our sets
print(f"Set 1 = {set1}")
print(f"Set 2 = {set2}")
print(f"Set 3 = {set3}")

# only returns 1
print("\nDifference of `set1` with `set2`\n")
print(f"Intersection: {set1.symmetric_difference(set2)}")

```

>Now we are going to have '*1*' and '*4*' ( `{1, 4}` ) as output!

---

# Socials

- [**Instagram**](https://www.instagram.com/s.sunhaloo/)
- [**YouTube**](https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg)
- [**GitHub**](https://www.github.com/Sunhaloo)

---

S.Sunhaloo
Thank You!