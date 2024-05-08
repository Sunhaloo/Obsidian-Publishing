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

1. We all **hate** them
2. They are key to understanding ( what did you think I was about to say "*Fuck Them*" well *Fuck You*! )

For example: what if in Maths and also Computer ( the subject as a whole ) you divide a number by 0? You would say that "*it can't be done! $\rightarrow$* Math Errors... And you would be right.

It would cause the program to halt its operations.

Thus, if a user enters zero ( as the *divisor* ), we have to be able to tell the user:

- That we cannot divide by 0,
	- And the user after seeing the message needs to be able to enter another value

This is where **Exception Handling** comes into place. It will not interrupt the flow of the program by **not** halting the program after an error has occurred.

## How to know the Type of Error?

You can run you code and make the error happen. After that you could see you errors.

Some errors that usually happens in ( *vanilla* ) Python are:

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
try:

    # DECLARE numerator: REAL
    # Asking the user to enter a value as "numerator"
    numerator = float(input("Please Enter A Value(numerator): "))

    # DECLARE dinominator: REAL
    # Asking the user to enter another value as "denominator"
    dinominator = float(input("Please Enter A Value(dinominator): "))

# If users enter any characters other than "numbers"
except ValueError:

    print()
    # Output this Message
    print("Please Enter Numbers Only!")
    print()

# FUNCTION division(DECLARE numerator: REAL, DECLARE dinominator: REAL)
def division(numerator, dinominator):

    # Exception Handling
    try:

        # DECLARE division: REAL
        # Calculation
        division = numerator / dinominator

        # Displaying the value
        print()
        print(f"The answer is: {division}")
        print()

    # If user divides by 0
    except ZeroDivisionError:

        print()
        # Output this Message
        print("Cannot Divide By 0!")
        print()

# Calling Function to `main` Program
division(numerator, dinominator)

```

### Example 2: Showing the error

```python

# Exception Handling
try:

    # DECLARE num1: REAL
    # Asking the user to enter a value as "numerator"
    num1 = float(input("Please Enter A Value: "))

    # DECLARE num2: REAL
    # Asking the user to enter another value as "denominator"
    num2 = float(input("Please Enter A Value: "))

# If users enter any characters other than "numbers"
# "as e" will output the type of error
except ValueError as e:

    print()
    # Output this Message
    print("Please Enter Numbers Only!")
    print()

# "as e" will output the type of error
except NameError as e:

    print()
    # Output this Message
    print("Something went wrong")
    print()

# FUCNTION add(DECLARE num1: INTEGER, DECLARE num2: INTEGER)
def add(num1, num2):

    # Exception Handling
    try:

        # DECLARE addition: INTEGER
        # Calculation
        addition = num1 + num2

        # Displaying the value
        print()
        print(f"The answer is: {addition}")
        print()

    # "as e" will output the type of error
    except NameError as e:

        print()
        # Output this Message
        print("Something went wrong")
        print()

    # If user divides by zero
    # "as e" will output the type of error
    except Exception as e:

        print()
        # Output this Message
        print("Cannot Divide By 0!")
        print()

# Calling Function to `main` Program
add(num1, num2)

```

### Example 3: `finally`

```python

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

- [**Instagram**](https://www.instagram.com/s.sunhaloo/)
- [**YouTube**](https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg)
- [**GitHub**](https://www.github.com/Sunhaloo)

---

S.Sunhaloo
Thank You!