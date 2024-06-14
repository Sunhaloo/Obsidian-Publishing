---
Alias: Arrays in C
Tag: C, basics, 1D-Array, 2D-Array
Author: S.Sunhaloo
Type: Arrays ( 1D / 2D )
Date: 2024-03-19
Status: HOLD
---

## List of Contents

- [[Arrays - C#Little Introduction to Arrays | Little Introduction to Arrays]]

## One Dimensional Array

- [[Arrays - C#One Dimensional Arrays ( 1D-Arrays ) | One Dimensional Arrays ( 1D-Arrays )]]
- [[Arrays - C#Creating 1D-Arrays | Creating 1D-Arrays]]
- [[Arrays - C#Displaying 1D-Arrays | Displaying 1D-Arrays]]
	- [[Arrays - C#Method 2 Displaying with a Loop | Displaying Array with Loops]]
- [[Arrays - C#Adding Elements into 1D-Arrays | Adding Elements into 1D-Arrays]]
	[[Arrays - C#"Inserting" Elements into 1D-Array | "Inserting" Elements into 1D-Array]]
	[[Arrays - C#"*Appending*" Elements into 1D-Array | *Appending*" Elements into 1D-Array]]
- [[Arrays - C#Deleting Elements From 1D-Arrays | Deleting Elements From 1D-Arrays]]
	- [[Arrays - C#"*Popping*" Element From 1D-Array | *Popping*" Element From 1D-Array]]
	- [[Arrays - C#"*Removing*" Element From 1D-Array | *Removing*" Element From 1D-Array]]

---

## Two Dimensional Array

- [[Arrays - C#Two Dimensional Arrays ( 2D-Arrays ) | Two Dimensional Arrays ( 2D-Arrays )]]
- [[Arrays - C#Creating 2D-Arrays | Creating 2D-Arrays]]
- [[Arrays - C#Displaying 2D-Arrays | Displaying 2D-Arrays]]

---

### My Links

- [[Arrays - C#Socials | Links to Socials]]

---

>[!note] Python!
>So I learned Python first because... *Fuck Off*! Don't @ me.
>
>I will also be writing the Equivalent Python Code.
>The route that I took `Python` $\rightarrow$ `C` is common ( *I think* ). Hence, that is why I will be also including Python Codes; so that someone who already have done Python can have a better understanding of the C Codes.
>>Also I like writing Python Codes!

---

# Little Introduction to Arrays

So arrays or *lists* are basically that: **lists** ( *formally known as Data Structures* 🤓 ) that holds the **same** data type.
Think about a single row **or** / **and** columns in an Excel Documents.

For more information about Arrays head over to [[Arrays, Tuples, Sets - Python#What is an Array/List?| Arrays in Python]] or Google, YouTube University or even ChatGPT.

>Remember Boys ( *and Girls* ), we use ChatGPT for information gathering / learning and **not** *cheating*!
>No for real, I hate fucking cheaters, if there was a way to ban people like you ban them in games; I would gladly press the <button>Report</button> Button ( *$\Leftarrow$ an actually button - like the HTML button tag ).

Yeah so lets get started with coding because I want to actually code some shit instead of me typing this; I know I wasted a bunch of time saying this... GO FUCK YOURSELF!

---

# One Dimensional Arrays ( 1D-Arrays )

## Creating 1D-Arrays

So the code below $\downarrow$ will show you how to create 1D-Arrays.

>[!tip] Usage
>Here is the format of a 1D-Array
>```
>DataType array_name[] = {value1, value2, value3, ...};
>
>```

### 2 Ways of Making an Array

>Refer to **comments** inside the code for explanation!

```C

// Include standard input / output header
#include <stdio.h>

int main()

{

  // First Method to Declare and Initialise an Array
    // Normally used when we know the values that will go into the array
  // DECLARE ARRAY numbers[4]: INTEGER
  int numbers[] = {1, 2, 3, 4, 5};
  
  // Second Method to Declare and Initalise an Array
    // This method is used when we only know the Size of the array
  // DECLARE ARRAY characters[4]: CHAR
  char characters[5];

  // We can then, later, come back to insert the values as so:
  characters[0] = 'a';
  characters[1] = 'b';
  characters[2] = 'c';
  characters[3] = 'd';
  characters[4] = 'e';

  return 0;

}

```

## Displaying 1D-Arrays

So as you know our arrays have something call "*index*". Basically the **first** value is at **index** *0*. Take a look below $\downarrow$

- Mark-up of a simple 1D-Array

| Index | Contents |
| ----- | -------- |
| 0 | 44 |
| 1 | 55 |
| 2 | 16 |
| 3 | 7 | 
| 4 | 3 |

>I like Formula 1, especially if Merc and / or Lewis Hamilton is Winning.

So there are a few ways to display the an array in C

### Method 1: Displaying values individually

```C

// Include standard input / output header
#include <stdio.h>

int main()

{

  // DECLARE ARRAY numbers[4]: INTEGER
  int numbers[] = {1, 2, 3, 4, 5};

  // Output the values of array `numbers` ( individually )

  printf("\nNumbers Array\n");
  printf("%d", numbers[0]);
  printf("\n%d", numbers[1]);
  printf("\n%d", numbers[2]);
  printf("\n%d", numbers[3]);
  printf("\n%d", numbers[4]);

  return 0;

}

```

This is normally used to print out single values from an array. As you can see from the above $\uparrow$ code; it's not that efficient to write every single index of the array. Because what are you going to do if the array has over a 1000 index? Cry! I bet so!

### Method 2: Displaying with a Loop

```C

// Include standard input / output header
#include <stdio.h>

int main()

{

  // DECLARE ARRAY intials[4]: INTEGER
  int initials[] = {'S', 'U', 'S', 'S', 'Y'};

  // Output the values of array `initials` ( using a `for` loop )

  // DECLARE i: INTEGER
    // In this case we have declared the counter `i` inside the for loop itself
    // Actually the best / main way to create counter is by doing it within the `for` loop itself
  for(int i = 0; i < 5; i += 1){
    // Displaying Characters on Different Lines
    printf("\n%c", initials[i]);
  }
  
  printf("\n\n");

  for(int i = 0; i < 5; i++){
    // Displaying all Characters on Same Line
    printf("%c", initials[i]);
  }

  return 0;

}

```

This is the better way of displaying an array.
In the code above $\uparrow$; you can see that there are 2 `for` loops.
The first one is used to display the contents on **separate** lines, while the other will display the contents on the **same** line.

In addition, You **cannot** use the same counter `i` for both.
But you say yourself, you just did you dogshit little liar!.
Brother take a look again; I *re-declared* the counter `i`

#### Equivalent Python Code

```python

initials = ['S', 'U', 'S', 'S', 'Y']

# Display on Separate Lines
for x in intials:
	print(x)

# Display on Same Line
for x in intials:
	print(x, end="")

```

### Method 3: Using [[C Tips#Calculate the Size of Arrays ( Not Length of Array ) | sizeof()]] Function to Display Array

We are going to be using the `sizeof()` Function. If you do not know what this does, then head over to [[C Tips#Calculate the Size of Arrays ( Not Length of Array ) | How to Calculate the Size of Array - Not the Length]]

```C

// Include standard input / output header
#include <stdio.h>

int main()

{

  // DECLARE ARRAY intials[4]: INTEGER
  int initials[] = {'S', 'U', 'S', 'S', 'Y'};
  // DECLARE ARRAY prices[3]: INTEGER
  double prices[] = {12.50, 9.99, 449.99, 10.00};

  // Display the size ( like actual size in Bytes ) each array

  // Size of Array `initials` in Bytes
  printf("\nSize of Array `initials` = %ld Bytes", sizeof(initials));
  printf("\nSize of Array `prices` = %ld Bytes\n", sizeof(prices));

  // Use `sizeof()` Function to Display Arrays `initials` and `prices`

  for (int x = 0; x < sizeof(prices) / sizeof(prices[0]); x++) {
    printf("\n%0.2lf", prices[x]);
  }

  return 0;
}


```

>[!info]-
>Can use this method if you do **not** know the size of the array!
>I like using this method!

## Adding Elements into 1D-Arrays

### "Inserting" Elements into 1D-Array

Will add elements into a given position / index.

But there are some extras in this code ( *insert meme add a little spice to it* ). So amma explain it like the good person that I am ( *am not* ).

This code is taken from a [video](https://www.youtube.com/watch?v=nIJvKd5I1cY) by Portfolio Courses

```C

// Include standard input / output header
#include <stdio.h>

int main()

{ 

  // DECLARE ARRAY array[99]: INTEGER
  // Big Number; so that user can enter a lot of elements
  int array[100];

  // DECLARE array_size: INTEGER
  int total_values;
  // Ask the user to enter total amount of values that will be stored
  printf("\nPlease Enter Amount of Values to Store: ");
  scanf("%d", &total_values);

  // Ask the user to enter values into array
  printf("\n\nEnter Values into Array Below\n");
  // DECLARE i: INTEGER
  for(int i = 0; i < total_values; i++){
    printf("array[%d] = ", i);
    scanf("%d", &array[i]);
  }

  // Display the Array
  printf("\n\nDisplaying Array");
  // DECLARE j: INTEGER
  for(int j = 0; j < total_values; j++){
    printf("\narray[%d]: %d", j, array[j]);
  }
  
  // DECLARE insert_value: INTEGER
  int insert_value;
  // DECLARE insert_index: INTEGER
  int insert_index;

  // Allow the user to input another value at
  printf("\n\nInsert Your Value\n");
  // Ask user to enter index of value to insert
  printf("Please Enter The Position To Insert Value: ");
  scanf("%d", &insert_index);
  // Ask user to enter value to insert
  printf("Please Enter The Value To Insert: ");
  scanf("%d", &insert_value);
  
  // Swap Values to make space for new value
  // We have space at the end of last value, hence
    // move all value to the right until desired index is found
  for(int x = total_values; x > insert_index; x--){
    // Swap Values
    array[x] = array[x - 1];
  }

  // Add the value to the desired location
	  // This is how "Dynamic Memory Allocation" looks like
  array[insert_index] = insert_value;

  // Increase the total values in array
  total_values++;

  // Output Array Again
  printf("\n\nDisplaying Array");
  // DECLARE z: INTEGER
  for(int z = 0; z < total_values; z++){
    printf("\narray[%d]: %d", z, array[z]);
  }

  return 0;

}

```

#### Equivalent Python Code

I am going to write it as similar to the above code.

> I have my ways of writing Python Code, but I am just showing you the difference. Thus, need to mimic the above code as similar as possible.

```Python

# DECLARE ARRAY array[99]: INTEGER
array = []

print()

# DECLARE total_values: INTEGER
# Ask the user to enter the number of elements in array
total_values = int(input("Please Enter The Number of Elements to be Stored: "))

print("Insert Values Into Array")
print()
# Insert Values
for x in range(total_values):
    user_values = int(input(f"array[{x}]: "))
    array.append(user_values)

print()
print("Displaying Array")
print()

# Display Array
# DECLARE i:INTEGER
# DECLARE y:INTEGER
for i, y in enumerate(array):
    print(f"array[{i}]: {y}")

print()

# DECLARE insert_index: INTEGER
# Ask the user to enter the position to insert value
insert_index = int(input("Please Enter The Position To Enter Value: "))

# DECLARE insert_value: INTEGER
# Ask the user to enter value to add to array
insert_value = int(input("Please Enter The Value to Insert: "))

# Insert Value in Array
# ONE FUCKING LINE
# AGAIN ONE FUCKING LINE
array.insert(insert_index, insert_value)

print()

# Display Array Again
# DECLARE j:INTEGER
# DECLARE z:INTEGER
for j, z in enumerate(array):
    print(f"array[{j}]: {z}")

```

>Even though we just used the `insert()` function to insert the *user's value* at the correct position.
>There is no knowledge ( *say that like the meme* ) and we **just** use it without ever taking a guess how it works in the background.
>Heck, even I do **not** know how it works!

### "*Appending*" Elements into 1D-Array

This code $\downarrow$ will show you how to insert an element into an array at the **end** of an array.

```C

// Include standard input / output header
#include <stdio.h>

// FUNCTION dis(DECLARE array[]: INTEGER, DECLARE size: INTEGER)
void display(int array[], int size)

{
  // Displays any array
  for(int i = 0; i < size; i++){
    printf("\nIndex = %d | Value: %d", i , array[i]);
  }
}

int main()

{

  // DECLARE size_array: INTEGER
  int size_array;

  // Ask the user to enter the size of array
  printf("\nPlease Enter The Size of Array: ");
  scanf("%d", &size_array);

  // DECLARE ARRAY intials[]: INTEGER ( user will be ask the enter the size of array )
  // NOTE: Declaring AFTER getting the `size_array` from the user.
    // This is because C, Yeah C, Memory Management and stuff.
    // This is big men / chad toy now, not Python, we need to be one with the computer.
  int initials[size_array];

  printf("\nSize of Array: %d", size_array);

  printf("\n");

  // Ask the user to enter the the elements in array
  // DECLARE counter: INTEGER
  for(int counter = 0; counter < size_array; counter++){
    printf("\nPlease Enter Elements: ");
    scanf("%d", &initials[counter]);
  }

  // Display the Array using Function `display`
  display(initials, size_array);
  
  printf("\n");

  return 0;
}

```

Here are some explanation:
1. The first thing that we ( *more like "I"* ) did, is create a function called `display` to display our ( *can also display any array* ) array. We need to pass the array name and the size of the array; which were both in this case `initials` and `size_array` respectively.

2. Then we need to ask the user to enter:
	- Size of Array
	- The Elements ( *that will go inside the array* )

3. After asking the Size and Elements that will go inside of our array, We then use the for loop to enter the elements given by the user into the array with each incrementing counter `counter` by 1 until the limit ( *here the limit is the size of array* ) is reached.

>[!note]-
>If we already had values in the array; we could use the function [[C Tips#Calculate the Size of Arrays ( Not Length of Array ) | `sizeof()`]] to find the size of the array like so:
>- `size_array = sizeof(initials) / sizeof(initials[0]`

#### Equivalent Python Code

>To be honest, I much prefer to write Python Codes than C, but the **SPEED** of C is soooooooo much better than Python.

I normally write the array in the very **first** line. This is because look at the above $\uparrow$ code, I declared the `size_array` first then asked the user to enter its value. Finally, we use the array as normally. 

>But if I was actually writing Python Code; I would structure it like this:
>- All declaration like
>	- Globals
>	- Arrays
>	- Constants
>- User input
>But then again I have not written many code, just some algorithms like [[Binary Search - Python#Example 1 Complete Code for 1D-Array| binary search]] and other.

```python

print()
# Ask the user to enter the size of array
array_size = int(input("Please Enter The Size of Array: "))

# DECLARE ARRAY array[array_size]: INTEGER ---> User Will Give The Size
array = []

print()

# Loop to iterate through array
for x in range(array_size):

    # Ask the user to enter elements / values into array
    # DECLARE user_input: INTEGER
    user_input = int(input("Please Enter A Value: "))
    
    # Appends the user value to array
        # Append ---> The value will added will always go to the last index of array
    array.append(user_input)

print()

# Output Array
for i, y in enumerate(array):

    print(f"Index: {i} | Value: {y}")

```

## Deleting Elements From 1D-Arrays

### "*Popping*" Element From 1D-Array

The code below $\downarrow$ will remove the **last** element in the array ( *just like the [[Arrays, Tuples, Sets - Python#Popping Element From 1D-Array| `pop()`]] Function* ).

Little Explanation: because of *memory management*, and little to *no abstraction*, we need to remove the value ourselves.

Hence, we create a variable that will hold the removed value and then **decrease** the size of the array by 1.

Thus, we get this code below inspired by the the `pop()` function in Python.

```C

// Include standard input / output header
#include <stdio.h>

// FUNCTION display(DECLARE ARRAY a[4]: INTEGER, DECLARE size: INTEGER)
void display(int a[], int size)

{

	// Output The Array
	// DECLARE i: INTEGER
	for(int i = 0; i < size; i++){
		printf("\nIndex: %d | Value: %d", i, a[i]);
	}

	printf("\n");

}

int main()

{

	// DECLARE ARRAY array[4]: INTEGER
	int array[] = {1, 2, 3, 4, 5};
	// DECLARE array_size: INTEGER
	int array_size = sizeof(array) / sizeof(array[0]);

	// Call Function `display` to Display Array
	printf("\nOriginal Array\n");
	display(array, array_size);

	// Remove the Last Value from Array
	// DECLARE value_removed: INTEGER
	int value_removed;

	// Removing Last Value
	value_removed = array[array_size - 1]; // Where (array_size - 1) is the INDEX of Last Value
	// Decrease size of array by 1
	array_size--;
	
	// Display the Array Again
	printf("\nModified Array\n");
	display(array, array_size);

	return 0;

}

```

#### Equivalent Python Code

```Python

# FUNCTION display(DECLARE ARRAY a[4]: INTEGER)
def display(a):

    print()

    # DECLARE x: INTEGER
    # DECLARE index: INTEGER
    for index, x in enumerate(a):
        print(f"Index: {index} | Value: {x}")

    print()

# DECLARE array[4]: INTEGER
array = [1, 2, 3, 4, 5]

# Display Original Array
print()
print("Original Array")

# Calling Function `display` to Display Array
display(array)

# Remove last value from array
# Using `pop()` Function
# Again ONE FUCKING LINE
array.pop()

# Display Array Again
print("Modified Array")
display(array)

```

### "*Removing*" Element From 1D-Array

Remove a specific value at a specific location in the array.

Again, this is inspired by the `remove()` Function in Python.

```C

// Include standard input / output header
#include <stdio.h>

// Array's Maximum Capacity
#define max_size 100
// FUNCTION display(DECLARE array[]: INTEGER, DECLARE array_size: INTEGER)
void display(int array[], int array_size)

{

  // Output Array
  // DECLARE i: INTEGER
  for(int i = 0; i < array_size; i++){
    printf("\nIndex: %d | Value: %d", i, array[i]);
  }

  printf("\n");

}


int main()

{ 

  // DECLARE ARRAY numbers[100]: INTEGER
  int numbers[max_size];
  // DECLARE total_values: INTEGER
  // Use to keep track of numbers / "things" in the array
  int total_values;

  // Ask the user to enter the number of elements in array
  printf("\nPlease Enter The Number of Elements To Be Added: ");
  scanf("%d", &total_values);
  
  // Ask the user to input values into array in range of `total_values`
  for(int j = 0; j < total_values; j++){
    printf("\nPlease Enter Value To Add In Array: ");
    scanf("%d", &numbers[j]);
  }

  // Display Original Array by Calling Function `display`
  printf("\n\nOriginal Array");
  display(numbers, total_values);

  // DECLARE find_index_delete: INTEGER
  int find_index_delete;

  // Ask the user to enter the index / value to delete
  printf("\n\nPlease Enter The Index To Delete: ");
  scanf("%d", &find_index_delete);
  
  // DECLARE x: INTEGER
  for(int x = find_index_delete; x < total_values; x++){
    numbers[x] = numbers[x + 1];
  }
  // Decrease the size of array
  total_values--;

  // Display Modified Array by Calling Function `display`
  printf("\n\nModified Array");
  display(numbers, total_values);

  return 0;

}

```

As you can see, we are asking the user to enter the **index** of the value that we want to delete.
Compared to [[Arrays, Tuples, Sets - Python#Removing Element From 1D-Array| `remove()`]] Function in Python which will delete the **value** entered by the user.

The rest is similar to the code above; like we have a Function `display` that will display our array... I do not think I need to say more.

# Two Dimensional Arrays ( 2D-Arrays )

Now we are going to move onto 2 Dimensional Arrays.

Here is a little analogy that I came up;

- 1 Dimensional Arrays are like *ToDo* lists or a simple list of things or even a text file ( *that is why we call it **lists**; could also say that we only move in the x **or** y axis* ).
- 2 Dimensional Arrays are like *Excel Sheets*, because we have a matrix / grid of "*things*" ( *in this case we can both move in x **and** y axis* )

>I think the above $\uparrow$ explanation is shit; I mean really shit. But I understand it.

## Creating 2D-Arrays

Below we are going to create some simple 2D-Arrays

```C

// Include standard input / output header
#include <stdio.h>

int main()

{

  // First Method: Declare and Initialise 2D-Array
  // DECLARE ARRAY numbers[1][4]: INTEGER
  int numbers[2][5] = {{1, 2, 3, 4, 5}, {6, 7, 8}};
  
  // Second Method: Declare 2D-Array ONLY
  // DECLARE ARRAY id[4][4]: STRING
  char id[5][5];

  // We can then later populate the array like so:
    // In this case we only filled up the first Row
  id[0][0] = 'F';
  id[0][1] = 'U';
  id[0][2] = 'U';
  id[0][3] = 'C';
  id[0][4] = 'K';
  id[0][5] = 'S';

  return 0;
}

```

## Displaying 2D-Arrays

This will require more work. As you know that we basically have arrays inside of arrays. But then again there are different ways of accessing those values inside 2D-Arrays.

### Method 1: Displaying Values Individually

I am going to take the array `id` from the example above $\uparrow$. Because I think that you will understand it better.

```C

// Include standard input / output header
#include <stdio.h>

int main()

{

  // DECLARE ARRAY id[4][4]: STRING
  char id[5][5];

  // Inserting Values inside array at First Row ONLY
  id[0][0] = 'F';
  id[0][1] = 'U';
  id[0][2] = 'U';
  id[0][3] = 'C';
  id[0][4] = 'K';

  // Displaying Array `id`
  printf("\nID Array\n");
  printf("%c", id[0][0]);
  printf("%c", id[0][1]);
  printf("%c", id[0][2]);
  printf("%c", id[0][3]);
  printf("%c", id[0][4]);

  // Output an index that is empty
  printf("\nEmpty Index ( [0][5] ): %c <--- Should be Empty", id[0][5]);

  return 0;
}

```

### Method 2: Displaying with a Loop

Now, this is the real deal. We are going to print out all the values in the array.

>This is the one that we are going to be using the **most**! ( *I think ... No, I am sure* )

```C

// Include standard input / output header
#include <stdio.h>

int main()

{

  // DECLARE ARRAY numbers[1][2]: INTEGER
  int numbers[2][3] = {{1, 2, 3}, {5, 6, 7}};

  printf("\n Values of Array numbers\n");

  // Display Array with `for` Loop
  // DECLARE i: INTEGER
  for(int i = 0; i < 2; i++){
	// DECLARE j: INTEGER
    for(int j = 0; j < 3; j++){

      // Output Values of Array
      printf("\nRow: %d Column: %d Value: %d", i, j, numbers[i][j]);

    }
  };

  printf("\n\n");

  return 0;
}

```

## Array of Strings ( 2D-Array )

So as you already know by now if you have been following; C does **not** have `string` datatypes.

Hence, we use array of characters `char`.

Here is a little explanation of the code below $\downarrow$:

First of all, we have a `cars` array with *incomplete* size, then, we add, some cars names in it ( *innit right?* ).

We then want to add the value `Toyota Supra` in the first index of the array; if you take a look at the comments, you will see that we need to use the `strcpy()` function from the `<string.h>` library.

>Now, do not ask me why because I might break your face!
>Obviously I don't fucking know!

Then we simply display the array to the user ( *in a fashionable way 😉* ).

```C

// Include standard input / output header
#include <stdio.h>
// Include string header
#include <string.h>

int main()

{

  // DECLARE ARRAY cars: STRING
  // We have not yet really added a proper Array Size
  char cars[][15] = {"Toyota Corolla", "Mazda RX-7 FD", "W11"};

  // NOTE: We CANNOT Do this ( check line below )
  // cars[0] = "Toyota Supra";

  // To Perform this action
    // i.e insert "Toyota Supra" at index '0', we need to use the `strcpy` function
  strcpy(cars[0], "Toyota Supra");

  // Displaying the Array
  int size_array = sizeof(cars) / sizeof(cars[0]);

  printf("\nContents of Array\n");

  // DECLARE i: INTEGER
  for(int i = 0; i < size_array; i++){

    // Output Values of Array
    printf("\nIndex: %d | Value: %s", i, cars[i]);

  }

  return 0;
}

```

---

# Socials

- [**Instagram**](https://www.instagram.com/s.sunhaloo/)
- [**YouTube**](https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg)
- [**GitHub**](https://www.github.com/Sunhaloo)

---

S.Sunhaloo
Thank You!