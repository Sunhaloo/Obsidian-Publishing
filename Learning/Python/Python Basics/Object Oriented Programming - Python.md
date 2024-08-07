---
Alias: Python OOP
Tag: python, basics
Author: S.Sunhaloo
Type: Computer OOP
Date: 2023-10-16
Status: In-Progress
---

## List of Contents

- [[Object Oriented Programming - Python#What is Computer Object Oriented Programming| What is Computer Object Oriented Programming]]
	- [[Object Oriented Programming - Python#Structure of OOP| Structure of OOP]]
	- [[Object Oriented Programming - Python#Principles of OOP| Principles of OOP]]
		- [[Object Oriented Programming - Python#Encapsulation| Encapsulation]]
		- [[Object Oriented Programming - Python#Abstraction| Abstraction]]
		- [[Object Oriented Programming - Python#Inheritance| Inheritance]]
		- [[Object Oriented Programming - Python#Polymorphism| Polymorphism]]
- [[Object Oriented Programming - Python#Computer Object Oriented Programming Codes| Start of Computer Object Oriented Programming]]
	- [[Object Oriented Programming - Python#Creating a Class| Creating A Class]]
		- [[Object Oriented Programming - Python#Example Create a class called "*Books*"| Example to Create Class]]
	- [[Object Oriented Programming - Python#Defining A Class| Defining A Class]]
		- [[Object Oriented Programming - Python#Constructor| Constructor Function]]
			- [[Object Oriented Programming - Python#Example Passing Values in Constructor| Making Constructor Example]]
		- [[Object Oriented Programming - Python#Attributes / Properties / Instance Variables| Attributes / Properties / Instance Variables]]
			- [[Object Oriented Programming - Python#Example Adding the Attributes ( *properties* ) of class "*Books*"| Adding Attributes Example]]
		- [[Object Oriented Programming - Python#Method / Getters ( Basically Functions and Procedures - Python Functions )| Method / Getters / Functions]]
			- [[Object Oriented Programming - Python#Example Getters / Methods / Functions| Example of Methods]]
		- [[Object Oriented Programming - Python#Creating an Object| Creating an Object]]
			- [[Object Oriented Programming - Python#Example: Creating Objects| Creating an Object Example]]
		- [[Object Oriented Programming - Python#Calling Methods / Getters / Functions| Calling Functions]]
		- [[Object Oriented Programming - Python#Class Variables| Class Variables]]
			- [[Object Oriented Programming - Python#Example Creating a Class Variable| Creating Class Variable Example]]
		- [[Object Oriented Programming - Python#Inheritance - Code | Inheritance - Code]]
			- [[Object Oriented Programming - Python#Example Inheriting Functions From Another Class ( Child Class $ Rightarrow$ Moto )| Examples of Inheritance]]
		- [[Object Oriented Programming - Python#Multilevel Inheritance| Multilevel Inheritance]]
			- [[Object Oriented Programming - Python#Example Inheriting Functions From Another Class ( Derived Class $ Rightarrow$ Small_Car )| Example of Multilevel Inheritance]]

---

# What is Computer Object Oriented Programming

Basically, whenever we think of "*OOP*"; we need to think **objects** ( like real world objects ).

We have:

- Objects: Which means "an entity that exists in the real world"

This is why we have *Computer **Object** Oriented Programming*

## Structure of OOP

- Classes
	- They are **user-defined** data types that acts as *blueprints* for objects, attributes, and methods
- Objects
	- These are **instances** of a class with *specifically* defined data types.
	- When a class is defined initially, the *description* is the **only** object that is defined
- Methods
	- These are **[[Functions and Procedures - Python | functions]]** that are defined **inside** a class that describe the behaviour of an object. They are useful for re-usability or keeping functionality *[[Object Oriented Programming - Python#Encapsulation| encapsulated]]* inside one object at a time.
- Attributes
	- These are *defined* in the **class template** and represent the **state** of an *object*
	- Objects contain data stored in the attribute field

>As you might have guessed, this is not my work; it is from [freeCodeCamp](https://www.freecodecamp.org/news/what-is-object-oriented-programming/)

## Principles of OOP

### Encapsulation:

It is the **binding** of data together. *Functions* **manipulate** the info and keep it safe. **No direct access** is granted to the info in case it is *hidden*.
To be able to access the information; you need to **interact** with the article in charge of that information.

### Abstraction:

It is the use of simple classes to represent complexity. Basically, we use abstraction to **hide** the *complex codes* by allowing the user to only see relevant information.

### Inheritance:

It allows other classes to follow the same *pattern* of other classes.
For Example:

Cars generally have 4 wheels and 4 doors ( excluding boot ); but so do *vans* and $4 \times 4$.

Hence, we could use the same bit of code from *cars*.

### Polymorphism:

This is the power of 2 **different** *objects* to reply to one form. Program will determine which usage is critical for every execution of the thing form the parent class which reduces code duplication.
It also allows different kinds of objects to interact with the same interface.

---

# Computer Object Oriented Programming Codes

>[!tip] Listen To Me
>I normally just write the part thar we need; example in:
>- [[Stack ADT - 1D Array ( Mine )#Functions| Stack Functions]]
>- [[Insertion Sort - Python#Template 1D-Array | Insertion Sort Function]]
>But as this is **Computer Object Oriented Programming**
>- I will be also writing the beginning of the code **each** time

# Creating a Class

To **create** a class in Python, you just need to type the following:

>[!tip] Usage
>```python
>class x:
>```

### Example: Create a class called "*Books*"

```python

# CLASS Books
class Books:

```

# Defining A Class

## Constructor

A "*constructor*" is a **special** [[Functions and Procedures - Python| function]] ( *method* ) that is automatically called when an *object* is created.

>[!note] Purpose
>To initialise the attributes ( *properties* ) of an object ( "*to be created*" ) and sets up its initial state

>[!tip] Python's Constructor Usage
>```python
># Constructor
># FUNCTION __init__(DECLARE self: self, DECLARE x: STRING, DECLARE y: INTEGER, DECLARE z: REAL)
>def __init__(self, x, y, z):
>```
>>[!note]
>>"*x*", "*y*", "*z*" are the *[[Functions and Procedures - Python#Parameters | parameters]]* that the user creates
>># But...
>>There is a special *parameter* that we need to pass:
>>```python
>>self
>>```
>>- It is the **first** parameter that we need to pass into the *brackets*

### Example: Passing Values in Constructor

>I am going to be continuing the "*Book*" class
>So that we can get a complete code at the end!

```python

# CLASS Books
class Books:

    # Constructor
    def __init__(self, name, author, editor, date_published):

        # For now, we need to explain "attributes"
        pass

```

## Attributes / Properties / Instance Variables

Attributes **represent** the *characteristics* / *properties* of **objects** in that class. I understand it like this:

- They are the things that an object has, example:
	- Names
	- Date
	- Engine Type
	- ...

### Example: Adding the Attributes ( *properties* ) of class "*Books*"

```python

# CLASS Books
class Books:

    # Constructor
    def __init__(self, name, author, editor, date_published):

        # Attributes / Properties / Instance Variable of Object
        self.name = name
        self.author = author
        self.editor = editor
        self.date_published = date_published

```

## Method / Getters ( Basically [[Functions and Procedures - Python | Functions]] )

What can I say, they are just function inside the class.

### Example: Getters / Methods / Functions

>[!warning]
>We **need** to pass "*self*" parameter

```python

# CLASS Books
class Books:

    # Constructor
    def __init__(self, name, author, editor, date_published, cost):

        # Attributes / Properties of Object
        self.name = name
        self.author = author
        self.editor = editor
        self.date_published = date_published
        self.cost = cost

    # Getters / Methods / Functions

    # FUNCTION display()
    def display(self):

        # Displaying the Attributes / Properties of objects
        print()
        print(f"Book Name: {self.name}")
        print(f"Author: {self.author}")
        print(f"Editor: {self.editor}")
        print(f"Date Published: {self.date_published}")
        print()

    # FUNCTION price()
    def price(self):

        print()
        print(f"Cost of {self.name} : {self.cost}")
        print()

```

## Creating an Object

There are 2 ( "*which I know right now*" ) ways of creating on object:

1. Programmer creates object **inside** the code
2. Programmer allows **user** create object

### Example: Creating Objects

```python

# CLASS Books
class Books:

    # Constructor
    def __init__(self, name, author, editor, date_published, cost):

        # Attributes / Properties of Object
        self.name = name
        self.author = author
        self.editor = editor
        self.date_published = date_published
        self.cost = cost

    # Getters / Methods / Functions

    # FUNCTION display()
    def display(self):

        # Displaying the Attributes / Properties of objects
        print()
        print(f"Book Name: {self.name}")
        print(f"Author: {self.author}")
        print(f"Editor: {self.editor}")
        print(f"Date Published: {self.date_published}")
        print()

    # FUNCTION price()
    def price(self):

        print()
        print(f"Cost of {self.name} : {self.cost}")
        print()

# DECLARE book_1: Books
# "book_1" is "written" by the "programmer"
book_1 = Books("How to Steal Like an Artist", "Austin Kleon", "Austin Kleon", "28 Febuary 2012", 21)

# "book_2" is "written" by the "user"
print()
print("Enter Book Details")
print()

# Asking the user to enter book details
# Exception Handling
try:

    book_name = input("Please Enter The Book Name: ")
    author_name = input("Please Enter The Name Of Author: ")
    editor_name = input("Please Enter The Editor Name: ")
    date_published = input("Please Enter Released Date: ")
    book_cost = float(input("Please Enter Price of Book: "))

# If user enters any other data type of for "cost"
except ValueError:

    # Output the appropriate message
    print()
    print("Please Enter Real Number Only For Cost Of Book!")
    print()

# DECLARE book_2: Books
# Creating "book_2"
book_2 = Books(book_name, author_name, editor_name, date_published, book_cost)

```

## Calling Methods /  Getters / Functions

In a way, you could also think of **methods** or **getters** as *actions*.

### Example: Calling our Functions

```python

# CLASS Books
class Books:

    # Constructor
    def __init__(self, name, author, editor, date_published, cost):

        # Attributes / Properties of Object
        self.name = name
        self.author = author
        self.editor = editor
        self.date_published = date_published
        self.cost = cost

    # Getters / Methods / Functions

    # FUNCTION display()
    def display(self):

        # Displaying the Attributes / Properties of objects
        print()
        print(f"Book Name: {self.name}")
        print(f"Author: {self.author}")
        print(f"Editor: {self.editor}")
        print(f"Date Published: {self.date_published}")
        print()

    # FUNCTION price()
    def price(self):

        print()
        print(f"Cost of {self.name} : {self.cost}")
        print()

# DECLARE book_1: Books
# "book_1" is "written" by the "programmer"
book_1 = Books("How to Steal Like an Artist", "Austin Kleon", "Austin Kleon", "28 Febuary 2012", 21)

# Creating another Object with identifier name "book_2"
# "book_2" is "written" by the "user"
print()
print("Enter Book Details")
print()

# Asking the user to enter book details
# Exception Handling
try:

    book_name = input("Please Enter The Book Name: ")
    author_name = input("Please Enter The Name Of Author: ")
    editor_name = input("Please Enter The Editor Name: ")
    date_published = input("Please Enter Released Date: ")
    book_cost = float(input("Please Enter Price of Book: "))

# If user enters any other data type of for "cost"
except ValueError:

    # Output the appropriate message
    print()
    print("Please Enter Real Number Only For Cost Of Book!")
    print()

# DECLARE book_2: Books
# Creating "book_2"
book_2 = Books(book_name, author_name, editor_name, date_published, book_cost)

print()

# Calling Methods / Functions

book_1.display()
book_1.price()

# For "book_2"
book_2.display()
book_2.price()

print()

```

## Class Variables

A **class variable**  is a variable that is shared among all instances ( *objects* ) of a class.
Unlike **[[Object Oriented Programming - Python#Attributes / Properties / Instance Variables| instances variables]]** which are *unique* to all objects; **class variables** are associated with the class rather than the instances of the class.

## Characteristics Includes:

- Shared Value
- Defined at Class Level ( "*normally just after writing class name*" )
- Accessed via the Class / Instances

>[!note]
>I will be using **another** example as from now
>This is so that I can explain you ( and myself ) better.

### Example: Creating a Class Variable

```python

# CLASS Car
class Car:

    # Class Variable
    # DECLARE wheels: INTEGER
    wheels = 4

```

### Accessing the Class Variable

To access the class variable, I will first complete the code, i.e;

- Defining the Class
- Making the constructor
- Making Methods / Functions
- Creating Objects

#### Accessing Class Variables

```python

# CLASS Car
class Car:

    # Class Variable
    # DECLARE wheels: INTEGER
    wheels = 4

    # Constructor
    def __init__(x, make, model, year, colour,):

    # Here the "self" has been replaced with "x"

        # Attributes / Properties
        x.make = make
        x.model = model
        x.year = year
        x.colour = colour

    # Our Methods / Functions / Getters

    # FUNCTION start()
    def start(x):

        print()
        print(f"{x.model} is starting its engine!")

    # FUNCTION warming()
    def warming(x):

        print()
        print(f"{x.model} is warming up")

    # FUNCTION drive()
    def drive(x):

        print()
        print(f"{x.model} is driving")

    # FUNCTION zooming()
    def zooming(x):

        print()
        print(f"{x.model} is going really fast")

# Creating Objects

# DECLARE car_1: Car
car_1 = Car("Mazda", "RX-7 FD", 1998, "Yellow")

# Displaying our "Class Variable"
print(f"car_1 has {car_1.wheels} wheels!")

# Changing the Class Variable "wheels" of the class `Car`
Car.wheels = 2

# Now, we have an updated class variable
print(f"car_1 has {car_1.wheels} wheels!")

```

## Inheritance - Code

We can make a class and create its [[Object Oriented Programming - Python#Method / Getters ( Basically Functions and Procedures - Python Functions )| methods]]. Now, what if we want to create **another** class that is **similar** to the class before.

What do I mean by *similar* is... Its function ( "*actions*" ) are the same.

### Example: Inheriting Functions From Another Class ( Child Class $\Rightarrow$ Moto )

```python

# CLASS Car
class Car:

    # Class Variable
    # DECLARE wheels: INTEGER
    wheels = 4

    # Constructor
    def __init__(x, make, model, year, colour,):

    # Here the "self" has been replaced with "x"

        # Attributes / Properties
        x.make = make
        x.model = model
        x.year = year
        x.colour = colour

    # Our Methods / Functions / Getters

    # FUNCTION start()
    def start(x):

        print()
        print(f"{x.model} is starting its engine!")

    # FUNCTION warming()
    def warming(x):

        print()
        print(f"{x.model} is warming up")

    # FUNCTION running()
    def running(x):

        print()
        print(f"{x.model} is running")

    # FUNCTION zooming()
    def zooming(x):

        print()
        print(f"{x.model} is going really fast")

# DECALRE car_1: Car
# Object with identifier name "car_1"
car_1 = Car("Mazda", "RX-7 FD", 1998, "Yellow")

# Displaying our "Class Variable"
print(f"car_1 has {car_1.wheels} wheels!")

# CLASS Moto(CLASS Car)
# Creating another class with the identifier name "Moto"
class Moto(Car):

    # Class Variable of class `Moto`
    # DECLARE wheels: INTEGER
    wheels = 2

    # Defining the class `Moto`
    # Constructor
    def __init_(self, make, model, engine_displacement, colour):

        # Attributes / Properties
        self.make = make
        self.model = model
        self.engine_displacement = engine_displacement
        self.colour = colour

    # Functions will be inherited from the class `Car`

# DECLARE moto_1: Moto
# Creating Objects for class `Moto`
moto_1 = Moto("Kawasaki", "H2", 998, "Carbon Black")

# Displaying the "Class Variable" of `Moto`
print(f"car_1 has {moto_1.wheels} wheels!")

# Calling Function for class `Moto`
# Inherits its function from the class `Car`

print()
print("Class Moto, Inherits Functions From Class Car")
print()

moto_1.start()
moto_1.running()
moto_1.warming()
moto_1.zooming()

print()

```

## Multilevel Inheritance

### Example: Inheriting Functions From Another Class ( Derived Class $\Rightarrow$ Small_Car )

```python

# CLASS Car
	# Parent Class
class Car:

    # Class Variable
    # DECLARE wheels: INTEGER
    wheels = 4

    # Constructor
    def __init__(x, make, model, year, colour,):

    # Here the "self" has been replaced with "x"

        # Attributes / Properties
        x.make = make
        x.model = model
        x.year = year
        x.colour = colour

    # Our Methods / Functions / Getters

    # FUNCTION start()
    def start(x):

        print()
        print(f"{x.model} is starting its engine!")

    # FUNCTION warming()
    def warming(x):

        print()
        print(f"{x.model} is warming up")

    # FUNCTION running()
    def running(x):

        print()
        print(f"{x.model} is running")

    # FUNCTION zooming()
    def zooming(x):

        print()
        print(f"{x.model} is going really fast")

# DECLARE car_1: Car
# Creating Objects for class `Car`
car_1 = Car("Mazda", "RX-7 FD", 1998, "Yellow")

# Displaying our "Class Variable"
print(f"car_1 has {car_1.wheels} wheels!")

# CLASS Moto(CLASS Car)
# Creating another class with the identifier name `Moto`
	# Child Class
# ( Moto <--- Car )
class Moto(Car):

    # Class Variable of class `Moto`
    # DECLARE wheels: INTEGER
    wheels = 2

    # Defining the class `Moto`
    # Constructor
    def __init_(self, make, model, engine_displacement, colour):

        # Attributes / Properties
        self.make = make
        self.model = model
        self.engine_displacement = engine_displacement
        self.colour = colour

    # Functions will be inherited from the class `Car`

# DECLARE moto_1: Moto
# Creating Objects for class `Moto`
moto_1 = Moto("Kawasaki", "H2", 998, "Carbon Black")

# Displaying the "Class Variable" of `Moto`
print()
print(f"moto_1 has {moto_1.wheels} wheels!")

# Calling Function for class `Moto`
# Inherits its function from the class `Car`

print()
print("Class Moto, Inherits Functions From Class Car")
print()

moto_1.start()
moto_1.running()
moto_1.warming()
moto_1.zooming()

print()

# CLASS Small_Car(CLASS Moto)
# Creating another class with the indentifier name "Small_Car"
	# Derived Class
# ( Small_Car <--- Moto <--- Car )
class Small_Car(Moto):

    # Class Variable of `Small_Car`
    # DECLARE wheel: INTEGER
    wheels = 4
    # DECLARE doors: INTEGER
    doors = 2

    # Constructor will be inherited from class "Moto" ( Moto <--- Car )
    # Function / Methods / Getters will be also inherited from "Moto" ( Moto <--- Car )

    # FUNCTION slow()
    def slow(self):

        print()
        print(f"{self.model} is going really slow")

# DECLARE car_2: Small_Car
# Creating Object for class `Small_Car`
car_2 = Small_Car("Honda", "Beat", 656, "Grey")

# Calling Function for class "Small_Car"
# Inherits its function from the class "Moto"

# Displaying the "Class Variable" of `Small_Car`
print(f"car_2 has {car_2.wheels} wheels!")
print(f"car_2 has {car_2.doors} doors!")

print()

print("Class Small_Car, Inherits Functions From Class Moto")

print()

car_2.start()
car_2.running()
car_2.warming()
car_2.slow()

print()

```

## Method Chaining

This is basically just writing the method is "*one line*", this is something that has to be shown to explain. Thus see the example below ( $\downarrow$ ).

### Example: Method Chaining

```python



```