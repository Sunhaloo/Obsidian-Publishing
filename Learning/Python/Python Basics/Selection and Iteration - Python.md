---
Alias: IF-CASE-WHILE-REPEAT
Tag: python, basics
Author: S.Sunhaloo
Type: Conditions / Statements
Date: 2023-10-01
Status: Completed
---

## List of Contents

- [[Selection and Iteration - Python#What is a Selection? | What is a Selection?]]
	- [[Selection and Iteration - Python#IF Statements | IF Statements]]
	- [[Selection and Iteration - Python#CASE Statements | CASE Statements]]

---

- [[Selection and Iteration - Python#What is an Iteration? | What is an Iteration?]]
	- [[Selection and Iteration - Python#Pre-Condition Loops | Pre-Condition Loops]]
		- [[Selection and Iteration - Python#While Loops | WHILE Loops]]
		- [[Selection and Iteration - Python#For Loops | FOR Loops]]
	- [[Selection and Iteration - Python#Post-Condition Loops | Post-Condition Loops]]
		- [[Selection and Iteration - Python#Repeat Until | REPEAT UNTIL]]

---

### Another Little Thing related to Loops

- [[Selection and Iteration - Python#Break Continue Pass | Break | Continue | Pass]]
	- [[Selection and Iteration - Python#Break | Break]]
	- [[Selection and Iteration - Python#Continue | Continue]]
	- [[Selection and Iteration - Python#Pass | Pass]]

---

My Links

- [[Selection and Iteration - Python#Socials | Link to Socials]]

---

# What is a Selection?

What is a **decision**? It is simply the action of deciding something after being asked a question.

In the same way, when designing a program; there are many times where we need to make a **decision**. A *decision* is also known as a **selection** in Computer Science.

We have 2 main type of "*selections*";

- [[Selection and Iteration - Python#IF Statements | IF Statements]]
- [[Selection and Iteration - Python#CASE Statements | CASE Statements]]

We use *these* $\uparrow$ again, to make a decisions. For example: If we present someone with a "*Construct Your Own Burger*" screen. The program will have to make decision after the user chooses his type of "*bread*" or he *exits* the program entirely.

# What is an Iteration?

An iteration is also defined as a **loop**. In programming, we need to repeat block of code many times. Thus, we have *loops* to the rescue. ( *no really thank that person who made them - fuck assembly language* )

Again we have 2 type of loops, but the are **different**. You see, there are:

1. **Pre**-Condition Loops
2. **Post**-Condition Loops

In the **Pre**-Condition Loop category, we have:

- [[Selection and Iteration - Python#While Loops | While Loops]]
- [[Selection and Iteration - Python#For Loops | For Loops]]

We normally used these when we *know* how many **times** we are going to *enter* the loop

In the **Post**-Condition Loop category, we have:

- REPEAT UNTIL Loops

This will be *executed* at **least once** and we use them when we do **not** *know* how many times we are going to enter loop.

---

# IF Statements

I am going to be honest with you ( *yes, the one reading this* ). This is not something that you grasp by reading; first of all you need to have your fundamentals. Thus, I will go directly to **simple** examples

## Example 1: Displaying a message after entering age

```python

# IF Statements

# DECLARE user_age: INTEGER
# Asking the user to input his age
user_age = int(input("Please Enter Your Age: "))

# If age is in equal and betwen 18 to 100
if user_age >= 18 and user_age < 100:

    print("You are an adult!")  

# If age is less than 0
elif user_age <= 0:

    print("Error!")

# If age is greater than 100
elif user_age >= 100:

    print("Congratulations! You are about to die")

# If age is equal to and between 1 and 18
elif user_age >= 1 and user_age <= 18:

    print("You are a child!")

```

## Example 2: Displaying a message after entering temperature

```python

# IF Statements

# DECLARE temp: INTEGER
# Asking the user to input the temperature
temp = int(input("What is the temparature: "))

# If temperature is equal to and between 0 to 40
if temp >= 0 and temp <= 40:

    print("Normal Temperature!")

# If temperature is equal to and between 40 to 100
elif temp >= 41 and temp <= 100:

    print("Very Hot")

# If temperature is less than 0
elif temp < 0:

    print("Very Cold")  

# If temperature is less than 0 and / or greater than 100
else:

    print("Extreme Temperature")

```

# CASE Statements

This is a little bit different instead of calling it "*CASE OF OTHERWISE ENDCASE*". *Pythonistas* ( *just learned that* ) calls it **MATCH CASE**. Or we could go the simple way and just use [[Selection and Iteration - Python#IF Statements| IF Statements]].

## Method 1: Match Case

### Example 1: User enter his programming language

```python

# CASE Statements

print()

# Displaying this little message
print("Programming Language Choice Thing :)")

print()

# Asking the user to input his language of choice
lang = input("What's the programming language you want to learn? ")

# IF user's input was:
match lang:

    # JavaScript
    case "JavaScript":

        print()
        print("You can become a web developer.")
        print()

    # Python
    case "Python":

        print()
        print("You can become a Data Scientist")
        print()

    # PHP
    case "PHP":

        print()
        print("You can become a backend developer")
        print()

    # Solidity
    case "Solidity":

        print()
        print("You can become a Blockchain developer")
        print()

    # Java
    case "Java":

        print()
        print("You can become a mobile app developer")
        print()

    # If user anything else that is not part of the code
    case _:

        print()
        print("The language doesn't matter, what matters is solving problems.")
        print()

```

## Method 2: [[Functions and Procedures - Python | Function/Procedure]]

### Example 1: 

```python

# CASE Statements

print()

# DECLARE lang: STRING
# Asking the user to enter his language
lang = input("Please Enter Your Programming Language: ")

print()

# FUNCTION switch(DECLARE lang: STRING)
def switch(lang):

    # If user types JavaScript
    if lang == "JavaScript":

        return "You can become a web developer."

    # If user types PHP
    elif lang == "PHP":

        return "You can become a backend developer."

    # If user types Python
    elif lang == "Python":

        return "You can become a Data Scientist"

    # If user types Solidity
    elif lang == "Solidity":

        return "You can become a Blockchain developer."

    # If user types Java
    elif lang == "Java":

        return "You can become a mobile app developer"

    # If user types anything else that is not part of the list
    else:

        return "You could have picked a normal language, but that would make you an idiot"

# Calling Function to `main` Program
result = switch(lang)

# Displaying Result
print(result)

```

# Pre-Condition Loops

## While Loops

Will I have to say the same things again, I will just being writing the examples as you need to understand then, because learning the theory will only gain you so much knowledge.

### Example 1: User enters phone number and displays a message

This program will **not stop** until user input his phone number

```python

# WHILE Loops

# DECLARE tel_num: STRING
# Initialising variable
tel_num = ""

# Condition to enter loop
while len(tel_num) == 0:
#or while not tel_num

	# User enter his phone number
    tel_num = input("Please Enter A Telephone Number: ")

# Prints phone number
print(f"Your Telephone Number is {tel_num}")

```

### Example 2: The program will enter the *while loop* **once**

```python

# WHILE Loops

# DECLARE enter: BOOLEAN
enter = True

# Condition to enter "while" loop
while enter == True:

    # Enters the "while" loop as variable "enter" = "True"
    print()
    print("Login Successful")
    print()

    # Variable "enter" becomes "False"
    enter = False

    # As "enter" has become "False"
    # The program will NOT enter the while loop after displaying this message
    print()
    print("You have been hacked")
    print()

```

## For Loops

So... What do I have to say; **for** loops are widely used in function such as [[Linear Search - Python | linear search]], [[Bubble Sort - Python | bubble sort]] and more.

### Example 1: Displaying values of array on separate lines

```python

# FOR Loops

# DECLARE ARRAY number[3]: INTEGER
number = [0, 23, 69, 90]

print()

# DECLARE i: INTEGER
# Displaying array "number" values on different lines
for i in number:

    # Displays each value on separate lines
    print(i)

print()

```

### Example 2.0: Displaying numbers from 0 to 10

```python

# FOR Loops

# Displaying 0 to 10

print()

# DECLARE i: INTEGER
# Remember in programming we start wih 0
for i in range(11):

    # Displays the numbers on separate lines
    print(i)

print()

```

### Example 2.1: Displaying number from 1 to 10

```python

# FOR Loops

# Displaying 1 to 10

print()

# DECLARE i: INTEGER
# We now have 2 "arguments" in or "range" function
for i in range(1, 11):

    # Displays the numbers on separate lines
    print(i)

print()

```

### Example 2.2: Displaying multiples of 2 ( starting with 2 ending with 10 )

```python

# FOR Loops

# Displaying multiples of 2

print()

# DECLARE i: INTEGER
# Starting from "2", ending with "10" in steps of "2"
for i in range(2, 11, 2):

    # Displays the values on separate lines
    print(i)

print()

```

### Example 2.3: Displaying from 10 to 1

```python

print()

# DECLARE x: INTEGER
for x in range(10, 0, -1):

    print(x)

print()

```

### Example 3: Making Art ( fucking see for yourself - I am too lazy to explain )

```python

# FOR Loops

#Asking the user to input the "parameters" ( trying to be fancy with it - fuck you )
print()

# DECLARE rows: INTEGER
# User inputs the number of rows
rows = int(input("Please Enter Number Of Rows: "))

# DECLARE columns: INTEGER
# User inputs the number of columns
columns = int(input("Please Enter Number Of Columns "))

# DECLARE symbols: INTEGER
# User inputs the character to choose to make the grid
symbol = input("Please Enter A Symbol To Use: ")

print()

# DECLARE x: INTEGER
# Displays the row
for x in range(rows):

    # Displays the columns
    # DECLARE y: INTEGER
    for y in range(columns):

        # Displays the symbol we choose in a grid with the specific size we choose
        #" end = "" " will not move the cursor to the next line
        print(symbol, end = "")

    # This "print()" function need to be here for it to change lines
    print()

print()

```

# Post-Condition Loops

## Repeat Until

This is unfortunately **not** available in [[Python Language| Python]]

So we have to improvise by using [[Selection and Iteration - Python#While Loops| while loops]]

### Example 1: User enter a name until desired name is found

```python

# REPEAT UNTIL Statements

print()

# In this case, this is equivalent to writing:
# Repeat "enter user_name"
while True:

    # DECLARE user_name: STRING
    # User enters a name
    user_name = input("Please Enter A Name: ")

    # If "user_name" is not equal to "S.Sunhaloo"    
    if user_name != "S.Sunhaloo":

        print()
        print("Not The Person We Wanted!")
        print()

    # IF "user_name" is equal to "S.Sunhaloo"
    else:

        print()
        print(f"Wecome Back {user_name}")
        print()

        # Does not stay in "while" loop
        break

```

### Example 2: Variable "i" increases until it become 5

```python

# REPEAT UNTIL Statements

print()

# DECLARE i: INTEGER
# Initialising "i" with the value 1
i = 1

# In this case, this is equivalent to writing:
# Repeat "print(i) and i -1" Until "i = 5"
while i <= 5:

    # Displays the value of i
    print(i)

    # Increases the value of i by 1
    i += 1
    # Until i = 5

print()

```

---

# Break | Continue | Pass

## Break

This is used to terminate a loop, when we know that the loop is going the continue

### Example 1: Asking the user to enter his name

```python

# BREAK

# Enter loop and keeps entering loop
while True:

    # DECLARE name: STRING
    # Asking the user to enter his name
    name = input("Please Enter Your Name: ")

    # If users enter his name
    if name != "":

        #Exits while loop
        break

```

## Continue

This is something that I cannot really explain; but all I know is that it will **skip** things

### Example 1: Skipping the "*-*" symbol

```python

# CONTINUE

print()

# DECLARE mobile_num: STRING
# Variable "mobile_num" hold a string
mobile_num = "1234-5678"

# DECLARE i: INTEGER
# Counter to find the required string
for i in mobile_num:

    # if variable "o" is equal to "-"
    if i == "-":

        # It will skip the symbol altogether
        continue

# prints the new value of mobile_num
print(i, end = "")

```

## Pass

This is another way to skip something. The **pass** function also acts as a *placeholder*

### Example 1: Skipping the number "*13*"

```python

# PASS

print()

# DECLARE i: INTEGER
# Counter to output the number from 0 to 20
for i in range(0, 21):

    # If the number "13" is found
    if i == 13:

        # It will skips the number "13"
        pass

    # After skipping
    else:

        # It will print the number 0 to 20 without displaying "13"
        print(i)

#Displays numbers from 0 to 20; and does not display 13

```

### Example 2: Using **pass** as a *placeholder*

This is normally used when in the process of programming

```python

# PASS

# FUNCTION binary_search()
# If the user has a function that has nothing in it
def binary_search():

    # Acting as a place holder
    pass

```

---

# Socials

- [**Instagram**](https://www.instagram.com/s.sunhaloo/)
- [**YouTube**](https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg)
- [**GitHub**](https://www.github.com/Sunhaloo)
---

S.Sunhaloo
Thank You!