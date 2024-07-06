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
	- [[Arrays, Array Lists, Tuples, Sets - Java#Adding Elements into 1D-Array | Adding Elements into 1D-Array]]
		- [[Arrays, Array Lists, Tuples, Sets - Java#"*Inserting*" Elements in 1D-Arrays | "Inserting" Elements in 1D-Arrays]]
		- [[Arrays, Array Lists, Tuples, Sets - Java#"*Appending*" Elements in 1D-Arrays | "Appending" Elements in 1D-Arrays]]
	- [[Arrays, Array Lists, Tuples, Sets - Java#Deleting Elements From 1D-Arrays | Deleting Elements From 1D-Arrays]]
		- [[Arrays, Array Lists, Tuples, Sets - Java#"*Popping*" Elements From 1D-Arrays | "Popping" Elements From 1D-Arrays]]
		- [[Arrays, Array Lists, Tuples, Sets - Java#"*Removing* Elements From 1D-Arrays | "Removing" Elements From 1D-Arrays]]

---

## List

- [[Arrays, Array Lists, Tuples, Sets - Java#Array Lists | Array Lists]]
	- [[Arrays, Array Lists, Tuples, Sets - Java#Creating An Array Lists | Create Array Lists]]
	- [[Arrays, Array Lists, Tuples, Sets - Java#Displaying Array Lists | Displaying Array Lists]]
	- [[Arrays, Array Lists, Tuples, Sets - Java#Adding Elements into Arrays Lists | Adding Elements into Arrays Lists]]
		- [[Arrays, Array Lists, Tuples, Sets - Java#"*Inserting*" Elements into Array Lists | "Inserting" Elements into Array Lists]]
		- [[Arrays, Array Lists, Tuples, Sets - Java#"*Appending*" Elements in Array Lists | "Appending" Elements in Array Lists]]

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

## Adding Elements into 1D-Array

### "*Inserting*" Elements in 1D-Arrays

>[!note]
>This code is taken from [[Arrays - C#"Inserting" Elements into 1D-Array | C]]'s *insert value at specific location*.
>I will ( *need to* ) be explaining it after writing the code.
>>[!note] Another NOTE... What?!?
>>Today is the 3rd of July 2024 @20:26.
>>I have restarted the making of notes for [[Java Data View | Java]].
>>I have updated that $\uparrow$ C code that I was talking about... This Java version is so much better.

```java

// import Scanner Object
import java.util.Scanner;
public class Main {
    public static void main(String[] args) {

        // create Scanner Object
        Scanner user_input = new Scanner(System.in);

        // DECLARE ARRAY numbers[99]: INTEGER
            // set an abitary high number ( size of array )
            // so that user will not get any problem inserting like 50 items
        int[] numbers = new int[100];

        // Exception Handling
        try {

            // ask the user to enter the amount of numbers he would like to input
            System.out.print("\nPlease Enter Amount of Values to Store: ");
            // DECLARE number_amount: INTEGER
            int number_amount = user_input.nextInt();

            // check if amount to be stored is in range
            if(number_amount <= 0 || number_amount >= 101) {
                // output appropriate message
                System.out.printf("\nAmount to Input '%d' is Out of Bounds\n\n", number_amount);
                // exit the program
                    // this is similar to `exit()` in Python
                System.exit(0);
            }

            System.out.println();

            // ask the user to enter the values into array
            // in the "range" that he specified ( `number_amount` )
            // DECLARE i: INTEGER
            for(int i = 0; i < number_amount; i++) {
                System.out.print("Please Enter Value ( i = " + i + " ): ");
                numbers[i] = user_input.nextInt();
            }

            System.out.println("\nContents of Array\n");

            // output the content of the array
            for(int i = 0; i < number_amount; i++) {
                System.out.printf("Index = %d | Value = %d\n", i, numbers[i]);
            }

            System.out.println();

            // ask the user to enter insert position
            // DECLARE insert_position: INTEGER
            System.out.print("Please Enter Insert Position for New Value: ");
            int insert_position = user_input.nextInt();

            // check if insert positio is in range
            if(insert_position <= 0 || insert_position >= 101) {
                // output appropriate message
                System.out.printf("\n\nInsert Position '%d' is Out of Bounds!\n\n", insert_position);
                // exit the program
                System.exit(0);
            }

            // because user does not know about how arrays work
            // we are going to decrement the value for `insert_position` by 1
            insert_position--;

            // ask the user to enter the actual value
            // DECLARE insert_value: INTEGER
            System.out.print("Please Enter Value to Insert: ");
            int insert_value = user_input.nextInt();

            // swapping values until desired input position is found
            for(int x = number_amount; x > insert_position; x--) {
                numbers[x] = numbers[x - 1];
            }

            // add the "new" value in that spot
            numbers[insert_position] = insert_value;

            // increase the bounds of array
            number_amount++;

            System.out.println("\nContents of Array After Insertion\n");

            // outputs the content of the array
            for(int i = 0; i < numbers.length; i++) {
                // check if number at index `i` is NOT equal zero
                if(numbers[i] != 0) {
                    // if NOT equal to '0' then, output that value together with index
                    System.out.printf("Index = %d | Value = %d\n", i, numbers[i]);
                }
            }

        } catch (java.util.InputMismatchException e) {
            // output suitable message
            System.out.println("\nPlease Enter Integer Numbers Only!!!\n");
        }

        finally {
            // close the Scanner Object
            user_input.close();
        }

    }
}

```

#### Explanation for "*Inserting*" Data into 1D-Arrays

>BTW when I say inserting, I am referring to the [[Arrays, Tuples, Sets - Python#Inserting Elements in 1D-Array | `.insert()`]] function from Python. When the user will enter values in this format `.insert(index, value)`
>As you know we do not have these function in C... yeah C, because when you are using **arrays**, they are from C while Python's arrays are actually **lists**.
>>[!tip] Summary
>>Java Arrays:
>>- Size is Static
>>- **Manual** management required for insertion, deletion and more
>>
>>Java Array Lists ( *similar to Python's Lists* ):
>>- Dynamic Size
>>- Uses built-in method for various operations
>
>Don't worry I did not forget about the Explanation, its below $\downarrow$

So we created an Empty array called `numbers` where we have set the size to 100.
Then we ask the user to enter the **amount** of *items* / values to enter. The program will check if the *amount* is in range. If so the program will allow the user to **input** the integer data that he wants.

After that the program will ask the user to enter an `insert_position` and what `insert_value` to enter at *that* position. Then the program will swap all the value starting from the "*top*" going down. When the *input position* is reached, it will take that value and `number_amount` ( *array size* ) will increase

>[!warning]
>Java Array are **NOT** *empty*.
>They have default values like `0`, `0.0` and null
>Because if you run this code below $\downarrow$:
>```java
>int[] numbers = new int[5]
>
>for(int i : numbers) {
>	System.out.println(i);
>}
>```
>Its going to output:
>```console
>0
>0
>0
>0
>0
>```

Hence, we need to iterate through **every** value in `numbers` and then check if the value at the index is $\neq$ '0'. If so output the value with the index at which the value is stored.

>Simple as that!!!

### "*Appending*" Elements in 1D-Arrays

Now we are going to append the elements into the array; What does *append* means?
All the elements that we are going to add will be added at the **end** of the array.

>This is similar to the `.append()` function in [[Arrays, Tuples, Sets - Python#Appending Elements into 1D-Array | Python]].

```java

// import Scanner Object
import java.util.Scanner;
// import package `InputMismatchException` for Exception Handling
import java.util.InputMismatchException;
public class App {

    // FUNCTION display(DELCARE ARRAY array[length_array]: INTEGER, DECLARE length_array: INTEGER)
    public static void display(int[] array) {

        // check if the array is filled with the number '0' or not
        boolean isEmpty = true;
        // DECLARE i: INTEGER
        for(int i : array) {
            // if value at index 'i' is NOT equal to '0'
            // meaning array is not "empty"
            if( i != 0) {
                isEmpty = false;
                break;
            }
        }

        // if `isEmpty = true` ---> meaning array is filled with '0'
        if(isEmpty) {

            // if array is contains only the number '0'; output the following message
            System.out.println("Array is Empty\n");

        }
        // `isEmpty = false` ---> meaning array is NOT filled with '0'
        else {

            // if array in NOT filled with '0'
            // output the contents of array
            for(int i = 0; i < array.length; i++) {
                // output the index and value at that index
                System.out.printf("Index = %d | Value: %d\n", i, array[i]);
            }

        }

    }

    // FUNCTION main(ARRAY of String as Arguments)
    public static void main(String[] args) throws Exception {

        // create Scanner Object
        Scanner user_input = new Scanner(System.in);

        // ask the user to enter the size of array
        System.out.print("\nPlease Enter Size of Array: ");
        // DECLARE array_size: INTEGER
        int array_size = user_input.nextInt();

        /*
         * similar to C, we need to ask the user for the size of array
         * then we are able to create the array
         * if not, we are going get an error; because its not in "memory"
         */

        // DECLARE ARRAY numbers[array_size]: INTEGER
        int[] numbers = new int[array_size];

        System.out.println("\nContents of Array\n");

        // call the function `display`
        display(numbers);

        // ask the user to enter integer values in array
        try {

            // DECLARE i: INTEGER
            for(int i = 0; i < numbers.length; i++){
                System.out.print("Please Enter A Value: ");
                // DECLARE user_num: INTEGER
                numbers[i] = user_input.nextInt();
            }

        }
        // code block that will run if program catches and exception
        catch(InputMismatchException e) {

            // output an appropriate message
            System.out.println("\nPlease Enter Integer Values Only!\n");

        }
        // code block that is always run
        finally {

            // close the Scanner Object
            user_input.close();

        }

        System.out.println("\nContents of Array\n");

        // call the function `display` again to
        // output the updated contents of array
        display(numbers);

        System.out.println();

    }

}

```

#### Explanation for "*Appending*" Data in 1D-Arrays

First of all lets explain the `isEmpty` part in our function `display`.

```java

// check if the array is filled with the number '0' or not
boolean isEmpty = true;
// DECLARE i: INTEGER
for(int i : array) {
	// if value at index 'i' is NOT equal to '0'
	// meaning array is not "empty"
	if( i != 0) {
		isEmpty = false;
		break;
	}
}

```

As you know ( *I hope you do... I just explain that above $\uparrow$* ) when you create a *static* array in Java, its going to be filled with the value '0'. Hence if you are going to use `array.length == 0` to check if the array is empty or not... Its **not** going to be empty as you still have all of these 0's.
Thus, we need another method ( *not like the built-in functions* ) to be able to find out if the array is "*empty*" or not.

It will check each value in the array and if all the value in the array is **equal** to '0', then `isEmpty` will continue to stay `true`. Else, if you have another value except '0'; `isEmpty` becomes `false` and **output** the contents of the array.

The code above $\uparrow$ basically mimics this Python code below $\downarrow$:

```python

# FUNCTION display(DECLARE ARRAY array)
def display(array):

    # check if the array is empty or not
    if not array:

        # outputs the appropriate message
        print("\nArray is Empty!\n")

    # if array is not empty
    else:

        # outputs the content of the array
        for i, value in enumerate(array):
            print(f"Index = {i} | Value: {value}")

# FUNCTION main()
def main():

    # DECLARE ARRAY numbers: INTEGER
    numbers = [1, 2, 3, 4, 5,]
    # DECLARE ARRAY characters: CHAR
    characters = []

    print("\nContents of Array `numbers`\n")
    # call the function `display`
    display(numbers)

    print()
    print('-'*50)

    print("\nContents of Array `characters`")
    # call the function `display`
    display(characters)

# run the program
main()

```

>[!note]
>I think the other functions / part of the code are self-explanatory.

## Deleting Elements From 1D-Arrays

>[!info]-
>If you are my University Friend and you are reading this... you must thinking "_What the fuck is **popping** and **removing**_?"
>If you have done Python then you know what I might be talking about... the `pop()` and `remove()` function.
>>Basically the `pop()` function will remove the last value in the array ( *if you do not add any arguments in the function* )
>>The `remove()` function takes in an **element** as *argument* and then removes that element from the array

### "*Popping*" Elements From 1D-Arrays

>This is the same thing this $\rightarrow$ [[Arrays - C#"*Popping*" Element From 1D-Array | C Code]].

```java

public class App {

    // FUNCTION line()
    public static void line() {

        System.out.println();
        
        // DECLARE i: INTEGER
        for(int i = 0; i <= 28; i++) {
            // output the character '-' 28 times
            System.out.printf("-");
        }

        System.out.println();

    }

    public static void main(String[] args) throws Exception {

        // DECLARE ARRAY numbers[4]: INTEGER
        int[] numbers = {1, 2, 3, 4, 5};
        // DECLARE array_size: INTEGER
        // see explanation on why we need to use a separate variable
        int array_size = numbers.length;

        System.out.println("\nInitial Contents of Array\n");

        // display the array
        // DECLARE i: INTEGER
        for(int i = 0; i < array_size;i ++) {
            System.out.printf("Index = %d | Value: %d\n", i , numbers[i]);
        }

        // call the function `line`
        line();

        System.out.println("\nPop the Last Value");

        // call the function `line`
        line();

        // DECLARE pop_value: INTEGER
        int pop_value = numbers[array_size - 1];
        
        // decrement the size of array by 1
        array_size--;

        System.out.println("\nModified Contents of Array\n");

        // output the value of array after removal of last value
        for(int i = 0; i < array_size;i ++) {
            System.out.printf("Index = %d | Value: %d\n", i , numbers[i]);
        }

        System.out.println();

    }

}

```

#### Explanation on *popping* Elements from 1D-Arrays

So why do we have to create a variable `array_size` while we already have the `numbers.length()` available... This is because, *again*, *arrays* are **static**! Meaning that if you do an operation like *removal of a value*.
You, yourself need to actually change the size of the array and if you use `numbers.length()` when displaying the array after doing:

```java

int pop_value = numbers[array_size - 1]

```

You are still going to get the output like you did <span style="color: red;"><strong>NOT</strong></span> modified the array!

>[!success]- Code Ouput
>>[!info] Good Code Output
>>```console
>>Initial Contents of Array
>>
>>Index = 0 | Value: 1
>>Index = 1 | Value: 2
>>Index = 2 | Value: 3
>>Index = 3 | Value: 4
>>Index = 4 | Value: 5
>>
>>-----------------------------
>>
>>Pop the Last Value
>>
>>-----------------------------
>>
>>Modified Contents of Array
>>
>>Index = 0 | Value: 1
>>Index = 1 | Value: 2
>>Index = 2 | Value: 3
>>Index = 3 | Value: 4
>>```
>
>---
>
>>[!info] Bad Code Output
>>```console
>>Initial Contents of Array
>>
>>Index = 0 | Value: 1
>>Index = 1 | Value: 2
>>Index = 2 | Value: 3
>>Index = 3 | Value: 4
>>Index = 4 | Value: 5
>>
>>-----------------------------
>>
>>Pop the Last Value
>>
>>-----------------------------
>>
>>Modified Contents of Array
>>
>>Index = 0 | Value: 1
>>Index = 1 | Value: 2
>>Index = 2 | Value: 3
>>Index = 3 | Value: 4
>>Index = 4 | Value: 5
>>```
>

### "*Removing* Elements From 1D-Arrays

Here instead of blatantly removing the **last value** in the array. We are instead going to **ask** the user to enter an *index*'s value to delete.

>[!warning]
>I did not add a **check**; to *check* ( *I know my English is fucked up* ) if `remove_index` is in range or not!

```java

// import Scanner Object
import java.util.Scanner;
// import InputMismatchError ---> for exception handling
import java.util.InputMismatchException;
public class App {

    // FUNCTION display(DECLARE ARRAY array[array_size]: INTEGER, DECLARE array_size: INTEGER)
    public static void display(int[] array, int array_size) {

        System.out.println();

        // DECLARE i: INTEGER
        for(int i = 0; i < array_size; i++) {
            System.out.printf("Index = %d | Value: %d\n", i, array[i]);
        }

        System.out.println();

    }
    public static void main(String[] args) throws Exception {

        // NOTE: In the equivalent C Code, this was much complicated...
            // What I mean is that I asked the user to enter the values into the array
            // For this one I am just going to be populating the array

        // create Scanner Object
        Scanner user_input = new Scanner(System.in);

        // DECLARE number[4]: INTEGER
        int[] numbers = {1, 2, 3, 4, 5};
        // similar to "popping" values; we need to create a variable to hold the size of array
        int array_size = numbers.length;

        System.out.println("\nDisplay Initial Contents of Array");
        
        // calling function `display
        display(numbers, array_size);

        // exception handling
        try {

            // ask the user to enter index of value to remove
            System.out.print("\nPlease Enter Index of Value to Remove: ");
            // DECLARE remove_index: INTEGER
            int remove_index = user_input.nextInt();

            // find and remove the value ( index's value )
            for(int i = remove_index; i < array_size - 1; i++) {
                // all the values above the `remove_index` are being swapped
                numbers[i] = numbers[i + 1];
            }

            // decrement the array size by 1
            array_size--;

            System.out.println("\nDisplay Modified Array");

            // calling the function `display`
            display(numbers, array_size);

        }
        // code block that is run when code catches exception
        catch(InputMismatchException e) {

            // output appropriate message
            System.out.println("\nPlease Enter Integer Values Only!!!\n");
            
        }
        // code block that is always run
        finally {

            // close the Scanner Object
            user_input.close();

        }

    }

}

```

#### Explanation on *removing* Element from 1D-Array

The main thing to look at is:

```java

// find and remove the value ( index's value )
for(int i = remove_index; i < array_size - 1; i++) {
	// all the values above the `remove_index` are being swapped
	numbers[i] = numbers[i + 1];
}

```

This is the trace:

>This is an example on how the above $\uparrow$ code snippet works!

```console

remove_index = 2 ==> will remove the value 3 ( which is stored at index 2 )

now:

i = 2
`i` will continue to iterate through array until it reaches the number 4 ( because `array_size` = 5 and `array_size - 1 = 4` )

because we have `numbers[i] = number[i + 1]` this means that the **value** at index '2' will be 4.
After the next iteration the **value** at index 3 will be 5. Hence, we get an array size of 4.

```

>[!tip] What happened to the value of 3?
>[I don't know!](https://www.youtube.com/watch?v=akEBOgKyXyY&t=6s)... I think its lost in memory... but then again, *I don't know*!

>[!warning] BIG WARNING
>As you can see in the code snippet, we have `i < array_size - 1`. This code is taken from [[Arrays - C#"*Removing*" Element From 1D-Array | C]].
>Over there we only have
>```C
>// DECLARE x: INTEGER
>for(int x = find_index_delete; x < total_values; x++){
>	numbers[x] = numbers[x + 1];
}
>```
>>Where `total_values` is the `array_size`. As you can see we do **not** have `total_values - 1`... I need to ask someone about this! Because I do not know what magic C is doing while Java with its mega abstraction cannot do.
>>But the *correct* way is the one that I wrote for **Java**!


---

# Array Lists

## Creating An Array Lists

>[!note]
>I will be *mostly* using Array List of Type `Object`, so that its similar to Python's List.

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
		// DECLARE i: INTEGER
        for (Object i : array_list) {
            System.out.println(i);
        }

        System.out.println("\nMethod 3: Doing it like the `enumerate` function in Python\n");

        // Method 3: Making it like the `enumerate` function from Python
        // DECLARE size_ArrayList: INTEGER
        int size_ArrayList = array_list.size();

		// DECLARE i: INTEGER
        for(int i = 0; i < size_ArrayList; i++) {
            // the `.get(i)` will "get" the values of each index from the array
            // we are using the format specifier `%s`; because we have created an ArrayList of Objects!
            System.out.printf("Index: %d | Value = %s\n", i, array_list.get(i));
        }

        System.out.println();

    }

}

```

## Adding Elements into Arrays Lists

### "*Inserting*" Elements into Array Lists

>[!tip] Usage
>```java
>array_list.add(index, element)
>```
>So... I lied then ( *kind-of* ), because we do not really have `.insert()` function / method here!
>The `.add()` is the `.insert()` Function from [[Arrays, Tuples, Sets - Python#Inserting Elements in 1D-Array | Python]].
>>[!warning]
>>We are going to be using the same `.add()` function for "*appending elements into array lists*"!

```java

// import module / package Array List
import java.util.ArrayList;
public class App {

    public static void main(String[] args) throws Exception {

        // create Array List of type Object with identifier name "array_list"
        ArrayList<Object> array_list = new ArrayList<Object>();

        // insert all elements at index '0'
        array_list.add(0, 1);
        array_list.add(0, "hello");
        array_list.add(0, 3.5);
        array_list.add(0, 'A');
        array_list.add(0, 69);

        System.out.println("\nContents of Array - Elements Added at Index '0'\n");

        // output contents of array
        // DECLARE i: INTEGER
        for(int i = 0; i < array_list.size(); i++) {

            /*
             * using `.get(i)` function ---> similar to `array[i]
             * NOTE: `array_list[0]` does not work
             */
            System.out.printf("Index = %d | Value: %s\n", i, array_list.get(i));
        }

        System.out.println();

    }

}

```

>[!tip] Output-
>```console
>
>Contents of Array - Elements Added at Index '0'
>
>Index = 0 | Value: 69
>Index = 1 | Value: A
>Index = 2 | Value: 3.5
>Index = 3 | Value: hello
>Index = 4 | Value: 1
>
>```
>As you can see, we do **not** have it like that $\downarrow$:
>```console
>
>Index = 0 | Value: 1
>Index = 1 | Value: hello
>Index = 2 | Value: 3.5
>Index = 3 | Value: A
>Index = 4 | Value: 69
>
>```

>[!bug]- Note
>As a beginner, you should not care about the **speed** of the language! You should **only and only** focus on learning the fundamentals of programming.
>But as I come from a gaming background... *I like everything to be as responsive and quick as possible*.
>What I am saying is that I wanted to see if using the `.get()` is faster or not.
>The other method is output like so $\downarrow$:
>```java
>// output contents of array
>// DECLARE index: INTEGER
>int index = 0;
>// DELCARE value: OBJECT
>for(Object value : array_list) {
>
>	System.out.printf("Index = %d | Value: %s\n", index, value);
>	// increment the `index` by '1'
>	index++;
>
}
>```
>Below you will find the result for using the `.get()` function and `index` "*method*"
>>First result is with `.get()` function and Second result is with `index` "*method*"
>```console
>real    0m0.068s
>user    0m0.062s
>sys     0m0.024s
>```
>---
>```console
>real    0m0.072s
>user    0m0.054s
>sys     0m0.037s
>```
>Just use the fucking `.get()` function / method.

### "*Appending*" Elements in Array Lists

>[!tip] Usage
>```java
>array_list.add(index, element)
>```

But this time, we **only** pass in the *element* that we are going to add!

```java

// import Scanner Object
import java.util.Scanner;
// import the package Array List
import java.util.ArrayList;
public class App {

    // FUNCTION display(ArrayList array: Object) ---> tbh, what do you write here?
    public static void display(ArrayList<Object> array) {

        // check if array list is empty
        if(array.isEmpty()) {

            // if array list is empty, output the message
            System.out.println("Array is Empty\n");

        }
        // if array list is NOT empty
        else {

            // output the contents of array list
            for(int i = 0; i < array.size(); i++) {
                // output the index and value at that index
                System.out.printf("Index = %d | Value: %s\n", i, array.get(i));
            }

        }

    }

    // FUNCTION main(ARRAY of String as Arguments)
    public static void main(String[] args) throws Exception {

        // create Scanner Object
        Scanner user_input = new Scanner(System.in);

        // create Array List of type Object with the identifier name "array_list"
        ArrayList<Object> array_list = new ArrayList<Object>();

        System.out.println("\nContents of Array\n");

        // call the function `display` to display the initial contents of array
        display(array_list);

        // ask the user to enter the amount of value he wants to enter
        System.out.print("Please Enter the Amount of Element to Enter: ");
        // DECLARE user_amount: INTEGER
        int user_amount = user_input.nextInt();

        // consume the next line character
        user_input.nextLine();

        // ask the user to input elements for the amount
        // DECLARE i: INTEGER
        for(int i = 0; i < user_amount; i++) {
            System.out.print("Please Enter an Element: ");
            // DECLARE user_element: Object
            Object user_element = user_input.nextLine();
            // append that element to array list
            array_list.add(user_element);
        }

        System.out.println("\nContents of Array\n");

        // display the updated contents of array
        display(array_list);

        // close the Scanner Object
        user_input.close();

    }

}

```

>Do I really need to explain this... I am getting tired now!

#### Explanation on *Appending* Elements in Array Lists

Lets start with the modified `display()` function.
Instead of passing in `int[] array` into the `()`, we are now passing in `ArrayList<Object> array`... *This is because you are using Array List you damn fucking fool*!
Now here we are able to use functions like `.isEmpty()`; so I am going to use to check if the Array List is empty or not then output the value and its index with the `.get()` method / function.

Now you will see that I have added the line

```java

user_input.nextLine()

```

This is because of the `%n` / `\n` problem. If you do not remember head over to [[Java Language#User Inputs | User Inputs]], head over to the second <span style="color: orange;">Warning</span> call-out, you will get the explanation.
Then again, the rest are pretty self-explanatory!

## Deleting Elements from Array Lists

### "*Popping*" Elements from Array Lists

>Again, I lied ( *again, kind-of* ) there is not such thing as a `pop()` function in Java. We are going to be using the `.remove()` function!

```java

// import module / package for Array Lists
import java.util.ArrayList;
public class App {

    public static void main(String[] args) throws Exception {


        // create an Array List of type Object with identifier name 'array_list'
        ArrayList<Object> array_list = new ArrayList<Object>();

        // append elements into Array List with `.add()` function
        array_list.add(5);
        array_list.add(4);
        array_list.add(3);
        array_list.add(2);
        array_list.add("fuck off");

        System.out.println("\nContents of Array List\n");

        // display the content of Array List
        for(int i = 0; i < array_list.size(); i++) {
            System.out.printf("Index = %d | Value: %s\n", i, array_list.get(i));
        }

        System.out.println();

        // pop the last element from Array List
        array_list.remove(array_list.size() - 1);

        System.out.println("Updated Contents of Array List\n");

        // display the content of Array List again
        for(int i = 0; i < array_list.size(); i++) {
            System.out.printf("Index = %d | Value: %s\n", i, array_list.get(i));
        }

        System.out.println();

    }

}

```

#### Explanation on *popping* Elements from Array Lists

Here we only need to *remove* the **last** element. Hence, we get this one liner code:

```java

// pop the last element from Array List
array_list.remove(array_list.size() - 1);

```

This `array_list.size() - 1` will calculate the **index** of the *last* element. *Wait a second*? *You might be asking but why, just pass in the last index directly*.
This is where you are very very wrong boi!
As you know the `.remove()` function can also *remove* an element by the *element* ( *like you input for example `shit ass`, it removes `shit ass`* ).
Hence, if you have

```console

array_list = [0, 1, 2, 3, 4]

Where:

Index = 0 | Value: 1
Index = 1 | Value: 2
Index = 2 | Value: 0
Index = 3 | Value: 6
Index = 4 | Value: 4

```

If you are going remove the **element** ( *not index* ) `0` which is found at **index** `2` and you do `array_list.remove(0)`.
Its going to remove the **element** `1`.
>This is because, from I am seeing, the `.remove()` function prioritise the **index** first! ( *as an argument* )

Hence, we need to do `array_list.size() - 1` to get the **index** of the last value and then it will _**pop**_ the last value out!

### "*Removing*" Elements from Array Lists

Similar to the [[Arrays, Tuples, Sets - Python#Removing Element From 1D-Array | `.remove()`]] function in Python. We can pass in the actual **element** as an *argument*!

```java

// import module / package for Array Lists
import java.util.ArrayList;
// import the Scanner Object
import java.util.Scanner;
public class App {

    public static void main(String[] args) throws Exception {

        // create Scanner Object
        Scanner user_input = new Scanner(System.in);

        // create an Array List of type Object with identifier name 'array_list'
        ArrayList<Object> array_list = new ArrayList<Object>();

        // ask the user to enter amount of element to add into Array List
        System.out.print("\nPlease Enter the Amount of Elements to Add into Array List: ");
        // DECLARE user_amount: INTEGER
        int user_amount = user_input.nextInt();

        // consume the new-line character 
        // ---> again check Java Language; section User Input ( second Warning callout )
        user_input.nextLine();

        System.out.println();

        // ask the user to enter data into array
        // here we are going to be appending the data, because to the user it will be making more sense
        // DECLARE i: INTEGER
        for(int i = 0; i < user_amount; i++){
            System.out.print("Please Enter an Element: ");
            // DECLARE user_element: OBJECT
            Object user_element = user_input.nextLine();
            // append that element to the Array List
            array_list.add(user_element);
        }

        System.out.println("\nContents of Array List\n");

        // display the content of Array List
        for(int i = 0; i < array_list.size(); i++) {
            System.out.printf("Index = %d | Value: %s\n", i, array_list.get(i));
        }

        System.out.println();

        // ask the user to enter a element to remove
        System.out.print("Please Enter an Element to Remove: ");
        // DECLARE remove_element: OBJECT
        Object remove_element = user_input.nextLine();

        // remove that element from Array List
        array_list.remove(remove_element);

        System.out.println("Updated Contents of Array List\n");

        // display the content of Array List again
        for(int i = 0; i < array_list.size(); i++) {
            System.out.printf("Index = %d | Value: %s\n", i, array_list.get(i));
        }

        System.out.printf("\nElement Removed: %s", remove_element);

		// close Scanner Object
		user_input.close()

    }

}

```

#### Explanation on *removing* Elements from Array Lists

The main thing to look at here is this $\downarrow$ code snippet:

```java

// ask the user to enter a element to remove
System.out.print("Please Enter an Element to Remove: ");
// DECLARE remove_element: OBJECT
Object remove_element = user_input.nextLine();

// remove that element from Array List
array_list.remove(remove_element);

```

- Ask the user to enter an **element** to *remove* ( *yes... element and not index. I mean you could if you want to!* )
- The *element* entered by the user goes into the variable `remove_element`
- **Removes** the *element* from the Array List with `array_list.remove(remove_element)`

>I wanted to skip this part, but because I am a good person ( *shut up... I am a good person* ), I decided to include something.

>[!info]
>Even if the user adds an element like... let's say `fuck you`. As you can see it has the `<Space>` in between. Now when the program / code will ask the user to enter an element to **remove**; it will actually **remove** the element `fuck you` if the user enters `fuck you`.
>>Its not like in C, where we need to use the [[C Language#`fgets()` Function | `fgets()`]] function to be able to accept white spaces in between words.

---

# Socials

- **Instagram**: https://www.instagram.com/s.sunhaloo/
- **YouTube**: https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg
- **GitHub**: https://www.github.com/Sunhaloo

---

S.Sunhaloo
Thank You!