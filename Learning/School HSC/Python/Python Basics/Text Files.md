---
Alias: Python Text Files
Tag: python, basics
Author: S.Sunhaloo
Type: Basics
Date: 2023-10-15
Status: Completed
---

## List of Contents

- [[Text Files#What is a Text File? | What is a Text File?]]
- [[Text Files#We need the OS Module | The Need For OS Module]]
- [[Text Files#Path of File | Path of File]]
	- [[Text Files#Example Path of a File | Example of Path]]
- [[Text Files#Checking if File / Directory Exists | Checking if File / Directory Exists]]
	- [[Text Files#Example | Example Code]]
- [[Text Files#Checking if "*path*" is a File or Directory | Checking if path is a File or Directory]]
	- [[Text Files#Example Checking if a *path* is a File | Checking if path is a File]]
	- [[Text Files#Example Checking if a *path* is a Directory | Checking if path is a Directory]]
- [[Text Files#Opening a Text File | Opening a Text File]]
	- [[Text Files#Example Opening a Text File | Example of Opening a Text File]]
- [[Text Files#Reading Contents of a Text File | Reading Contents of a Text File]]
	- [[Text Files#Example Reading the Contents of the Text File | Example of Reading Contents of Text File]]
- [[Text Files#Closing a Text File | Closing a Text File]]
	- [[Text Files#Example Closing a Text File | Example of Closing a Text File]]
	- [[Text Files#How to Check if a Text File is Open or Closed | How to Check if a Text File is Open or Closed]]
		- [[Text Files#Example Checking if Text File has been Closed | Example on How to Check if File has been Closed]]
- [[Text Files#Writing Data Into File | Writing Data Into File]]
	- [[Text Files#Example Opening a Text File to Write Into | Example of Writing Data Into File]]
- [[Text Files#Appending data into Text File | Appending data into Text File]]
	- [[Text Files#Example Appending data into Text File | Example of Appending Data Into File]]
- [[Text Files#Note | Note]]

---

My Links

- [[Text Files#Socials | Link to Socials]]

---

# What is a Text File?

Man, look; if you are asking this question, maybe you have never used a computer before or you are a kid or maybe you are just dumb.

I am not here to tell you what a text file is. But I am not that bad of a person. Thus I will give you the Wikipedia link; Click [here](https://en.wikipedia.org/wiki/Text_file) to go to website.

## We need the OS Module

To be able to perform certain actions, we need to use the *OS Module*. Find more about module [[Modules - Python| here]]

>[!tip] Import the OS Module
>Even if you are *not* using the **OS Module**. I recommend importing it in every code in which you are dealing with text files.

## Path of File

I recommend getting use to the **Terminal / Bash / ZSH Shel;** or **Power Shell**. This will improve your overall skills and also why not learn something easy and new.

Nevertheless, if you do not want to learn it ( "*again why would you not learn it*" ). You can:

- Right Click on the file
- Hit Properties
- Copy the path

After copying the path you could put it in a variable

### Example: Path of a File

```python

# Path Example

path = "C:/Users/F1/Smooth Operator.txt"

```

---

# Checking if File / Directory Exists

This checks if the **location** of the file is stored.

>[!tip] Usage
>```python
>os.path.exists("path")
>```

## Example

```python

# Checking if File / Directory Exists

# Importing Module "os"
import os

print()

# Passing the "path" of text file "python.txt" inside the function
if os.path.exists("C:/Users/azmaa/Desktop/python.txt"):

    # If "python.txt" exists
    print("Exists")

else:

    # If "python.txt" exists
    print("Does Not Exists")

```

# Checking if "*path*" is a File or Directory

This is a function in which it will try to find out whether that "*path*" actually a *text file* or *directory*

>[!tip] Usage
>```python
># File
>os.path.isfile("path")
># Directory
>os.path.isdir("path")
>```

## Example: Checking if a *path* is a File

```python

# Checking Path 

# Importing Module "os"
import os

print()

# Checking if "python.txt" file is a text file
if os.path.isfile("C:/Users/azmaa/Desktop/python.txt"):

    # If "python.txt" is text file
    print("It is a file!")

else:

    # If "python.txt" is NOT a text file
    print("Not a file!")

```

## Example: Checking if a *path* is a Directory

```python

# Checking Path

# Importing Module "os"
import os

# Using path of text file "python.txt"
print()
print("Using Path of Text File ( includes python.txt ):")
print()

if os.path.isdir("C:/Users/azmaa/Desktop/python.txt"):

    # If path is a directory
    print("It Is A Directory")

else:

    # If path is NOT a directory
    print("Not A Directory")

# Using path of "directory"
print()
print("Using Path of Text File ( does not include python.txt )")
print()

if os.path.isdir("C:/Users/azmaa/Desktop"):

    # If path is a directory
    print("It Is A Directory")

else:

    # If path is NOT a directory
    print("Not A Directory")

```

>[!note]
>For the code below, you need to do it sequentially; thus, I will be using the same code.
>Just adding more to it.

# Opening a Text File

This will allow Python to **open** a *text* file.

>[!tip] Usage
>```python
>with open("path") as file:
>	pass
>```

>[!warning]
>This will **not** *close* the text file

## Example: Opening a Text File

```python

# Opening a File

# Import Module "os

# Even though this module will not be used
# I will be inserting it as it will be harmless
# Yes, there might be a possibility that the execution of the program
# will be longer as it has to load contents module "os"
import os

print()

# DECLARE path: OF STRING
path = "C:/Users/azmaa/Desktop/python.txt"

# Opening "python.txt" file
with open(path) as file:

```

# Reading Contents of a Text File

To **read** a text file; we need to **open** it first ( "*Bruh, obviously*" ).

>[!tip] Usage
>```python
>print(file.read())
>```

>[!note]
>We still need to **open** the text file
>>[!tip] Usage
>>```python
>>with open("path") as file:
>>	print(file.read())
>>```

## Example: Reading the Contents of the Text File

```python

# Reading Contents of a Text File

# Import Module "os

# Even though this module will not be used
# I will be inserting it as it will be harmless
# Yes, there might be a possibility that the execution of the program
# will be longer as it has to load contents module "os"
import os

print()

# DECLARE path: OF STRING
path = "C:/Users/azmaa/Desktop/python.txt"

# Opening "python.txt" file
with open(path) as file:

    # Reading the contents of the text file
    print(file.read())

```

>[!warning]
>The file has **not** been **closed**
>We still need to close the file

# Closing a Text File

After opening a  text file; it needs to be closed as if we do not close it; it will stay in *Memory*.

>[!tip] Usage
>```python
>file.close()
>```

### Example: Closing a Text File

```python

# Closing A Text File

# Import Module "os

# Even though this module will not be used
# I will be inserting it as it will be harmless
# Yes, there might be a possibility that the execution of the program
# will be longer as it has to load contents module "os"
import os

print()

# DECLARE path: OF STRING
path = "C:/Users/azmaa/Desktop/python.txt"

# Opening "python.txt" file
with open(path) as file:

    # Reading the contents of the text file
    print(file.read())

    # Closing text file
    file.close()

```

## How to Check if a Text File is Open or Closed

This check is done using a [[Functions and Procedures - Python#What are Built-In Functions | built-in]] function.

>[!tip] Usage
>```python
>file.closed
>```
>We will have to use it in a **print** function

### Example: Checking if Text File has been Closed

```python

# Checking if Text File has been Closed

# Import Module "os

# Even though this module will not be used
# I will be inserting it as it will be harmless
# Yes, there might be a possibility that the execution of the program
# will be longer as it has to load contents module "os"
import os

print()

# DECLARE path: OF STRING
path = "C:/Users/azmaa/Desktop/python.txt"

# Opening "python.txt" file
with open(path) as file:

    # Checking if Text File is Open
    print("Is Text File Closed: " + str(file.closed))
    print()
    print("Reading python.txt File:")
    print()

    # Reading the contents of the text file
    print(file.read())

    # Closing text file
    file.close()

    print()

    # Checking if Text File is Closed
    print("Is Text File Closed: " + str(file.closed))

```

# Writing Data Into File

To be able to **write** in text files, we need to let Python know, that we are going to **write** into text file instead of *only* reading the contents

>[!tip] Usage
>```python
>with open("path", "w") as file:
>	pass
>```
>By adding "*"w"* "; we have let Python know that we are going to write in file

>[!warning]
>"*Writing*" data into file will mean that
># Everything will be *DELETED*
>### Proceed with caution 🚩

## Example: Opening a Text File to Write Into

```python

# "Writing" Into Text File

# Import Module "os

# Even though this module will not be used
# I will be inserting it as it will be harmless
# Yes, there might be a possibility that the execution of the program
# will be longer as it has to load contents module "os"

import os

print()

# DECLARE path: OF STRING
path = "C:/Users/azmaa/Desktop/python.txt"

# Opening "python.txt" file
with open(path, "w") as file:

    # Checking if Text File is Open
    print("Is Text File Closed: " + str(file.closed))

    # Writing Into File
    file.write("Typing Something 5 Times")

    file.write("\n")

    # We could even use a "For" Loop to write multiple lines
    for i in range(5):

        # Writing "This is a looped text" 5 times
        # "\n" --> Will not write on the same line
            # Writes on separate lines in Text File
        file.write("This is a looped text\n")

    # Closing text file
    file.close()

    print()

    # Checking if Text File is Closed
    print("Is Text File Closed: " + str(file.closed))

```

>[!note]
>```python
>file.write("\n")
>```
>This will *write* a **blank line in** *text file*

# Appending data into Text File

As the word "*append*" tells us; this will continue to add data into the Text File.

>[!tip] Usage
>```python
>with open("path", "a") as file:
>	pass
>```

>[!note]
>This will **not** *erase* anything in the text file that has been previously written

## Example: Appending data into Text File

```python

# Appending data into Text File

# Import Module "os

# Even though this module will not be used
# I will be inserting it as it will be harmless
# Yes, there might be a possibility that the execution of the program
# will be longer as it has to load contents module "os"
import os

print()

# DECLARE path: OF STRING
path = "C:/Users/azmaa/Desktop/python.txt"

# Opening "python.txt" file
with open(path, "a") as file:

    # Checking if Text File is Open
    print("Is Text File Closed: " + str(file.closed))

    # Appending data in File
    file.write("\n")
    file.write("\n")
    file.write("Appending Data Into File")
    file.write("\n")
    file.write("This line has been written in appending mode!?!")

    # Closing text file
    file.close()

    print()

    # Checking if Text File is Closed
    print("Is Text File Closed: " + str(file.closed))

```

---

# Note

Think of the **read**, **write** and **append** as *modes* in Vim

---

# Socials

- [**Instagram:**](https://www.instagram.com/s.sunhaloo/)
- [**YouTube:**](https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg)

---

S.Sunhaloo
Thank You!