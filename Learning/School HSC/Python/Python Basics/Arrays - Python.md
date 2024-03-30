---
Alias: Arrays In Python
Tag: python, basics, 1D-Array, 2D-Array
Author: S.Sunhaloo
Type: Arrays ( 1D / 2D )
Date: 2023-08-16
Status: Completed
---

## List of Contents

- [[Arrays - Python#What is an Array/List? | What is an Array/List?]]
- [[Arrays - Python#What can Arrays Do? | What can Arrays Do?]]
- [[Arrays - Python#What can we do with Arrays? | What can we do with Arrays?]]

---

- [[Arrays - Python#Arrays in Algorithms | Arrays in Algorithms]]
- [[Arrays - Python#Arrays in Data Structures | Arrays in Data Structures]]
---

## One Dimensional Arrays

- [[Arrays - Python#One Dimensional Arrays ( 1D-Arrays ) | One Dimensional Arrays ( 1D-Arrays )]]
	- [[Arrays - Python#Creating A 1D-Array | Creating An  1D-Array]]
	- [[Arrays - Python#Displaying 1D-Array | Displaying 1D-Array]]
		- [[Arrays - Python#Displaying Empty Arrays | Displaying Empty 1D-Arrays]]
		- [[Arrays - Python#Displaying Non-Empty Arrays | Displaying Non-Empty 1D-Arrays]]
	- [[Arrays - Python#Adding Elements into 1D-Array | Adding Elements into 1D-Array]]
		- [[Arrays - Python#Inserting Elements in 1D-Array | Inserting Elements in 1D-Array]]
		- [[Arrays - Python#Appending Elements into 1D-Array | Appending Elements into 1D-Array]]
	- [[Arrays - Python#Deleting Elements From 1D-Array | Deleting Elements From 1D-Array]]
		- [[Arrays - Python#Popping Element From 1D-Array | Popping Element From 1D-Array]]
		- [[Arrays - Python#Removing Element From 1D-Array | Removing Element From 1D-Array]]
		- [[Arrays - Python#Deleting Element Using `del` | Deleting Element Using `del`]]
		- [[Arrays - Python#Clearing  A 1D-Array | Clearing An 1D-Array]]
	- [[Arrays - Python#Copy Contents of One 1D-Array to Another 1D-Array | Copying contents of Arrays]]

---

## Two Dimensional Arrays

- [[Arrays - Python#Two Dimensional Arrays ( 2D-Arrays ) | Two Dimensional Arrays ( 2D-Arrays )]]
	- [[Arrays - Python#Creating A 2D-Array | Creating A 2D-Array]]
	- [[Arrays - Python#Displaying 2D-Arrays | Displaying 2D-Arrays]]
		- [[Arrays - Python#Displaying Empty 2D-Arrays | Displaying Empty 2D-Arrays]]
		- [[Arrays - Python#Displaying Non-Empty 2D-Array | Displaying Non-Empty 2D-Array]]
	- [[Arrays - Python#Adding Elements Into 2D-Array | Adding Elements Into 2D-Array]]
		- [[Arrays - Python#Inserting Elements into 2D-Array | Inserting Elements into 2D-Array]]
		- [[Arrays - Python#Appending ( adding ) Elements into 2D-Array | Appending ( adding ) Elements into 2D-Array]]
	- [[Arrays - Python#Deleting Elements From A 2D-Array | Deleting Elements From A 2D-Array]]
		- [[Arrays - Python#Popping Elements From 2D-Array | Popping Element From 2D-Array]]
		- [[Arrays - Python#Removing Element From 2D-Array | Removing Element From 2D-Array]]

---

### My Links

- [[Arrays - Python#Socials | Links to Socials]]

---

# What is an Array/List?

An *array* or *list* is a data structure that can store **values** of the **same** *data type*

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

# Creating A 1D-Array

This code will create arrays with identifier name:

- "cars"
- "numbers"
- "float_numbers"

```python

# Creating 1D-Arrays

# DECLARE cars: ARRAY[0:8] OF STRING
cars = ["Rx-7", "Supra", "AE-86","GT-86", "GTR-R32", "McLaren-P1", "Porsche-918-Spyder", "Koenisegg-Regera-R", "Lancer-MR9"]

# DECLARE numbers: ARRAY[0:4] OF INTEGER
numbers = [1, 2, 3, 4, 5]

# DECLARE float_numbers: ARRAY[0:4] OF REAL
float_numbers = [1.2, 2.3, 3.4, 4.5, 5.6]

```

>[!note]
>This code will **not** *display* anything!
>
>Nevertheless, we could check the "type" ( data type ) of the arrays about by using the "type" function:
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

# DECLARE array: ARRAY[0:5] OF INTEGER
num = [None for x in range(6)]

# DECLARE cars: ARRAY[0:3] OF STRING
cars = [0 for i in range(4)]

# DECLARE bikes: ARRAY[0:1] OF STRING
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

else:

    print(cars)

# If "bikes" is "empty"
if not bikes:

    # Outputs: Array is EMPTY
    print()
    print("Array is EMPTY!")
    print()

else:

    print(bikes)

print()

```

## Displaying Non-Empty Arrays

### Method 1: This will not print the "*index*" of values

>I will include all the methods in the same code.

```python

# Displaying 1D-Array

# DECLARE cars: ARRAY[0:8] OF STRING
cars = ["Rx-7", "Supra", "AE-86","GT-86", "GTR-R32", "McLaren-P1", "Porsche-918-Spyder", "Koenisegg-Regera-R", "Lancer-MR9"]

# DECLARE numbers: ARRAY[0:4] OF INTEGER
numbers = [1, 2, 3, 4, 5]

# DECLARE float_numbers: ARRAY[0:4] OF REAL
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

# DECLARE motocycles: ARRAY[2] OF STRING
motocycles = ["Kawsaki H2R", "Ducati Panigale V4R", "Yamaha M1"]

# DECLARE numbers: ARRAY[4] OF INTEGER
numbers = [1, 2, 3, 4, 5]

# DECLARE Boolean: ARRAY[1] OF BOOLEAN
Boolean = [True, False]

print()
print("Boolean Values in Array")
print()

# Method 1: No Index
for x in Boolean:

    print(x)

print()
print("Displaying Motocycles")
print()

# Method 2: Index outside array

# DECLARE index: OF INTEGER
index = 0

for y in motocycles:

    print(y, index)
    index += 1

print()
print("Displaying Numbers")
print()

# Method 3: Index inside array
for index, numbers in enumerate(numbers, start = 0):
    print(f"Index: {index} => {numbers}")

```

# Adding Elements into 1D-Array

## Inserting Elements in 1D-Array

>[!warning]
>The "*.insert()*" function will add elements at **specific locations**

>[!info]
>To "insert" elements into array; we use:
>```python
array.insert(index, value)
># Where:
># "array" is our array
># "index" is the **index** at which element will be added
># "value" is our **item** to add

```python

# Inserting Elements at Specific Location

# DECLARE f1_drivers: ARRAY[] OF STRING
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
>The ".append()" function will add elements at the **end** of an array

There are several methods we could go about. Below you will find these methods.

>[!info]
>To "append" elements into array; we use:
>```python
array.append(element)
># Where:
># "array" is our array
># "element" is the value being added; it is passed inside the append function

### Method 1: Adding the element when writing the code.

```python

# Appending Elements inside Code

# DECLARE array: ARRAY[] OF INTEGER

# Array with identifier name "array" with
# 1. No Values
# 2. Size = "Infinite" when we look at python code
array = []

# Displaying Array
print(array)

# Appending value to "array"

print()
# array[0] <--- 1
array.append(1)
print()

# Display "array" After appending data
print(array)

```

### Method 2: Ask the **user** to enter data into array

- With an array in which the *size* is **already** defined

```python

# Users Appends Elements into Array

# DECLARE name: ARRAY[0:2] OF STRING
name = []

print()

# Appending Elements in "range"
for x in range(3):

    # Ask User to enter a "string"
    user_input = str(input("Please Enter A Name: "))
    # Appends user input into "name"
    name.append(user_input)

print()
print("Displaying Array After User Input")
print()

print(name)

print()

```

- With an array in which the *size* is **not** defined

```python

# Users Appends Elements into Array

# DECLARE age: ARRAY[array_size] OF INTEGER
age = []

print()

# Ask user to enter size of array
array_size = int(input("Please Enter Size Of Array: "))

# Appending Elements in "range ( array_size )"
for x in range(array_size):

    # Ask the user to enter a value ( "integer" )
    user_value = int(input("Please Enter Age: "))
    age.append(user_value)

print()
print("Displaying Array After User Input")
print()

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

# Array with identifier name "list"
# Array with no specific size
list = []

# Function "display" will allow us to display the array
def display():

    # If array is empty
    if not list:

        print()
        print("ARRAY IS EMPTY!")
        print()

    # If array is NOT empty
    else:

        # Print all values of array in separate lines
        for x in list:

            # Output the values
            print(x)

        print()

# Calling Function "display"
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

# Calling function "display" to show changes
display()

```

## Array have a specific size

It is just the same as above, but now the array will have a **specific size**.

```python

# Array with specific size

# Array with identifier name "list"
# Array with no specific size
list = []

# Variable to keep track of size of array
# In this case the array size is 5
array_size = 5

# Function "display" will allow us to display the array
def display():

    # If array is empty
    if not list:

        print()
        print("ARRAY IS EMPTY!")
        print()

    # If array is NOT empty
    else:

        print()

        # Print all values of array in separate lines
        for x in list:

            # Output the values
            print(x)

        print()

# Calling Function "display"
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

# Calling function "display" to show changes
display()

```

>[!note]-
>There was another code in which after entering a **repeated value**, the array will **diminished** in *size*.
>Now tell me, who the fuck would want that.

# Deleting Elements From 1D-Array

## Popping Element From 1D-Array

>[!warning]
>The ".pop()" function will remove the last element

>[!info]
>To "pop" an element from the array; we use:
>```python
>array.pop()
># Where:
># "array" is our array
># NOTE: No values are passed into the function as it need remove the last item... Obviously!

```python

# "Popping" Element From Array

# DECLARE food: ARRAY[] OF STRING
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
>`pop(x)`, Where `x` is the **index**!

## Removing Element From 1D-Array

>[!warning]
>The ".remove()" function will remove elements found in an array at any location

>[!info]
>To "remove" an element; we use:
>```python
>array.remove(element)
># Where:
># "array" is our array
># "element" is the item need to be removed
># NOTE: Our "element" can be a "string"/"integer"

```python

# Removing Element From Array

# DECLARE food: ARRAY[] OF STRING
food = ["Briani", "Sushi", "Pizza", "Bougir"]

# Displaying Array

print()

print(food)

print()

# Removing Last Element
food.remove("Briani")

# Displaying Array After Changes
print(food)

print()

```

## Deleting Element Using `del`

We have another way to delete an element at a **specific** *index*. This is done by using the `del` 
"*function*".

>[!info]
>To "del" an element from the array; we use:
>```python
>del array_name[index]

>Its not really a function!

Check out the code below $\downarrow$

```python

# Deleting Elements From Array

# DECLARE ARRAY numbers: INTEGER
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
>The "*.clear()*" will remove **all** elements from array

>[!info]
>To "clear" an array; we use:
>```python
>array.clear()
># Where:
># "array" is our array

```python

# Clearing An Array

# DECLARE countries: ARRAY[0:2] OF STRING
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

To copy the contents of one array to another; we need to use the function `copy()`. Check below $\downarrow$ for a sample code.

```python

# Our Arrays
# Array with items / things
array_full = [1, 2, 3, "car", 4, "yeet"]
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

# Creating A 2D-Array

The code below will create arrays with the identifier name:

- "*food*"
- "*cars*"

>[!tip] Remember
>"*food*" and "*cars*" are **1D-Arrays**

## Method 1: Array have indefinite ( $\infty$ ) size

```python

# Creating 2D-Arrays

# DECLARE food: ARRAY[3, 20] OF STRING
food = [

    ["Water", "Soda"],
    ["Burger", "Sushi"],
    ["Ice-Cream", "Waffles"]
    
]

# Displaying Array "food"
print()
print(food)
print()

#DECLARE cars: ARRAY[] OF STRING
cars = [

    ["Pagani", "Koenigsegg"]+
    ["Supra", "GTR-R32", "RX-7", "MR-9"]

]

# Displaying Array "cars"
print(cars)

print()

```

>[!note]
>In **python**, array are kind of *infinite* or does not have a *"size"*.
>Example: "**cars**"

## Method 2: Array has a definite size

I will be including all examples in a single *code box*

```python

# Creating 2D-Arrays

# DECLARE Numbers: ARRAY[4: 4] OF STRING
Numbers = [[0 for x in range(4)] for x in range(4)]

# DECLARE analysis: ARRAY[25: 2] OF INTEGER
cols = 2
rows = 25

# Creating array "analysis"
analysis = [[None for y in range(cols)] for y in range(rows)]

```

>[!note]
>The above array in [[Arrays - Python#Method 2 Array has a definite size | method 2]] has a definite size.

>[!warning]
>For example if we write
>"*ARRAY[25:2]*"; this means that:
>- The array "ARRAY" has 25 **rows** and 2 **cols**
>
>But in Python, it is the reversed; see example above $\uparrow$ for array "*analysis*"

# Displaying 2D-Arrays

There are several way that we can outputs the elements of a 2D-Array

## Displaying Empty 2D-Arrays

## Method 1: Array does not have an actual size

```python

# Displaying Empty 2D-Array

# DECLARE planes: ARRAY(2, 3) OF STRING
planes = [

    [],
    []

]

# DECLARE road_names: ARRAY(3,2) OF STRING
road_names = []

# Displaying Array "planes"
print()
print(planes)
print()

# Displaying Array "road_names"
# Outputs "EMPTY" if array is empty
# If "road_names" is empty
if not road_names:

    #Outputs "EMPTY"
    print("EMPTY")
    print()

else:

    # Prints Array "road_names"
    print(road_names)
    print()

```

>[!warning]
>Do not put **[]** inside an *empty* 2D-Array
>**[]** $\rightarrow$ counts as an element
>Example: "**road_names**"

## Method 2: Array have a set size

I will be using the same example from [[Arrays - Python#Method 2 Array has a definite size | here]]

```python

# Displaying Empty Arrays

# DECLARE Numbers: ARRAY[4: 4] OF STRING
Numbers = [[0 for x in range(4)] for x in range(4)]

# Diplaying 2D-Array "Numbers"
# Function with identifier name "display_numbers"
def display_numbers():

    for i in Numbers:

        # Displays values ( each 1D-Array ) of array "Numbers" on separate lines
        print(i)

    print()

# DECLARE analysis: ARRAY[25: 2] OF INTEGER
cols = 2
rows = 25

# Creating array "analysis"
analysis = [[None for y in range(cols)] for y in range(rows)]

# Making a function to display array "analysis"
# Name plays an important part ( remember boys ... and girls )
def display_anal():

    for j in analysis:

        # Displays values ( each 1D-Array ) of array "analysis" on separate lines
        print(j)

    print()

# Calling Functions
print()
print("Example 1:")
print()
print("Displaying array Numbers!")

display_numbers()

print()
print("Example 2: I recommend using this one!")
print()
print("Displaying array analysis")

display_anal()

```

# Displaying Non-Empty 2D-Array

> I will include all the methods in the same code

```python

# Displaying Non-Empty Arrays

# DECLARE smart_phones: ARRAY(2, 1) OF STRING
smart_phones = [

    ["Pixel"],
    ["Samsung"]

]

# DECLARE decimal_numbers: ARRAY(3, 2) OF REAL
decimal_numbers = [

    [5.5, 2.0],
    [6.9, 2.9],
    [100.2, 72.6]

]

# DECLARE marks: ARRAY(3, 3) OF INTEGER
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

# Displaying Array "decimal_numbers"
for rows in decimal_numbers:

    for cols in rows:

        print(cols)

print()
print("-----")
print()

# Method 3: Specific Location

# Displaying Array "marks"

# NOTE: Remember Cartesian Map
print("At Position (3,1): " + str(marks[0][2]))
print("At Position (0,2): " + str(marks[1][0]))
print("At Position (2,3): " + str(marks[2][1]))

print()

```

# Adding Elements Into 2D-Array

## Inserting Elements into 2D-Array

>[!warning]
>The "*.insert()*" function will add elements at **specific locations**
>
>In addition, this is **not** like a *1D-Array*; as it will be very **tricky** to insert an item at a **specific location** using the "*.insert()*" function
>
>Hence, we use **create** a function to use. But we **still use** the "*.insert()*" function

>[!info]
>To "insert" elements into array; we use:
>```python
array.insert(index, value)
># Where:
># "array" is our array
># "index" is the **index** at which element will be added
># "value" is our **item** to add

```python

# Inserting Elements at Specific Location

# DECLARE array: ARRAY[] OF INTEGER
array = [

    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]

]

# Displaying "array"
print()
print("Array BEFORE Insering New Item")
print()

for x in array:

    print(x)

print()

# Function with identifier name "insert_elements"

# In this function, we need to pass:
# array,
# index_row
# index_col
# the value
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

# Calling Function
insert_element(array, 1, 1, 99)

# Displaying "array" after "inserting" element
print("Array AFTER Inserting New Item")
print()

for x in array:

    print(x)

```

## Appending ( adding ) Elements into 2D-Array

>[!warning]
>The ".append()" function will add elements at the **end** of an array

There are several methods we could go about. Below you will find these methods.

>[!info]
>To "append" elements into array; we use:
>```python
array.append(element)
># Where:
># "array" is our array
># "element" is the value being added; it is passed inside the append function

### Method 1: Using a **function** to *append* data into the array

#### Method 1.1: Using a function **made** by us

>[!note]
>Will add the new values ( *row* ) at the **bottom** of array

```python

# Appending Elements into Array

# DECLARE array: ARRAY[] OF INTEGER
array = [

    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]

]

# Displaying "array"
print()
print("Array BEFORE Appending New Item")
print()

for x in array:

    print(x)

print()

# Function with identifier name "append_elements"

# In this function, we need to pass:
# array,
# index_row
# index_col
# the value
def append_element(array, row_to_add):

    array.append(row_to_add)

# Making a new row
new_row = [10, 2, 1]

# Calling Function
append_element(array, new_row)

# Displaying "array" after "appending" element
print("Array AFTER Appending New Item")
print()

for x in array:

    print(x)

```

#### Method 2.2: Using the "*.append()*" function at specific locations

```python

# Appending Elements at Specific Location

# DECLARE array: ARRAY[] OF INTEGER
array = [

    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]

]

# Displaying "array"
print()
print("Array BEFORE Insering New Item")
print()

for x in array:

    print(x)

print()

# "Appending" new element directly
array[0].append(99)

# Displaying "array" after "appending" new valeu

print()
print("Array AFTER Appending New Item")

for x in array:

    print(x)

```

>[!info]
>In this case, it will append the new value on the **first** *row*

>[!note]
>Some of you might have noticed "*Array[]*" $\Rightarrow$ "*No Size*"
>This is because the size is... "*dynamic*".
>- I do not know how to explain it but man, it changes the number of columns

### Method 2: Another way to use the "*.append()*" function is to let the user enter data into the array.

```python

# User Appends Element into Array

# DECLARE array: ARRAY[] OF STRING
array = []

# Function with identifier name "user_insert_value"
def user_insert_value():

    # Ask the user to input the number of rows
    num_of_rows = int(input("Please Enter Number Of Rows: "))

    # Ask the user to input the number of columns
    num_of_cols = int(input("Please Enter Number Of Columns: "))

    # Adding data into 2D-Array
    for x in range(num_of_rows):

        # Array "row" will keep the values in each row
        row = []

        # Steps through the number of columns
        for y in range(num_of_cols):

            # Asking the user to enter a value
            value = input("Enter Value At Position [ " + str(x + 1) + " : " +  str(y + 1) + " ] : ")

            # Adds the value to the array "row"
            row.append(value)

        # Adds the value to to original array "array"
        array.append(row)

# Calling Function
user_insert_value()

# Displaying Array
print()
print("Array AFTER Adding Values")
print()

for x in array:

    print(x)

```

# Deleting Elements From A 2D-Array

## Popping Elements From 2D-Array

>[!warning]
>The "*.pop()*" function will remove the last element

>[!info]
>To "*pop*" an element from the array; we use:
>```python
>array.pop()
># Where:
># "array" is our array
># NOTE: No values are passed into the function as it needs to remove the last item... Obviously!

```python

# DECLARE vehicles: ARRAY[3:2] OF STRING
vehicles = [

    ["RX-7", "H2R"],
    ["SR-71", "USS Princeton"],
    ["Bus", "Boat"]

]

# Displaying Array "vehicles"
print()
print("Array BEFORE Changes")
print()

for x in vehicles:

    print(x)

# Removing last ROW of array "vehicles"
vehicles.pop()

# Displaying Array "vehicles" after removing last row
print()
print("Array AFTER Changes")
print()

for x in vehicles:

    print(x)

```

## Removing Element From 2D-Array

### Method 1: Removing a **specific** value from the **entire** 2D-Array

```python

# Removing a specific value from entire 2D-Array

# DECLARE array: ARRAY[2:2] OF INTEGER
array = [

    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]

]

# Function with identifier name "remove_value"
def remove_value(array, value_to_remove):

    # Making Another Array

    # new_array = [[checks each value in "one" row] check for every other row]
    updated_array = [[x for x in row if x != value_to_remove] for row in array]

    # Returns the new array "new_array"
    return updated_array

# Displaying array
print()
print("Array BEFORE Removing Value")
print()

for x in array:

    print(x)

# Calling Function
new_array = remove_value(array, 5)

print()
print("Array AFTER Removing Value")
print()

for x in new_array:

    print(x)

```

## Clearing A 2D-Array

>[!warning]
>The "*.clear()*" will remove **all** elements from array

>[!info]
>To "clear" an array; we use:
>```python
>array.clear()
># Where:
># "array" is our array

```python

# Clearing A 2D-Array

# DECLARE : ARRAY[3:3] OF STRING
brands = [

    ["McDonalds", "KFC", "Pizza Hut"],
    ["Porsche", "Mazda", "Toyota"],
    ["Lockheed", "Boeing", "Airbus"],
    ["Body&Soul", "Supreme", "Nike"]

]

print()

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

# Socials

- [**Instagram**](https://www.instagram.com/s.sunhaloo/)
- [**YouTube**](https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg)
- [**GitHub**](https://www.github.com/Sunhaloo)

---

S.Sunhaloo
Thank You!