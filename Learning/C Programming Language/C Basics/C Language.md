---
Alias: C Language/Basics
Tag: C, basics
Author: S.Sunhaloo
Type: Basics
Date: 2024-01-31
Status: Completed
---

## List of Contents

- [[C Language#What is C? | What is C?]]
	- [[C Language#Creator of C | Creator of C]]
- [[C Language#What can C do? | What can C do?]]

---

- [[C Language#How to comment in C | How to comment in C]]
- [[C Language#Simple C Boiler Plate | Simple C Boiler Plate]]
- [[C Language#Escape Sequence | Escape Sequence]]
- [[C Language#Data Types, Constants and Variables | Data Types, Constants and Variables]]
	- [[C Language#What Data Types are Available? | What Data Types are Available?]]
	- [[C Language#[Format Specifiers](https //www.youtube.com/watch?v=87SH2Cn0s9A&t=2296s) | Format Specifiers]]
	- [[C Language#Variables | Variables]]
	- [[C Language#Constants | Constants]]
- [[C Language#Arithmetic Operations | Arithmetic Operations]]
	- [[C Language#Addition $+$ | Addition]]
	- [[C Language#Subtraction $-$ | Subtraction]]
	- [[C Language#Multiplication $ times$ | Multiplication]]
	- [[C Language#Division $ div$ and Remainder of Numbers $ %$ | Division and Remainder]]
- [[C Language#User Inputs | User Inputs]]

---

### My Links

- [[C Language#Socials | Links to Socials]]

---

# What is C?

General Purpose computer programming language. Unlike [[Python Language | python]]; it requires a **compiler** like *GCC*, *Clang*.

- For C language we need to *re-compile* the code every time we make changes to the code.
	- This is why we get a `.exe` file after compiling.
- Python uses and **interpreter**, which simply means that the code is translated in *machine code* **line-by-line**

>[!note]
>Both translators have their benefits and drawbacks.
>**Interpreters** are used during the *writing* phase while **Compilers** a used to translate the whole code after the writing process has finished.
>Go check online for more information.

>[!warning]
>C is **not** an *Object Oriented Programming* language. Meaning that we cannot do OOP.
>Hence, we will need to use [C++](https://en.wikipedia.org/wiki/C%2B%2B)

## Creator of C

**Name:** [Dennis Ritchie](https://en.wikipedia.org/wiki/Dennis_Ritchie)
**Created At:** Bell Telephone Laboratories
**Created On:** 1972

# What can C do?

- Creating and maintaining IoT ( [Internet of Things](https://en.wikipedia.org/wiki/Internet_of_things) )
- Developing Compilers
- Created High Level Programming Languages, like:
	1. Python
	2. JavaScript

---

# How to comment in C

To comment a **single** line in C, we will use the symbol

>[!tip] Usage
>```C
>// This is where text goes
>```

To comment **multiple** line in C, we will use

>[!tip] Usage
>```C
>/* This is where text goes */
>```

## Simple C Boiler Plate

The code below is the simplest C code that I think has been written. It will display `Hello World` ( *what the fuck did you expect* ).

```C

// Basically need to be able to write most simple things
#include <stdio.h>

// Similar to Visual Basic where we have a "Sub Main()"
int main()

{

	// Outputs "Hello World" and places the cursor on a new line
	printf("Hello World\n");

	// Return 0 to indicate the the program executed successfully
	// Will return 1 if it failed
	return 0;

}

```


### What does each line means?

#### What does `#include <stdio.h>` means?

It is a [preprocessor](https://www.google.com/search?client=firefox-b-d&q=what+is+a+preprocessor) which tells the compiler to include this **library**.

But what does `#include` means?

*You dumb fuck, what does the word "include" means?*

- It will tell the preprocessor to *include* the content of a specified file.

What does `<stdio.h>` means?

It is the name of the **header** file to be included. `<stdio.h>` means *standard input/output header.

By including this library we get accessed to functions like `printf` and `scanf`.

>[!tip]
>The angle brackets `<` and `>` $\Rightarrow$ indicates that the file is a *standard* library header.

>Do I really need to explain the `printf` function?

What does `return 0` do?

It is there to check for any errors and will *return* `0` if a program executed successfully else it will *return* `1`

>[!warning]
>You need to write `return 0;` at the end or it will not work.

# Escape Sequence

- It is a character **combination** consisting of a backslash `\` followed by a *letter* or *combination of digits*.
- Specifies actions within a line or string of text

Here are some **Escape Sequence** characters:

| Escape Sequence | Meaning |
| --------------- | ------- |
| \a | Alarm |
| \b | Backspace |
| \f | Form Feed |
| \n | New Line |
| \r | Carriage Return |
| \t | Tab |
| \v | Vertical Tab |
| \\ | Backslash |
| \' | Single Quote |
| \" | Double Quote |
| \? | Question Mark |
| \nnn | Octal Number |
| \xhh | Hexadecimal Number |
| \0 | Null |

# Data Types, Constants and Variables

## What Data Types are Available?

### Integers ( `long int` )

4 Bytes ( -2,147,483,648 to +2,147,483,648 )

- Use `%d` or `%i` to print *integers*

```C

// Integer Data Types
int number_1 = 63;
int num_1 = 46;
int array_length = 5;

```

### Unsigned Integers ( `unsigned long int` )

4 Bytes ( 0 to 4,294,967,295 )

- Use `%u` to print *unsigned integers*

```C

// Unsigned Integer Data Types
unsigned int unsigned_int = 4294967295;

```

### Short Integers

2 Bytes ( -32,768 to +32,768 )

- Use `%d` or `%hd` to print *integers*

```C

// Short Integer Data Types
short int short_integer_half_size_of_int = 28107;
// OR
short short_integer_half_size_of_int = 28107;

```

### Unsigned Short Integers

2 Bytes ( 0 to +65,535 ) ( *kinda max number + positive only* ) $\Rightarrow$ Doubling our Positive Number while using the *unsigned short integer* data type.

- Use `%d` or `%uhd` to print *integers*

```C

// Unsigned Short Integer Data Types
unsigned short int max_unsigned_short_int = 65535;
// OR
unsigned short max_unsigned_short_int = 65535;

```

### Long Long Integer

8 Bytes ( +9 Quintillion to -9 Quintillion  )

- Use `%lld` to print *long long integer*

```C

// Long Long Integer Data Types
long long int nine_quintillion = 9223372036854775807;

```

### Unsigned Long Long Integer

8 Bytes ( 0 to +18 Quintillion ) ( *kinda max number + positive only* ) $\Rightarrow$ Doubling our Positive Number while using the *unsigned long long integer* data type.

- Use `%llu` to print *unsigned long long integer*

```C

// Unsigned Long Long Integer Data Types
unsigned long long int eighteen_quintillion = 18446744073709551616;

```

>[!note]
>We **rarely** use *long long integers* and mostly use "*normal*" *integers* because it is unnecessary and will slow down the code.

### Floating Point Numbers

4 Bytes ( 32 Bits of precision )

- Use `%f` to print *floats*.

```C

// Floating Point Numbers ( Float Data Type )
float price = 502.95;
float insurance = 1000.99;

```

### Double ( `long double` )

8 Bytes ( 64 Bits of precision ).

Basically the same as floating point numbers but has much better accuracy / precision ( *15 - 16 digits compared to 6 - 7 digits* ).

- Use `%lf` to print *doubles*.

```C

// Double Data Types
double money = 23.98312334266;
double pressure_level = 45.891316639;

```

>[!tip] Remember
>C will display all the decimal numbers for float and double.
>We can use a value ( *decimal number* ) to tell how many digits to display / output on the screen.
>For Example:
>- `0.15%f` and `0.15%lf` will display 15 digits for both *floats* and *doubles*.

### Char ( `signed Char` )

1 Byte  ( -128 to +127 ).

- Use `%c` to print *chars*.

```C

// Char Data Types
char grade = 'A';
char Level = 100;

```

>[!note]
>We can also use `%c` or `%d` for Chars.
>If we use, `%d` on `Level`, we will get "**100**". But if we use `%c` we will get "**d**".
>Refer to ASCII Table.
>![[ASCII Table.webp]]

### Unsigned Char

1 Byte ( 0 to +255 ) ( *kinda max number + positive only* ) $\Rightarrow$ Doubling our Positive Number while using the *char* data type.

>[!warning]
>To print / output *unsigned char*, we can only use `%d`

```C

// Char Data Types
unsigned char grade = 'A';
unsigned char max_char = 255;

```

### String

>[!bug] Big NOTE
>We do **not** have the *string* data type in C!!! ( *insert shocking face here* )
>- This is because it is not a Computer Object Oriented Programming Language.
>	- Hence we have a substitute for *string* data types $\downarrow$

- Use `%s` to print *strings*.

```C

// "String" Data Types
char name[] = "Charles 'Perceval' Leclerc"
char car[] = "Mazda RX-7"

```

### Boolean

>[!warning] Note
>To be able to use the *boolean* data type, we need to include the library `<stdbool.h>`!

- Use `%d` to print *boolean*.

```C

// Do NOT forget about the boolean library
#include <stdbool.h>

// Boolean Data Types
bool update = true;
bool increase_temp = false;

```

---

## [Format Specifiers](https://www.youtube.com/watch?v=87SH2Cn0s9A&t=2296s)

This is the *place holder* that we need to be able to **display** over variables on the screen.

>I will be writing it as table ( *because FUCK YOU* ).

>[!note]
>This is **not** everything!!!

| Display | What to Write |
| ------- | ------------- |
| Char | %c |
| String | %s |
| Integer | %d |
| Float | %f |
| Double | %lf |

>[!warning]
>C is **not** like Python.<span style="color: red;"> We need to <strong>declare</strong> our variables and constants</span>
>>Hence you could say that C is slower than Python in terms of typing speed.

## Variables

Again, "*What is a Variable?*" A variable is something / data that can change during the execution of a program.

In C; It is a **allocated space** in memory to store a *value*.

### Examples

Here we are going to write some variables, one will be written on 2 lines while the other will be written on the same line ( *because I kinda have OCD, I need to write this, then the notes will be **aESthEtIcs** (⊙_⊙;)* ).

>Again remember we **need** to *declare* our stuff and do not forget the `;` semi-colon at the end!

#### Integer Data Type

```C

// Declaration
int x;

// Initialisation
x = 44;

// Output the variable
printf("x = %d", x);

```

```C

// Declaration and Initialisation
int x = 47;

// Output the variable
printf("x = %d", x);

```

#### Floating Pointer Number ( *basically decimal numbers* ) Data Type

```C

// Declaration and Initialisation
float price = 403.75;

// Output the variable
printf("Price = %f", price);

```

>[!success]-
>I think I like the **second** one better 😎! Because we only need one `;`

#### Char Data Type

```C

// Declaration and Initialisation
char grade = "A";

// Output the variable
printf("Grade: %c", grade);

```

#### Substitute for String Data Types

We need to make an array. To make an array, we can use the following symbol `[]` ( *similar to Python but not really, you will see what I mean* ).

```C

// Substitute for String Data Type
// Array of characters
int name[] = "Jimmy Broadbent";

// Output the variable
printf("My name is %s", name);

```

>[!tip] Remember
>`%d`, `%f`, `%c`, `%s` are known as **place holders**
>>For the moment just remember them by heart.

## Constants

As we already know, *constants* cannot be changed; even during the *execution* of the program.

For example, lets create the constant for $\pi$

```C

// Constant

const float PI = 3.142;

```

If you try to change it to a different value like `PI = 69` ( *hehe* ). It will be an error saying `assignment of read-only variable 'PI'`.

>[!warning]- Note
>It is a good practice to write you *constants* **UPPERCASE**.
>Nevertheless, it will work even if you do *not* write in UPPERCASE.


# Arithmetic Operations

>[!note]-
>I think you will be able to understand the answers

## Addition $+$

Okay, I hope you know that is addition. Because if you do not, then what the fuck are you doing here.

```C

// Addition

	// Integers

    int add_num1;
    int add_num2;

    add_num1 = 3;
    add_num2 = 7;

    int int_addition;

    int_addition = add_num1 + add_num2;

	// Floats

    float add_num3;
    float add_num4;

    add_num3 = 3;
    add_num4 = 7;

    float float_addition;

    float_addition = add_num3 + add_num4;

	// Doubles

    double add_num5;
    double add_num6;

    add_num5 = 3;
    add_num6 = 7;

    double double_addition;

    double_addition = add_num5 + add_num6;

```

## Subtraction $-$

This is the *negative* ( *fuck off this is my notes I can write whatever the fuck I want* ) of addition.

```C

// Subtraction

	// Integers

    int sub1;
    int sub2;

    sub1 = 9;
    sub2 = 1;

    int int_sub_postive;
    int int_sub_negative;

    int_sub_postive = sub1 - sub2;
    int_sub_negative = sub2 - sub1;

	// Floats

    float sub3;
    float sub4;

    sub3 = 9;
    sub4 = 1;

    float float_sub_positive;
    float float_sub_negative;

    float_sub_positive = sub3 - sub4;
    float_sub_negative = sub4 - sub3;

	// Doubles

    double sub5;
    double sub6;
  
    sub5 = 9;
    sub6 = 1;

    double double_sub_positive;
    double double_sub_negative;

    double_sub_positive = sub5 - sub6;
    double_sub_negative = sub6 - sub5;

```

## Multiplication $\times$

This is multiplication, what is multiplication you ask? Again go fuck yourself because you are either too young for this or a complete and utter idiot ( *some might even say "sussy baka"* ).

```C

// Mutiplication

	// Integers

    int multiply1;
    int multiply2;
  
    multiply1 = 11;
    multiply2 = 44;

    int int_multiply;

    int_multiply = multiply1 * multiply2;

	// Floats

    float multiply3;
    float multiply4;

    multiply3 = 11;
    multiply4 = 44;

    float float_multiply;
  
    float_multiply = multiply3 * multiply4;

	// Doubles

    double multiply5;
    double multiply6;

    multiply5 = 11;
    multiply6 = 44;

    double double_multiply;

    double_multiply = multiply5 * multiply6;

```

## Division $\div$ and Remainder of Numbers $\%$

This is the *inverse* ( *again I can write whatever the fuck I want* ) of multiplication.

For the **remainder of numbers**; you will be mostly using them for finding if a number is an *even* or *odd* number.

>Obviously I am joking from the above $\uparrow$ note. Reader please stay here.

```C

// Division

	// Integers

	int div1;
	int div2;

    div1 = 2;
    div2 = 5;

    int int_div_big;
    int int_rem_big;
    int int_div_small;
    int int_rem_small;

    int_div_big = div2 / div1;
    int_rem_big = div2 % div1;
    int_div_small = div1 / div2;
    int_rem_small = div1 % div2;

	// Floats

	float div3;
	float div4;

    div3 = 2;
    div4 = 5;

    float float_rem_big;
    float float_div_big;
    float float_div_small;
    float float_rem_small;

    float_div_big = div2 / div1;
    float_rem_big = div2 % div1;
    float_div_small = div1 / div2;
    float_rem_small = div1 % div2;

	// Doubles

	double div5;
	double div6;

    div5 = 2;
    div6 = 5;

    double double_rem_big;
    double double_div_big;
    double double_div_small;
    double double_rem_small;

    double_div_big = div2 / div1;
    double_rem_big = div2 % div1;
    double_div_small = div1 / div2;
    double_rem_small = div1 % div2;

```

### Augmented Assignment Operators ( for quick arithmetic calculations )

Down below $\downarrow$ will be a list of *augmented assignment operators*.

```C

// Augmented Assignment Operators

int x = 12;

// Increment Addition

// First Method
x = x + 1;

// Second Method ( Similar to Python )
x += 1;

// Decrement Addition

// First Method
x = x - 5;

// Second Method ( Similar to Python )
x -= 5;

// Multiplication

// First Method
x = x * 2;

// Second Method
x *= 2;

// Division

// First Method
x = x / 10;

// Second Method
x /= 10;

// Remainder

// First Method
x = x % 4;

// Second Method
x %= 4;

```


# User Inputs

In Python, if we would like to take an **input** from the user, we would do:

```python

# DECLARE name: STRING
name = input("Please Enter Your Name")

# DECLARE age: INTEGER
age = int(input("Please Enter Your Age"))

```

Similar we will have to use an *in-built* function provided by the `<stdio.h>` header / library.

```C

// User Inputs

// Integers
int age;

printf("\nPlease Enter You Age: ");
scanf("%d", &age);

// Characters / String ( Remember we do NOT have strings )
char name[25];

printf("Please Enter Your Name: ");
scanf("%s", name);

```

>[!note]
>For *number* variables ( *I mean integers, floats, doubles...* ), do **not** forget the "$\&$" symbol in **front** of the variables.

>[!warning]
>The function `scanf()` will only **read** the input till the first *whitespace* / `<Space>`
>For Example:
>If I input `Goodnight Bitch`, and let say we have a variable called `goodnight`.
>If we were to output / *print* `goodnight`, the output would be:
>```console
>
>Goodnight
>
>```
>As you can see, it completely **ignores**, the "*Bitch*" part!
>>[!tip] Here comes `fgets()` to the Rescue!
>> To make it read **after** the *whitespace* / `<Space>`, check the sample code below $\downarrow$
>> ```C
>> 
>> // Characters / Strings
>> char name[25];
>>
>>printf("Please Enter Your Name: ");
>>fgets(name, 25, stdin);
>> 
>> ```
>> We will be covering this in more details later!

## `getchar()` Function

Look at the code below $\downarrow$:

```C

// Include standard input / output header
#include <stdio.h>

int main()

{
  // Declaration
  // DECLARE rows: INTEGER
  int rows;
  // DECLARE cols: INTEGER
  int cols;
  // DECLARE user_symbol: CHAR
  char user_symbol;

  // Ask the user to enter number of rows
  printf("\nPlease Enter The Number Of Rows: ");
  scanf("%d", &rows);
  // Ask the user to enter number of columns
  printf("Please Enter The Number Of Columns: ");
  scanf("%d", &cols);

  // Allows us to switch from input of Integers to Characters  
  getchar();

  // Ask the user to enter symbol to print / output
  printf("Please Enter The Symbol To Be Used: ");
  scanf("%c", &user_symbol);

  // Displaying the "image"
  for (int x = 1; x <= rows; x += 1) {
    for (int y = 1; y <= cols; y += 1) {
      printf("%c", user_symbol);
    }
    printf("\n");
  }

  return 1;
}

```

As you can see, this code will allows the user to display / make an *image* with any symbol.

### What is the `getchar()` Function?

It is used to read a single character from the standard input ( *i.e: Keyboard* ).
- Returns an Integer value, which represents the ASCII value of the character read.

#### Explanation for above $\uparrow$ code

When we are reading the 2 *integer* characters ( `rows` and `cols` ) entered by the user.
The entered integer is read **but** a the *newline character* is still in the buffer / memory.
But for **characters** ( *char* datatypes ) this is not the case; when the user enters his character. The *newline character* is immediately **consumed** and `scanf()` function reads it instead of waiting for a new character input.

Hence, when we go to input our symbol ( `user_symbol` ), again remember that we have 2 `int` we are waiting to input from the user; the **newline character** does **not** get destroyed. Hence, we are stuck waiting to input `user_symbol`.

>*newline* character in this case is when the cursor switches to the next line.

<li style = "color: lime">Solution</li>

Thus, we use the `getchar()` function, when switching input's datatype.

>I think you understand what I am trying to convey!

>[!tip]
>Good practice to **include** the `getchar()` function when you are **switching** between reading *integers* and *characters* to avoid unexpected behaviour due to *newline characters* in the input buffer.


# Logical Operators

Basically, **AND**, **OR** and **NOT** are called *logical operators*. Because they involves logical things.

AND Operator

| A | B | X |
| - | - | - |
| 0 | 0 | 0 |
| 0 | 1 | 0 |
| 1 | 0 | 0 |
| 1 | 1 | 1 |

OR Operator

| A | B | X |
| - | - | - |
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 1 |

XOR Operator

| A | B | X |
| - | - | - |
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 0 |

## Python Logical Operators

### Python `and` Operator

To be able to use the `and` operator in Python, we simply write `and`. That's it nothing more or less.

```python

# Ask the user to enter 2 numbers
num1 = int(input("Please Enter A Number: "))
num2 = int(input("Please Enter Another Number: "))

# Conditions
if (num1 == 5 and num2 == 5):

	print("You have guessed correctly!")

elif (num1 == 4 and num2 == 4):

	print("You are going to die")

```

### C `&&` ( AND ) Operator

Like to be honest, there must be a real reason that we are using `&&` instead of `and`... Let me go and find out.

>I could not find the answer. But I guess it was like something to do with **Assembly** or something
>Bruh, what the fuck man... **ASM** uses *AND*, *OR*, *XOR* and *NOT*. So why dafuq does C uses 2 fucking ampersand.

The Python code above $\uparrow$ will be converted to C down below $\downarrow$

```C

// Include standard input/output header
#include <stdio.h>

int main()

{

	// Declaration

	// DECLARE num1: INTEGER
	int num1;
	// DECLARE num2: INTEGER
	int num2;

	// Ask the user input his / her numbers

	// For `num1`
	printf("Please Enter A Number: ");
	scanf("%d", num1);

	// For `num2`
	printf("Please Enter Another Number: ");
	scanf("%d", num2);

	// Conditions
	if (num1 == 5 && num2 = 5){
		printf("You have guessed correctly!");
	}
	else if(num1 == 4 && num2 == 4){
		printf("You are going to die");
	}

	return 0;

}

```

### Python `or` Operator

Simple as the `and` operator but this one will be like with `or`

>Again, I will be writing a simple program in Python and then converting it into C.

```python

# Ask the user to enter the number of wheels of vehicle
# NOTE: Wheel can also be 0

wheels = int(input("Please Enter The Number Of Wheel: "))

# Conditions
if (wheels == 2 or wheels = 4):

	print()
	print("You Have A Land Vehicle!")
	print()

elif wheels = 0;

	print()
	print("You Probably Have A Boat!")
	print()

```

### C `||` ( OR ) Operator

Again, I do not know why the fuck we are actually using `||` ( *2 pipes* ) instead of just good-old regular `or`. If you have the answer, do let me know; my email is azmaan151003@gmail.com

The Python code above $\uparrow$ will be converted to C down below $\downarrow$

```C

// Include standard input / output header
#include <stdio.h>

int main()

{

	// Declaration

	// DECLARE wheels: INTEGER
	int wheels;

	// Ask the user to enter the number of wheels
	printf("Please Enter The Number Of Wheels: ");
	scanf("%d", wheels);

	// Conditions
	if(wheels = 2 || wheels = 4){

		printf("\nYou Have A Land Vehicle!\n");

	}
	else if(wheels = 0){

		printf("\nYou Probably Have A Boat!\n");

	}

	return 0;

}

```

### Python and C `!` ( NOT ) Operator

Even though both does not make any sense at all; but I can tell you than the **NOT** operator works just like in [[Python Language | Python]].

>Hence, I will only be writing for C code... I am very very very ***lazy***!

```C

// Include standart input / output header
#include <stdio.h>
// Include string manipulation header / library
#include <string.h>

int main()

{

	// Declaration

	// DECLARE name: STRING
	// NOTE: C Does not have STRING data type ---> Remember the array thing
	char name[25];

	// Ask the user to enter his name
	printf("\nPlease Enter Your Username: ");
	scanf("%s", name);

	// Conditions
	if(strcmp(name, "Deez_Nuts") != 0){
	
		printf("\nAccess Denied! Wrong Person\n");
	
	}
	else{
	
		printf("\nWelcome Deez_Nuts\n");
	
	}

	return 0;

}

```

>[!note]-
>Do not worry about the `<string.h>` for the moment, but I think you get the point of the program
>- Allows the user to enter his username
>	- Checks whether the username is equal to "*Deez_Nuts*"
>		- If so, outputs the message "*Welcome Deez_Nuts*"
>	- If username is **not** equal to "*Deez_Nuts*"
>		- Outputs the message "*Access Denied! Wrong Person*"

---

# Socials

- [**Instagram**](https://www.instagram.com/s.sunhaloo/)
- [**YouTube**](https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg)
- [**GitHub**](https://www.github.com/Sunhaloo)

---

S.Sunhaloo
Thank You!
