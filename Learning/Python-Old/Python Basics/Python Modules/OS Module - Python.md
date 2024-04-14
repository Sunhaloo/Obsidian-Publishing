---
Alias: OS Module Python
Tag: python, basics, python_module
Author: S.Sunhaloo
Type: Module
Date: 2024-04-12
Status: In-Progress
---

## List of Contents

- [[OS Module - Python#What is the OS Module used for? | What is the OS Module used for?]]
	- [[OS Module - Python#Importing OS Module | Importing OS Module]]
- [[OS Module - Python#Find the OS Type | Find the OS Type]]
- [[OS Module - Python#List Folders and Other Files in Directory | List Folders and Other Files in Directory]]
- [[OS Module - Python#Directories | Directories]]

---

### My Links

- [[OS Module - Python#Socials| Links to Socials]]

---

# What is the OS Module used for?

>This note is part of the [[Modules - Python | module]] notes.

It will allow the user to interact with the operating system dependent functionality. You can have functionalities like:

- Read and Write files ( *normally text files* )
- Manipulate Paths ( `C:\User\user_name...` or `~/.config/nvim/...` )
- Create Temporary files and Directories

>[!info]
>From what I can see glancing at the [documentations](https://docs.python.org/3/library/os.html). Not all functions are available on Windows... *Glory to Linux*!!!

## Importing OS Module

>[!tip] Usage
>```python
>import os
>```
>>This is required to use the functions of the `os` module.

# Catch Error Given by the OS Module

For example if you have someone input '0' as the divisor into a *Calculator* Program in Python. You would see that you get the error `ZeroDivisionError`.

An [[Exception Handling - Python | exception]] of `OSError` will be raised when the system functions returns system-related errors such as:

- File / Directories Related Errors
- Process Related Errors
- General System Errors

To *catch* an `os` module errors; use the **exception**: `OSError`

>[!tip] Usage
>```python
># Exception Handling
>try:
>...
>except OSError:
>...
>```
>You can generate the error by [[OS Module - Python#Importing OS Module | importing]] the `os` module and then type `print(os.error)`.

## Find the OS Type

We can use python to find the Operating System that we are using. Here is the code below $\downarrow$:

```python

import os

print(os.name)

```

This can output 3 different things:

1. `nt` $\rightarrow$ Windows NT
2. `posix` $\rightarrow$ Unix / Linux
3. `java` $\rightarrow$ JavaOS


## Directories

### Check if Directory Exists

We can easily check if a directory exists by using the function `os.path.exists`. Here is a little code below $\downarrow$ to give you a little example:

```python

import os 

# Check if "C:/Users/Azmaan/Desktop" Exists
print()

print(f"Does Directory Exists? {os.path.exists("C:/Users/Azmaan/Desktop")}")

print()
# Check if "C:/Users/Azmaan/Desktop/Does_NOT_Exists" Exists
print()

print(f"Does Directory Exists? {os.path.exists("C:/Users/Azmaan/Desktop/Does_NOT_Exists")}")

print()

```


### List Folders and Other Files in Directory

This is simply the `ls` command but in Python.

```python

import os

print()

# List all Folders and Files in Directory
print(f"Folders and Files in Directory: {os.listdir()}")

print()

```

>[!tip]
>We can pass in a `path` in `os.listdir()` to list the folders and files in that **specific** directory.
>The [[Python Language#Type Function | "type"]] of `os.listdir()` is of `list`!

### Display Current Directory and Change Directory

Here, we are going to learn about how to display the current working directory and change the working directory to another folder on the Computer.

```python

import os

print()

# DECLARE current_dir: STRING
# Display Current Directory
current_dir = os.getcwd()
print(f"The Current Directory: {current_dir}")

print()

# DECLARE new_directory: STRING
# Change Current Directory
new_directory = "C:/Users/Azmaan/Desktop/c_programming"
# Use function `os.chdir` to change current directory to `new_directory`
os.chdir(new_directory)

# Find the Current Directory Again
print(f"The Current Directory Now is: {os.getcwd()}")

print()

```


## Current Base Name / Folder Name of Directory

Pretend that you are working on the directory `~/.config/nvim`. This function will return the `nvim` part; basically the **last** things in the part / directory.

```python

import os

print()

# DECLARE path: STRING
path = "C:/Users/Azmaan/Desktop"

print(f"Current Directory '{os.getcwd()}' |  Current Folder = '{os.path.basename(path)}'")

print()

```

The function `os.path.dirname()` will show us the directory but will skip the last folder opened; if you have `~/.config/nvim/lua/config` if you apply the function to that path. It will result in something like this `~/.config/nvim/lua/`

```python

import os

print()

# DECLARE path: STRING
path = "C:/Users/Azmaan/Desktop"

print(f"Current Directory '{os.getcwd()}' |  Current Folder = '{os.path.basename(path)}' | 'Main Directory' = '{os.path.dirname(path)}'")

print()

```

## Create Folder ( with Sub-Folders )

### Create a Single Folder

>[!tip] Usage
>```python
>os.mkdir(folder_name)
>```

The function above $\uparrow$ will only create **single** folder ( *no sub-folders* ) in a directory.

```python

import os

# FUNCTION list_directories()
def list_directories():

    print("List of Folders / Files:")
    print()

    # DECLARE ARRAY folders_files: STRING
    folders_files = os.listdir()

    print('-'*50)

    # DECLARE index: INTEGER
    # DECLARE x: STRING
    # List All Files and Folders
    for index, x in enumerate(folders_files):

        print(f"Item {index + 1} = {x}")

    print('-'*50)

	# DECLARE index: INTEGER
	# DECLARE x: STRING
    # Find the Folder / File called 'Test-Python'
    for index, x in enumerate(folders_files):

        if x == "Test-Python":

            print(f"Item {index + 1} = {x} <---")

print()
print(f"Current Directory = '{os.getcwd()}'")
print()
print("Directories Before Adding Creating Folder 'Test_Python'")
print()

# Calling Function `list_directories`
list_directories()

print("Creating Folder 'Test-Python'...")

# Create Folder 'Test-Python' in Current Directory
os.mkdir("Test-Python")

print()
print("Directories After Adding Creating Folder 'Test_Python'")
print()

# Calling Function `list_directories`
list_directories()

print('-'*50)
print()


```

>[!warning]
>This function will not be able to create something like this ( *from the example given above $\uparrow$* ) `C:/Users/Azmaan/Desktop/Test_Folder/Test_Sub_Folder`
>If you want to be able to create folders with sub-folders; please check the function right below $\downarrow$!

### Create Folders with Sub-Folders

>[!tip] Usage
>```python
>os.makedirs(folders_with_sub_folders)
>```

```python

import os

# FUNCTION list_directories()
def list_directories():

    print("List of Folders / Files:")
    print()

    # DECLARE ARRAY folders_files: STRING
    folders_files = os.listdir()

    print('-'*50)

    # DECLARE index: INTEGER
    # DECLARE x: STRING
    # List All Files and Folders
    for index, x in enumerate(folders_files):

        print(f"Item {index + 1} = {x}")

    print('-'*50)

    # DECLARE index: INTEGER
    # DECLARE x: STRING
    # Find the Folder / File called 'Test-Python'
    for index, x in enumerate(folders_files):

        if x == "Test-Python":

            print(f"Item {index + 1} = {x} <---")

print()
print(f"Current Directory = '{os.getcwd()}'")
print()
print("Directories Before Adding Creating Folder(s) 'Test_Python/Sub_Folder1' and 'Test_Python/Sub_Folder2'")
print()

# Calling Function `list_directories`
list_directories()

print("Creating Folder(s) 'Test-Python/Sub_Folder1' and 'Test_Python/Sub_Folder2'...")

# Create Folder 'Test-Python/Sub_Folder1' and 'Test_Python/Sub_Folder2' in Current Directory
os.makedirs("Test-Python/Sub_Folder1")
os.makedirs("Test-Python/Sub_Folder2")

print()
print("Directories After Adding Creating Folder(s0 'Test_Python/Sub_Folder1' and 'Test_Python/Sub_Folder2'")
print()

# Calling Function `list_directories`
list_directories()

print('-'*50)

print("List All Sub-Folders in 'Test-Python' Folder:")
print()

# DECLARE path_to_folder: STRING
path_to_folder = "C:/Users/Azmaan/Desktop/Test-Python"
# DECLARE ARRAY sub_folders: STRING
sub_folders = os.listdir(path_to_folder)

# DECLARE index: INTEGER
# DECLARE i: STRING
for index, i in enumerate(sub_folders):

    print(f"Item {index + 1} = {i}")

print()

```

>[!note]
>For Both `os.mkdir()` and `os.makedirs()` above; We only need to pass in the folders and / or folders with subfolder's **names**.
>Because it will create the folders and / or sub-folders in the **current** directory.

## Remove Folders ( with Sub-Folders )

### Remove a Single Folder

>[!tip] Usage
>```python
>os.rmdir(folder_name)
>```

```python

import os

def find_folder():

    # DECLARE ARRAY folders_files: STRING
    folders_files = os.listdir()

    print('-'*10)

    # DECLARE index: INTEGER
    # DECLARE x: STRING
    for index, x in enumerate(folders_files):

        if x == "Test-Python":

            print(f"Item {index + 1} = {x}")
            
            # If found, do not continue to iterate
            break

    if x != "Test-Python":

        print("Folder Was Not Found!")

    print('-'*10)

print()
print(f"Current Directory: {os.getcwd()}")
print()

print("Creating Folder 'Test-Python'...")

# Create Folder 'Test-Python'
os.mkdir("Test-Python")

# Calling Function `find_folder` to find 'Test-Python'
find_folder()

print()
print("Removing Folder 'Test-Python'")
print()

# Removing Folder 'Test-Python'
os.rmdir('Test-Python')

# Calling Function `find_folder` to find 'Test-Python'
find_folder()

```

### Remove Multiple Folders

>[!tip] Usage
>```python
>os.removedirs(folders_with_sub_folders)
>```

>[!note]
>Whatever conditions applies to creating folders ( with sub-folders ) also applies to removing / deleting folders!
>Check the *Note* above $\uparrow$.

```python

import os

def find_folder():

    # DECLARE ARRAY folders_files: STRING
    folders_files = os.listdir()

    print('-'*10)

    # DECLARE index: INTEGER
    # DECLARE x: STRING
    for index, x in enumerate(folders_files):

        if x == "Test-Python":

            print(f"Item {index + 1} = {x}")
            
            # If found, do not continue to iterate
            break

    if x != "Test-Python":

        print("Folder Was Not Found!")

    print('-'*10)

print()
print(f"Current Directory: {os.getcwd()}")
print()

print("Creating Folder(s) 'Test-Python/Sub_Folder1' and 'Test-Python/Sub_Folder2'...")

# Create Folder 'Test-Python'
os.makedirs("Test-Python/Sub_Folder1")
os.makedirs("Test-Python/Sub_Folder2")

# Calling Function `find_folder` to find 'Test-Python'
find_folder()

print()
print("Removing Folder(s) 'Test-Python/Sub_Folder1' and 'Test-Python/Sub_Folder2'")
print()

# Removing Folder(s) 'Test-Python/Sub_Folder1' and 'Test-Python/Sub_Folder2'
# Only need to remove 1 Folder / Sub-Folder; because parent folder will be removed
os.removedirs("Test-Python/Sub_Folder1")
os.removedirs("Test-Python/Sub_Folder2")

# Calling Function `find_folder` to find 'Test-Python'
find_folder()

```

#### Explanation: Removing Folders / Sub-Folders

In the code above $\uparrow$ you can see that we are making 2 sub-folders in the folder `Test-Python` and they are:

- `Sub_Folder1`
- `Sub_Folder2`

You would *think* that `os.removedirs("Test-Python/Sub_Folder1")` will remove **both** the sub-folder `Sub_Folder1` and `Sub_Folder2`. But think again! It cannot just simply remove any folders without permission!
Thus, we simply need to add `os.removedirs("Test-Python/Sub_Folder2")` below the first `os.removedirs()` Function.

## Check if Path is a Directory

>[!tip] Usage
>```python
>os.path.isdir(path)
>```

```python

import os

print()

# DECALRE path1: STRING
path1 = "C:/Users/Azmaan/Desktop"
# DECLARE path2: STRING
path2 = "C:/Users/Azmaan/Desktop/test.txt"

# Check if whether or not path1 and path2 are directories

print(f"Is '{path1}' a Directory? {os.path.isdir(path1)}")
print(f"Is '{path2}' a Directory? {os.path.isdir(path2)}")

print()

```

## Check if Path is a Text File

>[!tip] Usage
>```python
>os.path.isfile(path)
>```

```python

import os

print()

# DECALRE path1: STRING
path1 = "C:/Users/Azmaan/Desktop/test.txt"
# DECLARE path2: STRING
path2 = "C:/Users/Azmaan/Desktop"

# Check if whether or not path1 and path2 are text files

print(f"Is '{path1}' a File? {os.path.isfile(path1)}")
print(f"Is '{path2}' a File? {os.path.isfile(path2)}")

print()

```

## os.path.ismount(path)

>[!tip] Usage
>```python
>os.path.ismount(path)
>```

This function will check if the `path` is a mount point like a Pendrive or any type of storage device.

```python

import os

print()

# DECALRE path1: STRING
path1 = "C:/"
# DECLARE path2: STRING
path2 = "D:/"
# DECLARE path3: STRING
path3 = "C:/Users/Azmaan"

# Check if whether or not path1 and path2 are text files

print(f"Is '{path1}' a Mount Point? {os.path.ismount(path1)}")
print(f"Is '{path2}' a Mount Point? {os.path.ismount(path2)}")
print(f"Is '{path3}' a Mount Point? {os.path.ismount(path3)}")

print()

```

## Opening and Writing into File

>[!bug]- We have Text Files Manipulation in Python. If you are working with `.txt` Files; I recommend looking at [[]].
>This is for Fun!

This is a simple program what will open a text file in `write` mode and will enter `Written from Python` in it.

```python

import os

print()

# Opening File in `write` mode
file_descriptor = os.open("test.txt", os.O_WRONLY | os.O_CREAT)

# Writing into File
os.write(file_descriptor, b"\nWritten from Python\n")

# Closing File
os.close(file_descriptor)

# Displaying Contents of `test.txt` from Python ---> To get an idea if wether or not it has worked
# The code below forms part of Text File
with open("test.txt", 'r') as text_file:

    # Outputs the contents of `test.txt`
    print("Contents of Text File:")
    print(text_file.read())

    # Close the File
    text_file.close()

    # Check if `test.txt` has been closed
    print(f"Is `test.txt` closed? {text_file.closed}")

```

The arguments passed into `os.open()` function might seems a bit scary... it is scary! But don't worry [ChatGPT](chat.openai.com) got us covered.

- The argument `os.O_WRONLY` simply means that it will open the file in `write` mode.
- The argument `os.O_CREAT` will create the file if it does not find it.

>[!note]
>In normal Text File operations such as in [[]]; we cannot use the arguments that are found above $\uparrow$ in the `os.open()` function.

---

# Socials

- [**Instagram**](https://www.instagram.com/s.sunhaloo/)
- [**YouTube**](https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg)
- [**GitHub**](https://www.github.com/Sunhaloo)

---

S.Sunhaloo
Thank You!