---
Alias: Python Text Files
Tag: python, basics
Author: S.Sunhaloo
Type: File Manipulation
Date: 2024-04-16
Status: In-Progress
---

## List of Contents

- [[Text Files - Python v2#Context Manager | Context Manager]]
- [[Text Files - Python v2#Start Here | Text File]]

---

### My Links

- [[Text Files - Python v2#Socials | Links to Social]]

---

>[!info]
>I will be using some stuff from the [[OS Module - Python | Python OS Module]]
>So please refer to it.

# Create A Text ( any ) File

To create a text file or any type of file ( `.py`, `.c`, etc ) in Python we need to use the `open()` function will the mode `x`.

>[!note]-
>I will be focusing on Text Files as this is the notes for Text Files

以下を見てください $\downarrow$

## Without Context Manager

```python

import os # To be able to use some features such as 'getcwd()'

# FUNCTION close_files(DECLARE x: TextIOWrapper, DECLARE y: TextIOWrapper)
def close_files(x, y):

    x.close()
    y.close()

# Get Current Directory
print()
print(f"Current Directory: '{os.getcwd()}'")
print()

print("Creating Text Files")

# DECLARE text_file: TextIOWrapper
# Create Text File called "python_made.txt"
text_file = open("python_made.txt", 'x')
# DECLARE nice_text_file: TextIOWrapper
# Create Text File Called "very_nice.txt"
nice_text_file = open("very_nice.txt", 'x')

print()
# Check if files have been closed
print(f"Is 'python_made.txt' Closed? {text_file.closed}")
print(f"Is 'very_nice.txt' Closed? {nice_text_file.closed}")
print()

print("Closing Files...")

# Calling Function `close_files`
close_files(text_file, nice_text_file)

print()
# Check if files have been closed
print(f"Is 'python_made.txt' Closed? {text_file.closed}")
print(f"Is 'very_nice.txt' Closed? {nice_text_file.closed}")

print()

```

>[!warning]
>You will need to **close** the file **after** creation.
>Also this will create the file in the **current** directory.

>[!bug] Note
>This is not it brother. I was just playing with you. Below you are going to find the real start of the notes. The above $\uparrow$ code is good and works perfectly fine; but it is not the way to do it because we have a better version using **Context Managers**.

# Context Manager

## What is a Context Manager?

It is an object that is use to manage *resources* within a `with` statement.

- Allocates and Releases resources **automatically** when *entering* and *exiting* the context

>[!tip] Meaning...
>You do **not** need to close the file using the `.close()` function. Yaaayy!!!
>>Fuck My Life!

# Start Here

## Check if Text File is a Text File

Here we are going to be using the function from the [[OS Module - Python|OS Module]]

![[OS Module - Python#Check if Path is a Text File | OS Module]]

# Modes of Text Files

Here is a link to freecodecamp's [File Handling in Python](https://www.freecodecamp.org/news/file-handling-in-python/). If you know the basics of File Handling in Python, you know that there are different modes like:

- `x`
- `r`
- `w`
- `a`

This ranges from creating a file to reading and writing into said text file. Refer to the link above for more precise explanation ( _whatever the fuck "**precise**" means here_ ).

>As from now on, I will be using the [[Text Files - Python v2#Context Manager | Context Manager]]
>I will also be moving relatively fast for learning sake... I really want to start other Projects / Fun things like [Advent of Code](https://www.adventofcode.com)

## Output Mode of Text File



## 'r' Mode

>[!tip]- Usage
>```python
>file.read()
>```

This "mode" will allow us to **only** and **only** read text files.

In this example my text file that I want to read is found in `~/Desktop` and I am in `~` $\Rightarrow$ *Home Directory*. I will show you how to read the file from `~`.

```python

import os

# FUNCTION list_current_directory()
def list_current_directory():

    print()

    # DECLARE ARRAY files: STRING
    files = os.listdir()

    print('-'*50)

    # DECLARE i: INTEGER
    # DECALRE x: STRING
    for i, x in enumerate(files):

        if x == "songs to download.txt":

            print(f"Item No {i} = {x}")
            break


    if x != "songs to download.txt":

        print("Not Found!")

    print('-'*50)

print()

# Get Current Directory
print(f"Current Directory: {os.getcwd()}")

# Change the Directory to where text file is located
os.chdir("C:/Users/Azmaan/Desktop")

print()

# Check Directory Again
print(f"Current Directory Now: {os.getcwd()}")

# Call Function `list_current_directory`
list_current_directory()

print()
print("Opening File...")

# Read the Text File
with open("songs to download.txt", 'r') as text_file:

    # DECLARE contents: STRING
    # Read the contents of File
    contents = text_file.read()

    print()
    print("Contents of File:")
    print(contents)
    print()

# Check if file had been closed
print(f"Is Text File Closed? {text_file.closed}")

print()

```

## 'w' Mode

>[!tip]- Usage
>```python
>file.write()
>```

I think you are getting the point of this? Are you?... This will fucking allow us to fuck with the file. Not really, but will allow us to **write** into the file

>[!warning] BIG BIG WARNING
>If you use this mode in a text file that **already** contains something
>>[!bug] It will erase everything; all things will be overwritten!!!

```python

import os

# FUNCTION find_file():
def find_files():

    print("Find 'Text_File.txt': ", end="")

    # DECLARE text_file: STRING
    text_file = "Text_File.txt"

    # Check if path exists / file exists
    if os.path.exists(text_file):
        
        print("Text File Has Been Found")

    else:

        print("NOT Found!")

# FUNCTION reading():
def reading():

    with open("Text_File.txt", 'r') as file:

        output = file.read()

        print('-'*45)
        print("Contents of File:")
        print(output)
        print()

        EOF = file.readline()
        if EOF == "":

            print("<---END OF FILE--->")

        print('-'*45)

# Get Current Directory
print()
print(f"Current Directory: '{os.getcwd()}'")
print()

# Call Function `find_files`
find_files()

print()
print('-'*45)
print("Creating and Writing Contents into File...")

# Open Text File for Writing using Context Manager
with open("Text_File.txt", 'w') as file:

    file.write("Hello MotherFucker!")

print('-'*45)
print()
print("Find Text File Again")

# Call Function `find_files` again
find_files()

print()

# Call Function `reading`
reading()

# Check if files have been closed
print()
print(f"Is 'Text_File.txt' Closed? {file.closed}")
print()

```

>[!note]
>If you run this program; you would this that there was **no** "*Text_File.txt*". When we use the context manager with the mode `w`. It will also create the file in addition to writing "*Hello Motherfucker*" into it.

## 'a' Mode

This is basically the same as the `w` mode $\uparrow$. But in this case our file will **not** be *overwritten*!

```python

import os

# FUNCTION find_file():
def find_files():

    print("Find 'Text_File.txt': ", end="")

    # DECLARE text_file: STRING
    text_file = "Text_File.txt"

    # Check if path exists / file exists
    if os.path.exists(text_file):
        
        print("Text File Has Been Found")

    else:

        print("NOT Found!")

# FUNCTION reading():
def reading():

    with open("Text_File.txt", 'r') as file:

        output = file.read()

        print('-'*45)
        print("Contents of File:")
        print(output)
        print()

        EOF = file.readline()
        if EOF == "":

            print("<---END OF FILE--->")

        print('-'*45)

# Get Current Directory
print()
print(f"Current Directory: '{os.getcwd()}'")
print()

# Call Function `find_files`
find_files()

print()
print('-'*45)
print("Appending into Text File")

# Open Text File for Appending using Context Manager
with open("Text_File.txt", 'a') as file:

    file.write("\n")
    file.write("This is the second line of the file!")
    file.write("\nThis is the third line of the file!")

print('-'*45)
print()
print("Find Text File Again")

# Call Function `find_files` again
find_files()

print()

# Call Function `reading`
reading()

# Check if files have been closed
print()
print(f"Is 'Text_File.txt' Closed? {file.closed}")
print()

```

>[!info]
>Again, as I said; this is basically the same thing as `w` mode.
>If you did not create the file before running it. It will **create** it for you. Be thankful!

---

# Socials

- [**Instagram**](https://www.instagram.com/s.sunhaloo/)
- [**YouTube**](https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg)
- [**GitHub**](https://www.github.com/Sunhaloo)

---

S.Sunhaloo
Thank You!