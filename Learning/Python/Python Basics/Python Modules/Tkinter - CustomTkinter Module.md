---
Alias: Python GUI Modules
Tag: python, basics, python_module
Author: S.Sunhaloo
Type: Module
Date: 2024-04-21
Status: In-Progress
---

>[!note]
>This will not be like any other notes that I have made.
>Instead I will focusing on creating an app. Hence, I will still get the experience and just learn the things that I need and not be a fool and learn every single syntax.

## List of Contents

### Tkinter

- [[Tkinter - CustomTkinter Module#Install CustomTkinter | Install CustomTkinter]]
- [[Tkinter - CustomTkinter Module#Hello World in Tkinter | Hello World]]
- [[Tkinter - CustomTkinter Module#Buttons | Buttons]]
- [[Tkinter - CustomTkinter Module#Input Fields - Text Boxes | Input Fields - Text Boxes]]
- [[Tkinter - CustomTkinter Module#Grid Layout | Grid Layout]]
- [[Tkinter - CustomTkinter Module#Customisation | Customisation]]

---

### CustomTkinter

- [[Tkinter - CustomTkinter Module#CustomTkinter | CustomTkinter]]

---

### My Links

- [[Tkinter - CustomTkinter Module#Socials | Link to Socials]]

---

>[!info]
>Official Documentations of CustomTkinter are found at: https://customtkinter.tomschimansky.com/

# Install CustomTkinter

```console

pip install customtkinter

```

# Hello World in Tkinter

```python

# import tkinter
import tkinter

# create application window
# need to create this first ---> so that we can get a window appear
root = tkinter.Tk()
# add a name to the application window
root.title("First Program")
# make a defined size for the window
root.geometry("400x700")

# write something in the app
my_label = tkinter.Label(root, text="Hello World", font=("Helvetica", 20))
# display `my_label` onto the screen / app window ---> Outputs to Screen
my_label.pack()

# loop the app / run the app
root.mainloop()

```

The `root.mainloop()` will run the program, we need this because the program need to be able to communicate things like **mouse positions** and be able to resize the GUI app.

```python

# import tkinter; use keywork `tk` instead of `tkinter`
import tkinter as tk

# create application window
# need to create this first ---> so that we can get a window appear
root = tk.Tk()
# add a name to the application window
root.title("Centering Text")
# make a defined size for the window
root.geometry("700x400")

# write something in the app
hello_world = tk.Label(root, text="Hello World!", font=("Helvetica", 20))
my_name = tk.Label(root, text="My name is S.Sunhaloo", font=("JetBrainsMono NF Regular", 20))
text = tk.Label(root, text="This is on row 2 and column 1", font=(("RobotoMono Nerd Font", 10)))
blank_line = tk.Label(root, text="")

# outputs to the CENTER of Screen
hello_world.grid(row=0, column=0)
my_name.grid(row=0, column=1)
# output the blank line at row 1 and column 1
blank_line.grid(row=1, column=1)
text.grid(row=2, column=1)

# loop the app / run the app
root.mainloop()

```

Here we have used the `.grid()` method to output stuff to our screen. Even if you want to use the `.pack` method; you will <span style="color: red;"><strong>not</strong></span> be able to use it.

## Buttons

```python

# import tkinter; use keywork `tk` instead of `tkinter`
import tkinter as tk

# FUNCTION button_does_nothing() ---> will not do anything
def button_does_nothing():

    pass

# FUNCTION button_quits() ---> will close down the app
def button_quits():

    # quits the app
    root.quit()

# create application window
# need to create this first ---> so that we can get a window appear
root = tk.Tk()
# add a name to the application window
root.title("Centering Text")
# make a defined size for the window
root.geometry("500x100")

# make a button that does nothing
big_nothing_button = tk.Button(root, text="Nothing Button", padx=20, pady=20, command=button_does_nothing, font=("Helvetica", 20))
button_close = tk.Button(root, text="Close Button", command=button_quits, font=("Helvetica", 20))
blank_column = tk.Label(root, text="", width=10)

# output to screen
big_nothing_button.grid(row=0, column=0)
blank_column.grid(row=0, column=1)
button_close.grid(row=0, column=2)

# loop the app / run the app
root.mainloop()

```

### Opening Applications ( Windows + Executable Programs )

File `functions.py` will hold the functions ( *button commands* ) of program

```python

import os
import subprocess

def application():

	# opens thorium browser
	subprocess.Popen(['C:/Users/Azmaan/Appdata/Local/Thorium/Application/thorium.exe'])

def notepad():

    os.system('notepad.exe')

```

File `main.py` will be responsible of creating and managing the GUI

```python

import tkinter as tk # GUI
# Import Functions from `funciton.py` file
from functions import *

root = tk.Tk()
root.title("Application")
root.geometry("500x500")

# button for opening Notepad
windows_notepad = tk.Button(root, text="Open Notepad", font=(("Helvetica", 14)), command=notepad)
# button for opening Browser
browser = tk.Button(root, text="Open Browser", font=(("Arial", 10)), command=application)
# output Buttons to screen
windows_notepad.grid()
browser.grid()

root.mainloop()

```

## Input Fields - Text Boxes

### Simple Input Example

This code below $\downarrow$ will make the user enter some *text* into an input box. In addition, there will be a button; when the user presses that button. I will output whatever the fuck the user entered above.

```python

import tkinter as tk

# create window
root = tk.Tk()
# application / window title
root.title("Application")
# window start size
root.geometry("500x500")

# create input field / box
input = tk.Entry(root)

# output input field on screen
input.pack()

root.mainloop()

```

### Display the User Input in GUI / Window

Normally, when you use the function `tk.Entry()`, all things that the user will type will be displayed into the VS Code terminal... ( *does note actually displays anything if you run it from just OS's terminal* )
To display the text that the user entered; use the function below:

```python

# where `x` is the Input Field / Entry Point
# x = tk.Entry(root, ...)
x.get()

```

#### Display the User's Input ( Continues to Display it )

>The following code below $\downarrow$ was not done in VS Code, but instead the glorious, greatest editor of all time <span style="color: #69A33E;">Neo</span><span style="color: #3E93D3;">vim</span>

```python

import tkinter as tk

# FUNCTION get_user_input_label()
def get_user_input_label():
    # get text from input box
    user_text_label = user_input.get()
    # create first Label
    first_label = tk.Label(
        root,
        text=f"Text Entered(First Label): {user_text_label}",
        bg="black",
        fg="white",
    )
    # DECLARE message: STRING
    message = "Text Entered(Second Label):"
    second_label = tk.Label(
        root, text=f"{message}: {user_text_label}", bg="black", fg="white"
    )
    # create blank line
    blank_line = tk.Label(root, text="", bg="black", fg="white")
    # output to screen
    first_label.pack()
    blank_line.pack()
    second_label.pack()

# create window
root = tk.Tk()
# application / window title
root.title("Application")
# window start size
root.geometry("800x800")
# change the window background color to black
root.configure(bg="black")

# create input field
user_input = tk.Entry(
    root,
    font=(("Helvetica", 20)),
    justify="center",
    bd=2,
    bg="lightgrey",
    fg="black",
    width=50,
)

# display user input with `Label`
display_label = tk.Button(
    root,
    text="Ouput Using Label",
    font=(("JetBrainsMono NF Regular", 20)),
    bd=2,
    bg="white",
    fg="black",
    command=get_user_input_label,
)

# display the input box
user_input.pack(padx=50, pady=50)
# display button on GUI / window
display_label.pack()

root.mainloop()

```

#### Display the User's Input ( Overwrites Every Time )

Now, this code was given to me by ChatGPT

```python

import tkinter as tk

# FUNCTION get_user_input()
def get_user_input():
    # get text from input box
    message = user_input.get()
    # output the user's input with a message before it
    output_label.config(text=f"Message: {message}", bg="black", fg="white")
    # output the message
    output_label.pack()

# create window
root = tk.Tk()
# application / window title
root.title("Application")
# window start size
root.geometry("800x800")
# change the window background color to black
root.configure(bg="black")

# create input field
user_input = tk.Entry(
    root,
    font=(("Helvetica", 20)),
    justify="center",
    bd=2,
    bg="lightgrey",
    fg="black",
    width=50,
)

# display user input with `Label`
display_button = tk.Button(
    root,
    text="Ouput Using Label",
    font=(("JetBrainsMono NF Regular", 20)),
    bd=2,
    bg="white",
    fg="black",
    command=get_user_input,
)

# display input box / input field
user_input.pack(padx=20, pady=20)
# display the button
display_button.pack()
# output the user's input on GUI / tkinter
# by creating a label ---> using same name as above i.e `messsage`
output_label = tk.Label(root, font=(("Impact", 16)), bd=2, bg="black", fg="white")

root.mainloop()

```

>[!info]
>In this situation, the `.config` means that the text displayed will be overwritten.
>In the first code above $\uparrow$

## Grid Layout

We normally use the `grid()` function to display the widgets on screen / application window. But we can also define a grid layout... think of this like window managers such as i3, Hyprland and more.

### Define Grid

To define a grid, we normally use the functions `x.columnconfigure()` and `x.rowconfigure()`.

>Where `x` is the `root` or `window`!
>If you do <span style="color: red;">not</span> have `x`; the code will not work. I mean what the fuck are you doing with "*tkinter*" if you do not even have `root`!

```python

import os
import tkinter as tk

# FUNCTION quit_app():
# will be a function that will quit the appe ---> used with button `display_button`
def quit_app():
    # command to quit the app
    root.quit()

# FUNCTION open_notepad():
# will be responsible for opening notepad
def open_notepad():
    # open notepad
    os.system("notepad.exe")

# FUNCTION open_calc():
# will be responsible for opening calculator
def open_calc():
    # open calculator
    os.system("calc.exe")

# create window
root = tk.Tk()
# application / window title
root.title("Grid Layout")
# window start size
root.geometry("1280x720")

# create a button to quit app
quit_button = tk.Button(
    root,
    text="Quit App",
    font=(("JetBrainsMono NF Regular", 14)),
    bd=4,
    bg="white",
    fg="black",
    relief="groove",
    command=quit_app,
)

# create button to open notepad
open_notepad_button = tk.Button(
    root, text="Open Notepad", font=(("Helvetica", 20, "bold")), command=open_notepad
)

# create button to open calculator
open_calc_button = tk.Button(
    root, text="Open Calculator", font=(("Helvetica", 20, "bold")), command=open_calc
)

# create a label / message
text1 = tk.Label(
    root,
    text="This is A Label",
    font=(("Arial", 10, "italic")),
    bg="black",
    fg="white",
    bd=4,
    relief="solid",
)

# define the grid layout
root.columnconfigure(0, weight=1)
root.columnconfigure(1, weight=1)
root.rowconfigure(0, weight=1)
root.rowconfigure(1, weight=1)

# display the widgets
quit_button.grid(row=1, column=1)
open_notepad_button.grid(row=0, column=0)
open_calc_button.grid(row=0, column=1)
text1.grid(row=1, column=0)

root.mainloop()

```

In the code above we have create something like this:

![[Tkinter Grid Layout Image.png | 400]]

### Grid: Sticky Situation

Now we know to how create layouts we can; we can now move things inside the layouts

#### Modified GUI

We have the image above $\uparrow$, now take a look below $\downarrow$.

![[Tkinter Sticky.png | 350]]

Where now going to become exceptionally good navigators. Remember "*Never Eat See Weed*"; yeah, we have North, East, South and West in Python!!!

We just need to add the argument `sticky` which takes values `n`, `e`, `s`, `w` or a combination of these *locations*; in the function `.grid()`

```python

import os
import tkinter as tk

# FUNCTION quit_app():
# will be a function that will quit the appe ---> used with button `display_button`
def quit_app():
    # command to quit the app
    root.quit()

# FUNCTION open_notepad():
# will be responsible for opening notepad
def open_notepad():
    # open notepad
    os.system("notepad.exe")


# FUNCTION open_calc():
# will be responsible for opening calculator
def open_calc():
    # open calculator
    os.system("calc.exe")

# FUNCTION open_mspaint():
# will be responsible for opening calculator
def open_mspaint():
    # open Microsoft Paint
    os.system("mspaint.exe")

# create window
root = tk.Tk()
# application / window title
root.title("Sticky Situation")
# window start size
root.geometry("1280x720")

# create button1
button1 = tk.Button(
    root,
    text="Paint", 
    font=(("Arial", 20)), 
    bd=2,
    relief="flat",
    fg="green",
    padx=10, 
    pady=10,
    command=open_mspaint
)

# create button2
button2 = tk.Button(
    root,
    text="Notepad", 
    font=(("Arial", 20)), 
    bd=2,
    relief="solid",
    fg="green",
    command=open_notepad
)

# create button3
button3 = tk.Button(
    root,
    text="Calculator", 
    font=(("Arial", 20)), 
    bd=2,
    relief="groove",
    fg="green",
    command=open_calc
)

# create button4
button4 = tk.Button(
    root,
    text="Quit", 
    font=(("Arial", 20)), 
    bd=2,
    relief="ridge",
    fg="green",
    command=quit_app
)

# define a simple 4 square grid
root.columnconfigure(0, weight=1)
root.columnconfigure(1, weight=1)
root.rowconfigure(0, weight=1)
root.rowconfigure(1, weight=1)

# display the widgets
button1.grid(row=0, column=0, sticky="nw")
button2.grid(row=0, column=1, sticky="ne")
button3.grid(row=1, column=0, sticky="sw")
button4.grid(row=1, column=1, sticky="se")

root.mainloop()

```

### Combination Sticking

```python

import tkinter as tk

# create window
root = tk.Tk()
# application / window title
root.title("Sticky Situation")
# window start size
root.geometry("1280x720")

# create widgets
label1 = tk.Label(
    root,
    text="Label 1",
    font=(("", 20)),
    bg="black",
    fg="white"
)

label2 = tk.Label(
    root,
    text="Label 2",
    font=(("", 20)),
    bg="white",
    fg="black"
)

label3 = tk.Label(
    root,
    text="Label 3",
    font=(("", 20)),
    bg="green",
    fg="black"
)

labelx = tk.Label(
    root,
    text="Label x",
    font=(("", 20)),
    bg="yellow",
    fg="blue",
    borderwidth=2,
    relief="solid"
)

button1 = tk.Button(
    root,
    text="Button 1",
    font=(("", 20)),
    bd=2,
    relief="groove"
)

button2 = tk.Button(
    root,
    text="Button 2",
    font=(("", 20)),
    bd=2,
    relief="groove"
)

# define a simple 4 square grid
root.columnconfigure(0, weight=1)
root.columnconfigure(1, weight=1)
root.rowconfigure(0, weight=1)

# display the widgets
# `label1` fill the whole fucking shit
label1.grid(row=0, column=0, sticky="nesw")
label2.grid(row=0, column=0, sticky="n")
label3.grid(row=0, column=0, sticky="swe")
button1.grid(row=0, column=0, sticky="w")
button2.grid(row=0, column=0, sticky="e")
labelx.grid(row=0, column=1)

root.mainloop()

```

You will get this:

![[Tkinter North, East, South, West.png | 650]]

### Grid: Weight

>Changing the size of each grid layout; think of it like resizing application on windows managers!

Modifying this one line from the above code, we get:

```python

# change the weight of column
root.columnconfigure(0, weight=10)

```

This will result in this $\downarrow$:

![[Tkinter Grid Weight.png | 650]]

## Canvas

### Create A Simple "Window" / Area

This code below $\downarrow$ will create a simple black "*window*" will the word *Hello* displayed in the middle of it.

```python

import tkinter as tk

# create window
root = tk.Tk()
# application / window title
root.title("Canvas")
# window start size
root.geometry("1280x720")

# create a window / "rectangle"
window1 = tk.Canvas(root, bg="black")
label = tk.Label(root, text="Hello", bg="white", fg="black", font=(("Helvetica", 20)))

# define the window ---> to window it in the middle of screen
root.columnconfigure(0, weight=1)
root.rowconfigure(0, weight=1)

# display the rectangle
window1.grid()
# display the label inside the black window
label.grid(row=0, column=0)

root.mainloop()

```

## Customisation

>[!note]
>You can use Hexadecimal Colour Codes for customising the colours!
>You can use HSL, but it will be more complicated as you have to convert these HSL colours into RGB
>>Just fucking use *Hex* colour codes!

### Window / Application-Windows Customisations

#### Change Title

```python
import tkinter as tk

# create application window
root = tk.Tk()
# change the title
root.title("Insert Program Name Here")

root.mainloop()

```

#### Change Start Size

```python
import tkinter as tk

# create application window
root = tk.Tk()
# change the window size
root.geometry("1920x1080")

root.mainloop()

```

#### Change Window Background Color

```python

import tkinter as tk

# create application window
root = tk.Tk()
# background color = black
root.configure(bg="black")

root.mainloop()

```

### Label Customisations

#### Change Font and Font Size

```python

import tkinter as tk

# create application window
root = tk.Tk()

# create text / label
text1 = tk.Label(root, text="Change Font and Font Size", font=(("JetBrainsMono NF Regular", 12)))

# output text on screen
text1.pack() # or use `text1.grid()`

root.mainloop()

```

#### Change Color ( Background and Foreground )

Where:

- `bg` = background / padding colour
- `fg` = font colour

```python

import tkinter as tk

# create application window
root = tk.Tk()

# create text / label
text1 = tk.Label(root, text="Change Colour", bg="black", fg="white")

# output text on screen
text1.pack() # or use `text1.grid()`

root.mainloop()

```

# CustomTkinter

## Simple CustomTkinter Program

```python

import customtkinter as ctk

# create window of program
root = ctk.CTk()
# define the size of program window
root.geometry("1280x720")

# create a label
hello_world_label = ctk.CTkLabel(root, text="Hello World", font=(("Arial", 20)))

# configure the window
root.columnconfigure(0, weight=1)
root.rowconfigure(0, weight=1)

# display the label
hello_world_label.grid()

root.mainloop()

```

## Change the Theme of Window / Application Window

There are 3 options to this:

1. System Theme
	- will use the current system theme
2. Dark
3. Light

```python

import customtkinter as ctk

# use 'System' Theme
ctk.set_appearance_mode("system")

# use 'Dark' Theme
ctk.set_appearance_mode("dark")
# use 'Light' Theme
ctk.set_appearance_mode("light")

```

```python

import customtkinter as ctk

# uses dark theme for window
ctk.set_appearance_mode("dark")

# create window of program
root = ctk.CTk()
# define the size of program window
root.geometry("1280x720")

# create a label
hello_world_label = ctk.CTkLabel(root, text="Hello World", font=(("Arial", 20)))

# configure the window
root.columnconfigure(0, weight=1)
root.rowconfigure(0, weight=1)

# display the label
hello_world_label.grid()

root.mainloop()

```

## Change the Color of Widgets

### Using Default Values

The default values are `blue` ( *default* ), `green` and `dark-blue`

```python

import customtkinter as ctk

# set color theme to 'blue'
ctk.set_default_color_theme("blue")

# set color theme to 'green'
ctk.set_default_color_theme("green")

# set color theme to 'dark-blue'
ctk.set_default_color_theme("dark-blue")

```

>[!note]
>You can create your own custom theme, but you need to create it using this template:
>**URL:** https://github.com/TomSchimansky/CustomTkinter/blob/master/customtkinter/assets/themes/dark-blue.json

## CustomTkinter Grid Layout

Remember the notes for the [[Tkinter - CustomTkinter Module#Grid Layout | Tkinter Grid Layout]]...Basically in CustomTkinter, we use the same fucking function to define a grid layout.

>At least something that is not new so that I can try to remember it!

## Widgets

To be honest, there are more options that are available in CustomTkinter that in Tkinter ( *vanilla* ); I suggest you take a look at the documentation for widgets [here](https://customtkinter.tomschimansky.com/documentation/widgets)


## Hide Label After Certain Amount of Time

### Method 1: Using `.grid_forget()` Function

```python

import customtkinter as ctk

# FUNCTION hide_label()
def hide_label():
    # hide the label1
    label1.grid_forget()

ctk.set_appearance_mode("system")
ctk.set_default_color_theme("green")

root = ctk.CTk()
root.geometry("1280x720")
root.title("Hide Labels After 'x' Time")

# create widgets

# create a label
label1 = ctk.CTkLabel(
    root,
    text="Will Disappear in 5 Second",
)

# define the grid layout
root.rowconfigure(0, weight=1)
root.columnconfigure(0, weight=1)

# display widgets
label1.grid(row=0, column=0)
label1.after(5000, hide_label)

root.mainloop()

```

### Method 2: Using `.configure(text="")` Function

```python

import customtkinter as ctk

# FUNCTION hide_label()
def hide_label():
    # hide the label1
    label1.configure(text="")

ctk.set_appearance_mode("system")
ctk.set_default_color_theme("green")

root = ctk.CTk()
root.geometry("1280x720")
root.title("Hide Labels After 'x' Time")

# create widgets

# create a label
label1 = ctk.CTkLabel(
    root,
    text="Will Disappear in 5 Second",
)

# define the grid layout
root.rowconfigure(0, weight=1)
root.columnconfigure(0, weight=1)

# display widgets
label1.grid(row=0, column=0)
label1.after(5000, hide_label)

root.mainloop()

```

### Example: Hide Label after Button Press

```python



```

---

# Socials

- [**Instagram**](https://www.instagram.com/s.sunhaloo/)
- [**YouTube**](https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg)
- [**GitHub**](https://www.github.com/Sunhaloo)

---

S.Sunhaloo
Thank You!