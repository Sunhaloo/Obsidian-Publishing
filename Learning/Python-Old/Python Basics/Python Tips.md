---
Alias: Python Language Tips
Tag: python
Author: S.Sunhaloo
Type: Random Notes / Tips
Date: 2024-04-18
Status: HOLD
---

## List of Contents

- [[Python Tips#Read the First Line of Text File | Read the First Line of Text File]]

---

### My Links

- [[Python Tips#Socials | Links to Socials]]

---

# Read the First Line of Text File

Instead of using the normal `.read()` function; we are going to use the `.readline()` function.

```python

import os # To be able to use some features such as 'getcwd()'

# Get Current Directory
print()
print(f"Current Directory: '{os.getcwd()}'")
print()

print("Reading Contents of File:")

# Open Text File for Read using Context Manager
with open("Text_File.txt", 'r') as file:

    # DECLARE contents: STRING
    contents = file.readline()

    # Output the First Line of text file
    print(contents)

print('-'*34)

# Check if files have been closed
print(f"Is 'Text_File.txt' Closed? {file.closed}")

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