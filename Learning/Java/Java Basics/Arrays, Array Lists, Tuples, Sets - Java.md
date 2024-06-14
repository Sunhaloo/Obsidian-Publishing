---
Alias: Arrays - Array Lists - Tuples - Sets in Java
Tag: java, basics, 1D-Array, 2D-Array
Author: S.Sunhaloo
Type:  Arrays ( 1D / 2D )
Date: 2024-06-12
Status: In-Progress
---

>This is the $2^{nd}$ iteration of "*Arrays, Tuples and Sets in Java*"
>This is because I was treating it like Python; I was trying to convert Python Codes in Java.
>This **won't** work here, we because we have:
>1. [[Java Language#Primitive Data Types | Primitive Data Types]]
>2. [[Java Language#Wrapper / Referenced Data Types | Wrapper / Referenced Data Types]]
>3. `import java.util.Arrays;`
>4. Array Lists ( `import java.util.ArrayList;` )
>- And more!
>
>Hence, I am going to proceed like I want, like my brain understands it!

## List of Contents

## One Dimensional Arrays

- [[Arrays, Array Lists, Tuples, Sets - Java#One Dimensional Arrays ( 1D-Arrays )| One Dimensional Arrays ( 1D-Arrays )]]
	- [[Arrays, Array Lists, Tuples, Sets - Java#Creating 1D-Arrays| Creating 1D-Arrays]]
	- [[Arrays, Array Lists, Tuples, Sets - Java#Displaying 1D-Arrays | Displaying 1D-Arrays]]

---

## List

- [[Arrays, Array Lists, Tuples, Sets - Java#Array Lists | Array Lists]]
	- [[Arrays, Array Lists, Tuples, Sets - Java#Creating An Array Lists | Create Array Lists]]
	- [[Arrays, Array Lists, Tuples, Sets - Java#Displaying Array Lists | Displaying Array Lists]]

---

### My Links

- [[Arrays, Array Lists, Tuples, Sets - Java#Socials| Link to Socials]]

---

# One Dimensional Arrays ( 1D-Arrays )

## Creating 1D-Arrays

### Primitive Data Types ( Creating Arrays )

>Refer to the comments inside the `code block` for explanation!

```java

// Primitive Arrays

public class Main {

    public static void main(String[] args) {

        // Primitive Data Types

        // First Method
            // use this method when:
                // 1. You know the size of the Array
                // 2. You know the values that will go into the Array
        // DECLARE ARRAY numbers[4]: INTEGER
            // in this case we have DECLARED and also INITIALISED our Array
        int[] numbers = {1, 2, 3, 4, 5};

        // Second Method
            // use this method when:
                // 1. You only know the size of the array
            // Hence, we can first DECLARE and then Later INITIALISE the array once you have the values
            // For example, when asking the user to input data into array, we only need to initialise it
        // DECLARE ARRAY characters[4]: CHAR
        char[] characters = new char[5];

        // after we get the values; we can populate the array
        characters[0] = 'a';
        characters[1] = 'b';
        characters[2] = 'c';
        characters[3] = 'd';
        characters[4] = 'e';

    }
    
}

```

### Object / Wrapper / Referenced Data Types ( Creating Arrays )

>I will be using the same code as above $\uparrow$, but this time with [[Java Language#Wrapper / Referenced Data Types | Object / Wrapper / Referenced]] datatypes.

```java

// Object / Wrapper Arrays

public class Main {

    public static void main(String[] args) {

        // Object / Wrapper Data Types

        // First Method
            // use this method when:
                // 1. You know the size of the Array
                // 2. You know the values that will go into the Array
        // DECLARE ARRAY numbers[4]: INTEGER
            // in this case we have DECLARED and also INITIALISED our Array
        Integer[] numbers = {1, 2, 3, 4, 5};

        // Second Method
            // use this method when:
                // 1. You only know the size of the array
            // Hence, we can first DECLARE and then Later INITIALISE the array once you have the values
            // For example, when asking the user to input data into array, we only need to initialise it
        // DECLARE ARRAY characters[4]: CHAR
        Character[] characters = new Character[5];

        // after we get the values; we can populate the array
        characters[0] = 'a';
        characters[1] = 'b';
        characters[2] = 'c';
        characters[3] = 'd';
        characters[4] = 'e';

    }
    
}

```

>[!note] [[Java Language#Equivalent of `type()` Function | Equivalent of `type()` Function]]
>We can check the "*type*" of an **Array**, using the `.getClass()` and `.getSimpleName()` methods; <span style="color: green;">without</span> converting to Object / Wrapper datatypes!
>>I will only include the Code Snippet not the *whole* code!
>```java
>System.out.println(numbers.getClass().getSimpleName());
>System.out.println(strs.getClass().getSimpleName());
>System.out.println(doubly_nums.getClass().getSimpleName());
>```

## Displaying 1D-Arrays

### Primitive Data Types ( Displaying Arrays )

```java

public class Main {

    public static void main(String[] args) {

        // Primitive Datatypes

        // DECLARE ARRAY numbers[4]: INTEGER
        int[] numbers = { 1, 2, 3, 4, 5 };

        System.out.println("\nMethod 1: Part 1\n");

        // Method 1
        // part 1: using simple `for` loop with `println` function
        // this method is not really used, because... frankly its shit
        for (int i = 0; i < 5; i++) {
            System.out.println(numbers[i]);
        }

        System.out.println("\nMethod 1: Part 2\n");

        // part 2: using `for` loop with `printf` function
        // this method is similar to displaying arrays in C!
        // DECLARE length_numbers: INTEGER
        // will hold the length of array `numbers`
        int length_numbers = numbers.length;
        // we can even make it like the `enumerate` function in Python
        for (int i = 0; i < length_numbers; i++) {
            System.out.printf("Index: %d | Value = %d\n", i, numbers[i]);
        }

        System.out.println("\nMethod 2: Part 1\n");

        // Method 2
        // part 1: using `for-each` loop and here we are using `println`
        // this will only print out the values of the array
        for (int i : numbers) {
            System.out.println(i);
        }

        System.out.println("\nMethod 2: Part 2\n");

        // part 2: using `for-each` and doing it like `enumerate` function in Python
        // DECLARE index: INTEGER
        int index = 0;
        for (int i : numbers) {
            System.out.printf("Index = %d | Value = %s\n", index++, i); // <--- using '%s' to display Object values
        }

        System.out.println();

    }

}

```

>[!tip]
>The best method for displaying Arrays is using the `for-each` loop / method.
>Because its easy and simple!
>>But sometimes I like to do using the like `enumerate` function, I think its better if you use `printf` and `for` loop method.

### Object / Wrapper / Referenced Data Types ( Displaying Arrays )

>[!note]
>Its the **same** as above $\uparrow$; we are just going to be using:
>```java
>// Declaration ONLY
>Integer[] array = new Integer[5];
>// Declaration and Initialisation
>Integer[] array = {1, 2, 3, 4, 5};
>```
>That's it, everything will **work** as expected!!!

# Adding Elements into 1D-Array

## Inserting Elements in 1D-Array

>[!note]
>This code is taken from [[Arrays - C#"Inserting" Elements into 1D-Array | C]]'s *insert value at specific location*.
>I will ( *need to* ) be explaining it after writing the code.

```java



```


# Array Lists

## Creating An Array Lists

>[!warning]
>To use Array Lists in Java, we need to first import the module / library / package
>```java
>import java.util.ArrayList;
>```

>I might use the Array List $=$ Lists, in general!

What are "*Lists*"? If you have used [[Arrays, Tuples, Sets - Python | Python]], then you are going to feel right at home.
Compared to *Arrays*, **Lists** are <span style="color: green;">dynamic</span>!

In addition, they behave exactly like Lists in Python, where you can add like different datatypes in the list like `list = ["String", 1, 1.2345, True, 'A']`

```java

// need to import module / library / package
import java.util.ArrayList;

public class Main {

    public static void main(String[] args) {

        // create ArrayList of type 'Object' with identifier name "array_list"
	        // with the type 'Object'; we are going to be able make it similar to Python's List
        // create our ArrayList
        ArrayList<Object> array_list = new ArrayList<Object>(); // <--- I do not know if you need to put 'Object' here

        // initialise our ArrayList with data
        array_list.add("First String Value");
        array_list.add(1);
        array_list.add("Second String Value");
        array_list.add(true);
        array_list.add(7.5);

    }
}

```

>[!note] [[Java Language#Equivalent of `type()` Function | Equivalent of `type()` Function]]
>Same thing as checking the "*type*" of Array, we are not going to check the *types* of Array List!
>```java
>// Equivalent of `type()` function
>System.out.println(array_list_object.getClass().getSimpleName());
>System.out.println(array_list_string.getClass().getSimpleName());
>System.out.println(array_list_integer.getClass().getSimpleName());
>System.out.println(array_list_double.getClass().getSimpleName());
>```

## Displaying Array Lists

```java

// need to import module / library / package
import java.util.ArrayList;

public class Main {

    public static void main(String[] args) {

        // create ArrayList of type Object with identifier name "array_list"
        ArrayList<Object> array_list = new ArrayList<Object>();

        // using method `add()` to add values into the array
        array_list.add("Object-String-1");
        array_list.add("Object-String-2");
        array_list.add(1);
        array_list.add(2);
        array_list.add(3);
        array_list.add(1.00);
        array_list.add(2.00);
        array_list.add(3.00);
        array_list.add(true);
        array_list.add(false);

        // removing objects
        // NOTE: the `.remove()` function; uses the INDEX of the value
        // then it goes to that index and then removes it
        array_list.remove(0);
        array_list.remove(8);

        System.out.println("\nMethod 1: Single Line\n");

        // Method 1: Display using a `println` function
        System.out.println("List = " + array_list);

        System.out.println("\nMethod 2: Using `for-each` Loop\n");

        // Method 2: Display contents using `for-each` loop
        // because Array Lists are Objects, we need our counter `i` to also be an Object
        for (Object i : array_list) {
            System.out.println(i);
        }

        System.out.println("\nMethod 3: Doing it like the `enumerate` function in Python\n");

        // Method 3: Making it like the `enumerate` function from Python
        // DECLARE size_ArrayList: INTEGER
        int size_ArrayList = array_list.size();

        for(int i = 0; i < size_ArrayList; i++) {
            // the `.get(i)` will "get" the values of each index from the array
            // we are using the format specifier `%s`; because we have created an ArrayList of Objects!
            System.out.printf("Index: %d | Value = %s\n", i, array_list.get(i));
        }

        System.out.println();

    }

}

```

---

# Socials

- [**Instagram**](https://www.instagram.com/s.sunhaloo/)
- [**YouTube**](https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg)
- [**GitHub**](https://www.github.com/Sunhaloo)

---

S.Sunhaloo
Thank You!