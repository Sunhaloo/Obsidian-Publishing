---
Alias: Exception Handling In Python
Tag: python, basics
Author: S.Sunhaloo
Type: Exception Handling
Date: 2023-10-01
Status: Completed
---

## List of Contents:

- [[Exception Handling - Python#What is Exception Handling? | What is Exception Handling?]]
	- [[Exception Handling - Python#Code | Code]]
		- [[Exception Handling - Python#Python Language In Python | Python Language In Python]]
	- [[Exception Handling - Python#Examples | Examples]]
---

My Links

- [[Exception Handling - Python#Socials | Links to Socials]]

---

# What is Exception Handling?

So the thing about errors is that:

1. We ( especially *you* ) **hate** them
2. They are key to understanding ( what did you think I was about to say )

For example: what if in Maths and also Computer ( the subject as a whole ) you divide a number by 0? You would say that "*it can't be done! $\rightarrow$* Math Errors"... And you would be right.

It would cause the program to halt its operations.

Thus, if a user enters zero ( as the *divisor* ), we have to be able to tell the user:

- That we cannot divide by 0,
	- And the user after seeing the message needs to be able to enter another value

This is where **Exception Handling** comes into place. It will not interrupt the flow of the program by **not** ending the program after an error has occurred.

# Code

## [[Python Language | In Python]]

In Python, we can add *Exception Handling* by nesting our "*code*" ( program code ) inside of:

>[!tip] Usage
>```python
># Exception Handling
>try:
>except "Error"
>```
>Where "Error" is the type of error that is occurring.

## How to know the Type of Error?

You can run you code and make the error happen. After that you could see you errors.

In Python, the errors will be displayed as ( some of errors that happens in Python ):

1. TypeError
2. NameError
3. ValueError
4. ZeroDivisionError
5. Syntax
6. SyntaxError

## Examples

### Example 1: Division Calculator

```python

# Exception Handling

# Exception Handling
try:

    # Asking the user to enter a value as "numerator"
    numerator = float(input("Please Enter A Value(numerator): "))

    # Asking the user to enter another value as "denominator"
    dinominator = float(input("Please Enter A Value(dinominator): "))

# If users enter any characters other than "numbers"
except ValueError:

    print()
    print("Please Enter Numbers Only!")
    print()

# Function with identifier name "division"

# This function takes 2 arguments
def division(numerator, dinominator):

    # Exception Handling
    try:

        # Calculation
        division = numerator / dinominator

        # Displaying the value
        print()
        print("The answer is: " + str(division))
        print()

    # If user divides by zero
    except ZeroDivisionError:

        print()
        print("Cannot Divide By 0!")
        print()

# Calling Function
division(numerator, dinominator)

```

### Example 2: Showing the error

```python

# Exception Handling

# Exception Handling
try:

    # Asking the user to enter a value as "numerator"
    num1 = float(input("Please Enter A Value: "))

    # Asking the user to enter another value as "denominator"
    num2 = float(input("Please Enter A Value: "))

# If users enter any characters other than "numbers"
# "as e" will output the type of error
except ValueError as e:

    print()
    print("Please Enter Numbers Only!")
    print()

# "as e" will output the type of error
except NameError as e:

    print()
    print("Something went wrong")
    print()

# Function with identifier name "add"

# This function takes 2 arguments
def add(num1, num2):

    # Exception Handling
    try:

        # Calculation
        addition = num1 + num2

        # Displaying the value
        print()
        print("The answer is: " + str(addition))
        print()

    # "as e" will output the type of error
    except NameError as e:

        print()
        print("Something went wrong")
        print()

    # If user divides by zero
    # "as e" will output the type of error
    except Exception as e:

        print()
        print("Cannot Divide By 0!")
        print()

# Calling Function
add(num1, num2)

```

### Example 3: Finally

```python

# Exception Handling

# Exception Handling
try:

    print()
    print("This is a sentence")
    print()

finally:

    print()
    print("This will always execute!")
    print()

```

---

# Socials

- [**Instagram:**](https://www.instagram.com/s.sunhaloo/)
- [**YouTube:**](https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg)

---

S.Sunhaloo
Thank You!