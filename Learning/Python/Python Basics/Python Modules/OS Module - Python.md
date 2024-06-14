---
Alias: OS Module Python
Tag: python, basics, python_module
Author: S.Sunhaloo
Type: Module
Date: 2024-04-12
Status: Completed
---

## List of Contents

- [[OS Module - Python#What is the OS Module used for? | What is the OS Module used for?]]
	- [[OS Module - Python#Importing OS Module | Importing OS Module]]
- [[OS Module - Python#Find the OS Type | Find the OS Type]]
- [[OS Module - Python#List Folders and Other Files in Directory | List Folders and Other Files in Directory]]
- [[OS Module - Python#Directories | Directories]]
- [[OS Module - Python#File Manipulation | File Manipulation]]
- [[OS Module - Python#Open System Applications | Open System Applications]]

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


# Directories

## Check if Directory Exists

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


## List Folders and Other Files in Directory

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

## Display Current Directory and Change Directory

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

## Walk Directories

This is kinda weird and strange. So let me show you the code first and then we talk

>[!tip] Usage
>```python
>os.walk(path)
>```

```python

import os

print()

print(f"Current Directory: {os.getcwd()}")

# DECLARE dir_path: STRING
# DECLARE dir_names: STRING
# DECLARE file_names: STRING

for dir_path, folder_names, file_names in os.walk("/mnt/c/Users/Azmaan/Desktop"):

    print(f"Directory Path: {dir_path}")
    print()
    print(f"Folder Name:  {folder_names}")
    print()
    print(f"File Names: {file_names}")

print()

```

This is the output of the code above $\uparrow$:

```console
Current Directory: /mnt/c/Users/Azmaan/Desktop
Directory Path: /mnt/c/Users/Azmaan/Desktop

Folder Name:  ['c_programming', 'hacking', 'Ubuntu NeoVim']

File Names: ['adil discord.png', 'archlinux-2024.04.01-x86_64.iso', 'BattleBit Remastered.url', 'desktop.ini', 'Discord.lnk', 'EndeavourOS_Galileo-Neo-2024.01.25.iso', 'fonts installed.txt', 'geek.exe', 'HudSight - custom crosshair overlay.url', "KovaaK's.url", 'Obsidian.lnk', 'output.txt', 'PowerShell-7.4.2-win-x64.msi', 'Prefetch.lnk', 'songs to download.txt', 'temp.lnk', 'test.py', 'time.py', 'todo.md', 'Unturned.url', 'VS Code.lnk']
Directory Path: /mnt/c/Users/Azmaan/Desktop/c_programming

Folder Name:  []

File Names: ['main.o', 'Makefile', 'Number_Guessing_Game.c', 'output.exe', 'run.c', 'test']
Directory Path: /mnt/c/Users/Azmaan/Desktop/hacking

Folder Name:  ['phone_infoga', 'pics', 'social-analyzer']

File Names: []
Directory Path: /mnt/c/Users/Azmaan/Desktop/hacking/phone_infoga

Folder Name:  []

File Names: ['phoneinfoga']
Directory Path: /mnt/c/Users/Azmaan/Desktop/hacking/pics

Folder Name:  []

File Names: []
Directory Path: /mnt/c/Users/Azmaan/Desktop/hacking/social-analyzer

Folder Name:  ['.git', '.github', 'data', 'logs', 'modules', 'public', 'readme', 'test']

File Names: ['.dockerignore', '.editorconfig', '.gitattributes', '.gitignore', 'app.js', 'app.py', 'auto_pip.sh', 'clean-up.logs', 'docker-compose.yml', 'Dockerfile', 'info', 'LICENSE', 'package-lock.json', 'package.json', 'README.md', 'README.rst', 'requirements.txt', 'setup.py']
Directory Path: /mnt/c/Users/Azmaan/Desktop/hacking/social-analyzer/.git

Folder Name:  ['branches', 'hooks', 'info', 'logs', 'objects', 'refs']

File Names: ['config', 'description', 'HEAD', 'index', 'packed-refs']
Directory Path: /mnt/c/Users/Azmaan/Desktop/hacking/social-analyzer/.git/branches

Folder Name:  []

File Names: []
Directory Path: /mnt/c/Users/Azmaan/Desktop/hacking/social-analyzer/.git/hooks

Folder Name:  []

File Names: ['applypatch-msg.sample', 'commit-msg.sample', 'fsmonitor-watchman.sample', 'post-update.sample', 'pre-applypatch.sample', 'pre-commit.sample', 'pre-merge-commit.sample', 'pre-push.sample', 'pre-rebase.sample', 'pre-receive.sample', 'prepare-commit-msg.sample', 'push-to-checkout.sample', 'update.sample']
Directory Path: /mnt/c/Users/Azmaan/Desktop/hacking/social-analyzer/.git/info

Folder Name:  []

File Names: ['exclude']
Directory Path: /mnt/c/Users/Azmaan/Desktop/hacking/social-analyzer/.git/logs

Folder Name:  ['refs']

File Names: ['HEAD']
Directory Path: /mnt/c/Users/Azmaan/Desktop/hacking/social-analyzer/.git/logs/refs

Folder Name:  ['heads', 'remotes']

File Names: []
Directory Path: /mnt/c/Users/Azmaan/Desktop/hacking/social-analyzer/.git/logs/refs/heads

Folder Name:  []

File Names: ['main']
Directory Path: /mnt/c/Users/Azmaan/Desktop/hacking/social-analyzer/.git/logs/refs/remotes

Folder Name:  ['origin']

File Names: []
Directory Path: /mnt/c/Users/Azmaan/Desktop/hacking/social-analyzer/.git/logs/refs/remotes/origin

Folder Name:  []

File Names: ['HEAD']
Directory Path: /mnt/c/Users/Azmaan/Desktop/hacking/social-analyzer/.git/objects

Folder Name:  ['info', 'pack']

File Names: []
Directory Path: /mnt/c/Users/Azmaan/Desktop/hacking/social-analyzer/.git/objects/info

Folder Name:  []

File Names: []
Directory Path: /mnt/c/Users/Azmaan/Desktop/hacking/social-analyzer/.git/objects/pack

Folder Name:  []

File Names: ['pack-51dcc713acba494badd1fc1a591e7da2a7159458.idx', 'pack-51dcc713acba494badd1fc1a591e7da2a7159458.pack']
Directory Path: /mnt/c/Users/Azmaan/Desktop/hacking/social-analyzer/.git/refs

Folder Name:  ['heads', 'remotes', 'tags']

File Names: []
Directory Path: /mnt/c/Users/Azmaan/Desktop/hacking/social-analyzer/.git/refs/heads

Folder Name:  []

File Names: ['main']
Directory Path: /mnt/c/Users/Azmaan/Desktop/hacking/social-analyzer/.git/refs/remotes

Folder Name:  ['origin']

File Names: []
Directory Path: /mnt/c/Users/Azmaan/Desktop/hacking/social-analyzer/.git/refs/remotes/origin

Folder Name:  []

File Names: ['HEAD']
Directory Path: /mnt/c/Users/Azmaan/Desktop/hacking/social-analyzer/.git/refs/tags

Folder Name:  []

File Names: []
Directory Path: /mnt/c/Users/Azmaan/Desktop/hacking/social-analyzer/.github

Folder Name:  ['workflows']

File Names: []
Directory Path: /mnt/c/Users/Azmaan/Desktop/hacking/social-analyzer/.github/workflows

Folder Name:  []

File Names: ['main.yml']
Directory Path: /mnt/c/Users/Azmaan/Desktop/hacking/social-analyzer/data

Folder Name:  []

File Names: ['countries.json', 'dict.json', 'languages.json', 'names.json', 'sites.json', 'sites.json_new']
Directory Path: /mnt/c/Users/Azmaan/Desktop/hacking/social-analyzer/logs

Folder Name:  []

File Names: ['xrtf49av1s_log.txt']
Directory Path: /mnt/c/Users/Azmaan/Desktop/hacking/social-analyzer/modules

Folder Name:  []

File Names: ['engine.js', 'external-apis.js', 'extraction.js', 'fast-scan.js', 'helper.js', 'name-analysis.js', 'slow-scan.js', 'special-scan.js', 'stats.js', 'string-analysis.js', 'visualize.js']
Directory Path: /mnt/c/Users/Azmaan/Desktop/hacking/social-analyzer/public

Folder Name:  []

File Names: ['app.html', 'graph.html']
Directory Path: /mnt/c/Users/Azmaan/Desktop/hacking/social-analyzer/readme

Folder Name:  []

File Names: ['awesomeopensource.png', 'cli.gif', 'convertnumbers.png', 'findnumbers.png', 'finduserprofilesfast.png', 'finduserprofilesslow.png', 'finduserproflesfast.png', 'finduserproflesslow.png', 'intro_fast.gif', 'intro_slow.gif', 'model.jpg', 'modules.png', 'mostcommon.png', 'possible.png', 'profiles.png', 'showuserproflesslow.png', 'socialanalyzerlogo.png', 'socialanalyzerlogo_.png', 'splitwordsbyalphabet.png', 'splitwordsbyuppercase.png', 'structure.png', 'wordinfo.png']
Directory Path: /mnt/c/Users/Azmaan/Desktop/hacking/social-analyzer/test

Folder Name:  []

File Names: ['requirements.txt', 'test.sh']
Directory Path: /mnt/c/Users/Azmaan/Desktop/Ubuntu NeoVim

Folder Name:  []

File Names: ['cargo install fnm.png', 'fnm install - version.png']
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

You would *think* that `os.removedirs("Test-Python/Sub_Folder1")` will remove **both** the sub-folder `Sub_Folder1`, `Sub_Folder2` and the *root* folder `Test-Python`. But think again! It cannot just simply remove any folders without permission!
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

## Check it Path is a Mount Point

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

# File Manipulation

## Create Files

>Not adding "*usage*"; because its better if you look at the code itself!

>[!bug] We need to *close* the Files after Creation!!!

```python

import os

print()

print(f"Current Directory: {os.getcwd()}")

# Create a Text File
text_file = open("text.txt", 'x')
# Create a Python File
python_file = open("python.py", 'x')
# Create a C File
c_file = open("c.c", 'x')

# Closing Files
text_file.close()
python_file.close()
c_file.close()

# Check if Files has been closed
print()
print(f"Is Text File Closed? {text_file.closed}")
print(f"Is Python File Closed? {python_file.closed}")
print(f"Is C File Closed? {c_file.closed}")
print()

```

This function will allow us to create any file ( *examples `.txt`, `.py`, `.c` * ) in Python.

The `x` in `open("...", 'x')` means that it will **create** the file if and only if there is **no** other file with the **same** *name*.

## Remove any File

>[!tip] Usage
>```python
>os.remove(path)
>```

```python

import os

# FUNCTION find_files()
def find_files():

    # DECALRE ARRAY files: STRING
    files = os.listdir()

    print('-'*30)

    # DECLARE i: INTEGER
    # DECLARE x: STRING
    for i, x in enumerate(files):

        # Finding Files
        if x == "c.c":

            print(f"Item {i + 1} = {x}")
            continue

        elif x == "python.py":

            print(f"Item {i + 1} = {x}")
            continue
            

        elif x == "text.txt":

            print(f"Item {i + 1} = {x}")
            break
        
    else:

        print("Files Have NOT Been Found!")

    print('-'*30)

print()

print(f"Current Directory: {os.getcwd()}")

# Create a Text File
text_file = open("text.txt", 'x')
# Create a Python File
python_file = open("python.py", 'x')
# Create a C File
c_file = open("c.c", 'x')

# Closing Files
text_file.close()
python_file.close()
c_file.close()

# Check if Files has been closed
print()
print(f"Is Text File Closed? {text_file.closed}")
print(f"Is Python File Closed? {python_file.closed}")
print(f"Is C File Closed? {c_file.closed}")

# Calling Function `find_files`
print()
find_files()
print()

# Remove All Files
print("Removing All Files Created...")

os.remove("text.txt")
os.remove("python.py")
os.remove("c.c")

# Calling Function `find_files`
print()
find_files()

print()

```

>[!note]
>Take a look at the `if` statements in the function `find_files()` above $\uparrow$.
>1. `for` loops can take `else` statements?!? ( *actually WTF*! ).
>2. I had to write `c.c` then `python.py` and then `text.txt`
>	- Basically in alphabetical order, else the `break` statements would have fucked it up.

## Renaming Files

>[!tip] Usage
>```python
>os.rename('original_name.ext', 'new_name.ext')
>```

This function will allow you to rename **any** file that is on the computer... If it was not on the computer; where the fuck will you rename something... *My ass*!

>[!warning]
>We need to also pass in the *extension* ( `.txt`,  `.png`, `.c`, `.py` ) of the file

```python

import os

# FUNCTION list_directory()
def list_directory():

    print("-" * 40)

    # DECLARE ARRAY objects: STRING
    objects = os.listdir()
    # DECLARE count: INTEGER
    count = 0

    # DECLARE i: INTEGER
    # DECLARE x: STRING
    for i, x in enumerate(objects):
        print(f"Item {i + 1}: {x}")
        count += 1

    print("-" * 40)
    print(f"Number of Files = {count}")
    print("-" * 40)


print()
print(f"Current Directory: {os.getcwd()}")
print()

# Calling Funtion `list_directory`
list_directory()

# Create a Text File
text_file = open("txt.txt", "x")
# Create a Python File
python_file = open("py.py", "x")
# Create a C File
c_file = open("c.c", "x")

# Closing Files
text_file.close()
python_file.close()
c_file.close()

# Check if Files has been closed
print()
print(f"Is Text File Closed? {text_file.closed}")
print(f"Is Python File Closed? {python_file.closed}")
print(f"Is C File Closed? {c_file.closed}")

# Renaming All Files Created
print("Renaming All Files Created...")

os.rename("txt.txt", "text-file.txt")
os.rename("py.py", "python-file.py")
os.rename("c.c", "c-file.c")

# Calling Function `list_directory`
list_directory()

print()

```

The code above will create 3 files and then close it ( *because we are not using context manager* ). After closing these files that we just created; we are going to apply the function `os.rename(...)` and change their names respectively.

## "Stats" of Files

>[!tip] Usage
>```python
>os.stat('file.ext')
>```

This function above $\uparrow$ will allow you to show a variety ( *ahh! a word that I do not use often* ) of information about a file. Think of this in like [BattleBit Remastered](https://store.steampowered.com/app/671860/BattleBit_Remastered/) where you can see that *statistics* of you gun or character.
But now, its going to be about files ( *this is not a game... I repeat... this is not a game $\rightarrow$ but you can treat it as one* )

```python

import os

print()

print(f"Current Directory: {os.getcwd()}")

print()

# Text File's "stats"
print(f"Text File: {os.stat("C:/Users/Azmaan/Desktop/output.txt")}")
print()

# Python File's "stats"
print(f"Python File: {os.stat("C:/Users/Azmaan/Desktop/test.py")}")
print()

# C File's "stats"
print(f"C File: {os.stat("C:/Users/Azmaan/Desktop/c_programming/run.c")}")

print()

```

I recommend check all the attributes / result of the `os.stat()` function. I suggest reading about on the [documenation](https://docs.python.org/3/library/os.html#os.stat_result)

>[!info]
>This function as its *own* data type called `os.stat_result`. Refer to the ( *website* ) link above $\uparrow$ for more information.

### Accessing a Single Result of Function

As you know if you run the function `os.stat()` it will output a lot of gibberish ( *ahh, another word that I never ever used... even though I just used it* ). Thus, we have a way of only accessing a **single** "*answer*" from the function.

>Again, refer to the documentation link above $\uparrow$ for more information.

>[!note]-
>The module `datetime` is there so that we get a readable output of time.

```python

import os
from datetime import datetime

print()

print(f"Current Directory: {os.getcwd()}")

# Get the File Size of Text File
print()
print(f"File Size of 'hello_world.txt' = {os.stat("C:/Users/Azmaan/Desktop/hello_world.txt").st_size} Bytes")
print()

# Get the "Time Since Creation" of Markdown File
print(f"Time since Creation of 'todo.md' = {os.stat("C:/Users/Azmaan/Desktop/todo.md").st_birthtime} Seconds")
print(f"Another Date and Time Format of 'todo.md' = {datetime.fromtimestamp(os.stat("C:/Users/Azmaan/Desktop/todo.md").st_birthtime)}")

# Get the "Most Recent Access Time" of Python File
print()
print(f"Most Recent Access Time of 'test.py' = {os.stat("C:/Users/Azmaan/Desktop/test.py").st_atime} Seconds")
print(f"Another Date and Time Format of 'test.py' = {datetime.fromtimestamp(os.stat("C:/Users/Azmaan/Desktop/test.py").st_atime)}")
print()


print()

```

## Opening and Writing into File

>[!bug]- We have Text Files Manipulation in Python. If you are working with `.txt` Files; I recommend looking at [[Text Files - Python]].
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
>In normal Text File operations such as in [[Text Files - Python]]; we cannot use the arguments that are found above $\uparrow$ in the `os.open()` function.

# Open System Applications

>[!tip] Usage
>```python
>os.system(...)
>```

## Opening Some OS Programs

>[!note]-
>This was done on Windows!!!
>>Need to switch to Linux FULL TIME!!!

```python

import os

print()
print("Opening Notepad...")
print()

# opens notepad on windows
os.system("notepad.exe")

print("Opening Calculator...")

# opens the windows calculator
os.system("calc.exe")

print()

```

>[!warning] BIG NOTE
>You and I would think that this code above $\uparrow$ will firstly open up `notepad` and then open `calculator`.
>But... this is not know it goes...
>I will wait for you to close `notepad` and then open up the fucking `calculator` program.
>>[!info]
>>We can actually open both simultaneously, it will require us to ditch the `os` module completely; but that a topic for another day...
>>>The module is called **subprocess**!!!

---

# Socials

- [**Instagram**](https://www.instagram.com/s.sunhaloo/)
- [**YouTube**](https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg)
- [**GitHub**](https://www.github.com/Sunhaloo)

---

S.Sunhaloo
Thank You!