---
Alias: IF-CASE-WHILE-REPEAT - Java
Tag: java, basics
Author: S.Sunhaloo
Type: Conditions / Statements
Date: 2024-05-21
Status: Completed
---

## List of Contents

- [[Selections and Iteration - Java#IF Statements | IF Statements]]
- [[Selections and Iteration - Java#CASE Statements | CASE Statements]]
- [[Selections and Iteration - Java#WHILE Statements | WHILE Statements]]
	- [[Selections and Iteration - Java#DO WHILE Statements | DO WHILE Statements]]
- [[Selections and Iteration - Java#FOR Loops | FOR Loops]]

---

### Break, Continue and Pass

- [[Selections and Iteration - Java#Break Continue Pass | Break | Continue | Pass]]
	- [[Selections and Iteration - Java#Break | Break]]
	- [[Selections and Iteration - Java#Continue | Continue]]
	- [[Selections and Iteration - Java#Pass | Pass]]

---

### My Links

- [[Selections and Iteration - Java#Socials| Link to Social]]

---

>[!info]
>Because I do *not* really have time to make it "**beautiful**", I am just converting my Python note's codes ( *English mate, English* ).

# IF Statements

## Example 1: Age Thing

```java

// import Scanner object
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        // create Scanner for user input
        Scanner user_input = new Scanner(System.in);

        // ask the user to input his age
        System.out.print("\nPlease Enter Your Age: ");
        // DECLARE user_age: INTEGER
        int user_age = user_input.nextInt();

        /*        
            IF Statements ( conditions )
            Syntax is Similar to C
        */

        // || = OR ---> Same as C
        if(user_age < 0 || user_age > 100){
            System.out.println("\nYou got to be kidding me!\n");
        }
        // && = AND ---> Same as C
        else if(user_age >= 18 && user_age <= 100){
            System.out.println("\nYou are an adult\n");
        }

        // close Scanner object
        user_input.close();

    }
}

```


## Example 2: Temperature Thing

```java

// import Scanner object
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        // create Scanner for user input
        Scanner user_input = new Scanner(System.in);

        // ask the user to input the temperature
        System.out.print("\nPlease Enter Temperature: ");
        // DECLARE user_age: INTEGER
        float user_temp = user_input.nextFloat();

		// conditions

        if(user_temp >= 0 && user_temp <= 40){
            System.out.println("\nNormal Temperature\n");
        }
        else if(user_temp >= 41 && user_temp <= 100){
            System.out.println("\nVery Hot\n");
        }
        else if(user_temp < 0){
            System.out.println("\nVery Cold\n");
        }
        else{
            System.out.println("\nExtreme Temperature\n");
        }

        // close Scanner object
        user_input.close();

    }
}

```

# CASE Statements

Instead of [[Selection and Iteration - Python#Method 1 Match Case | Match Case]] we have `switch` case.

>[!warning]-
>We need to add `break` after each "*case*".
>So that it does not stay stuck and actually moves to the next "*case*"

```java

// import Scanner object
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        // create Scanner for user input
        Scanner user_input = new Scanner(System.in);

        // ask the user to input his favourite programming language
        System.out.print("\nWhat is your favourite Programming Language: ");
        // DECLARE user_lang: STRING
	    // could have also used `user_input.nextLine()`
        String user_lang = user_input.next();

        /*
            CASE Statements
            `switch...case...`
            instead of Python's
            `match...case...`
        */

         switch(user_lang) {
            case "JavaScript":
                System.out.println("\nYou can become a Web Developer\n");
                break;
            case "Python":
                System.out.println("\nYou can become a Data Scientist\n");
                break;
            case "PHP":
                System.out.println("\nYou can become a Backend Developer\n");
                break;
            case "Solidity":
                System.out.println("\nYou can become a Blockchain Developer\n");
                break;
            case "Java":
                System.out.println("\nYou can become a Mobile App Developer\n");
                break;
            /*
                instead of `case _...`
                we have `default`
            */
            default:
                System.out.println("\nThe language does not matter...\nWhat matters is solving problems\n");
                break;

         }

        // close Scanner object
        user_input.close();

    }
}

```

# WHILE Statements

## Example 1: User need to enter Phone Number

This is the same as our Python [[Selection and Iteration - Python#Example 1 User enters phone number and displays a message | code]].
Like we are going to check if the variable `tel_num` is `0` and then if **not**, we exit the `while` loop.

>But in Java ( *because of mega fucking huge ass abstraction* ) we have functions called `.isEmpty()` and `.isBlank()`.
>Which check if the variable `tel_num` is empty or not.

### Using Length

```java

// import Scanner object
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        // create Scanner for user input
        Scanner user_input = new Scanner(System.in);

        // DECLARE tel: STRING
        String tel = "";

        // output a blank line
        System.out.println();

        // keep looping until the user enters his phone number
        while(tel.length() == 0){
            System.out.print("Please Enter Your Phone Number: ");
            // using the same variable to be able to add contents for it
            tel = user_input.nextLine();
        }

		// check if `tel` contains Integer numbers
		// similar to `.isdigit()` in Python
        if(tel.matches("\\d+")){
            int telNum = Integer.parseInt(tel);
            System.out.printf("\nPhone Number: %d\n\n", telNum);
        }
        else{
            System.out.println("\nNot a Phone Number\n");
        }

        // close Scanner object
        user_input.close();

    }
}

```

>[!tip] What does `\\d+` means?
>`\d` $\Rightarrow$ Shorthand character class that matches any digit character ( *i.e 0 $\rightarrow$ 9* )
>`+` $\Rightarrow$ Quantifier that matches one or more occurrences of the preceding element
>Hence `\\d+` means:
>	- `\d` matches any single digit
>	- `+` ensures that there is at least one digit, but it can match more than one digit as well

### Using `.isEmpty()` Function

>Not going to be writing the whole code
>Only the code *Snippet* ( *ahh, a word that I do not normally use*! )

```java

// keep looping until the user enters his phone number
while(tel.isEmpty()){
	System.out.print("Please Enter Your Phone Number: ");
	// using the same variable to be able to add contents for it
	tel = user_input.nextLine();

```

### Using `.isBlank()` Function

>Again, not going to be writing the whole thing as its going to be a waste of time!

```java

// keep looping until the user enters his phone number
while(tel.isBlank()){
	System.out.print("Please Enter Your Phone Number: ");
	// using the same variable to be able to add contents for it
	tel = user_input.nextLine();

```

>I do **not** know which is actually faster in terms of *performance*.

## Example 2: Enter `while` Loop Once

```java

public class Main {
    public static void main(String[] args) {

        boolean enter = true;

        // condition to enter while loop
        while(enter == true){
            System.out.printf("\n`enter` = %b ---> Login Successful\n", enter);
            
            // `enter` becomes `false`
            enter = false;
            System.out.printf("\n`enter` = %b ---> You have been Hacked!!!\n\n", enter);
            // Will not enter while loop again as values is `false`

        }
    }
}

```

# DO WHILE Statements

Compared to a `while` loop, this will execute at least **once**!

## Example 1: Simple `index` Increment

```java

public class Main {
    public static void main(String[] args) {

        // DECLARE index: INTEGER
        // we are going to use pre-increment like `++index`
        int index = -1;

        // display `index` until its value reaches 10
        do{

            // PRE-increment index
            ++index;
            // display the value of `index`
            System.out.printf("Index = %d\n", index);

        // because we used `++index`, we need to make it until less than or equal to 9
        } while(index <= 9);

    }
}

```

>[!note]
>Here we used `++index` $\Rightarrow$ **pre**-increment; meaning as soon as we add this statement `++index`; its going to increment
>
>In simple terms, it increments first before printing
>Hence that it why `index = -1` and `while(index <= 9)`

>No more examples; because I do not really use `DO... WHILE` loops.

# FOR Loops

## Example 1 : Display values of Array

```java

public class Main {
    public static void main(String[] args) {

        // DECLARE number[4]: ARRAY
        int[] number = {1, 2, 3, 4, 5};

        // display each value of array
        for(int i = 0; i < number.length; i++){
            // displays the index and value at that index
            System.out.printf("Index: %d | Value = %d\n", i, number[i]);
        }
    }
}

```

## Example 2: Displaying a Range of Number ( *literally* )

```java

public class Main {
    public static void main(String[] args) {

        System.out.println("\nDisplay 0 to 100 inclusive\n");

        // display number 0 to 100 inclusive
        // DECLARE i: INTEGER
        for(int i = 0; i <= 100; i++){
            System.out.printf("%d... ", i);
        }

        System.out.println("\n\nDisplay 100 to 0 inclusive\n");

        // display number 0 to 100 inclusive
        // DECLARE j: INTEGER
        for(int j = 100; j >= 0; j--){
            System.out.printf("%d... ", j);
        }

        System.out.println("\n\nMultiples of 2\n");

        // display the multiples of 2
        // from 0 to 20 inclusive
        // DECLARE x: INTEGER
        for(int x = 0; x <= 21; x += 2){
            System.out.printf("%d\n", x);
        }

        System.out.println("\nDivide by 5\n");

        // initialise variable y to 100 then keep dividing until it reaches 0
        // DECLARE y: INTEGER
        for(int y = 100; y > 0; y /= 5){
            System.out.printf("%d\n", y);
        }

    }
}

```

## Example 3: Making Art

>See for your fucking self!
>I wrote this in the Python note; figure out that I also need to write this here!

```java

// import Scanner object
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        // create Scanner object
        // will be using the Scanner object for asking symbol, row and column count
        Scanner user_input = new Scanner(System.in);

        // ask to user to enter number of rows
        System.out.print("Please Enter Number of Rows: ");
        // DECLARE rows: INTEGER
        int rows = user_input.nextInt();
        // ask to user to enter number of columns
        System.out.print("Please Enter Number of Columns: ");
        // DECLARE cols: INTEGER
        int cols = user_input.nextInt();
        
        // consume nextline character ---> basically have to do this to be able to enter symbol / char
        user_input.nextLine();

        // ask the user to enter symbol to display
        System.out.print("Please Enter Symbol to Use: ");
        // why can't I not use `char` here
        String user_symbol = user_input.nextLine();

        // display a blank line
        System.out.println();

        // displaying the GRID
        for(int i = 0; i < rows; i++){
            // adds some type of padding
            // basically adds a space / margin
            for(int x = 0; x < rows; x++){
                System.out.printf(" ");
            }
            // displays the actuall symbol
            for(int j = 0; j < cols; j++){
                System.out.printf("%s", user_symbol);
            }
            // change the line
            System.out.println();
        }

        // display a blank line
        System.out.println();

        // close the Scanner object
        user_input.close();

    }
}

```

# Break | Continue | Pass

If you need a better explanation; head over to [[Selection and Iteration - Python#Break Continue Pass | Break | Continue | Pass]].
In addition there will always be [Google](https://www.google.com), [YouTube](https://www.youtube.com) University, [GitHub](https://www.github.com), [StackOverflow](https://www.stackoverflow.com) and more.

## Break

```java

public class Main {
    public static void main(String[] args) {
        
        // keeps entering the condition ---> because set to 'true'
        while(true){
            // output 0 to 100 inclusive
            // DECLARE i: INTEGER
            for(int i = 0; i <= 100; i++){
                // output the numbers
                System.out.printf("%d\n", i);
            }
            // will not keep entering the `while` loop
            // will "break" out from the `while` loop
            break;
        }

    }
}

```

## Continue

```java

public class Main {
    public static void main(String[] args) {
        
        // keeps entering the condition ---> because set to 'true'
        while(true){
            // output 0 to 100 inclusive
            // DECLARE i: INTEGER
            for(int i = 0; i <= 100; i++){
                // output the numbers
                System.out.printf("%d\n", i);
                // continue to output number if `i` is equal to 5
                if(i == 5 || i == 95){
                    System.out.println("\nArrived at i = "+ i + " continue to print values...\n");
                    // continue with the `for` loop
                    continue;
                }

            }
            // will not keep entering the `while` loop
            // will "break" out from the `while` loop
            break;
        }

    }
}

```

## Pass

>[!warning]
>There is <span style="color: green;"><strong>no</strong></span> `pass` *statement* in Java.
>Basically if you want to use the `pass` *thing*; just don't write **anything**, it will automatically `pass` it.

>For this I am going to write the [[Python Language | Python]] code.
>So that you can see the comparison with Java and how we just don't write anything.

### Python Code

```python

# output 0 to 100 inclusive
# DECLARE i: INTEGER
for i in range(101):
    # if variable `i` is equal to 5 or 95; don't output these numbers
    if i == 5 or i == 95:
        pass
        print(f"\nThe Number {i} has not been displayed\n")
    else:
        print(i)

```

### Java Equivalent Code

```java

public class Main {
    public static void main(String[] args) {
        
        // output 0 to 100 inclusive
        // DECLARE i: INTEGER
        for(int i = 0; i <= 100; i++){
            // if variable `i` is equal to 5 or 95; don't output these numbers
            if(i == 5 || i == 95){
                System.out.printf("\nThe Number '%d' has not been displayed!\n\n", i);
            }
            // for the rest of the numbers
            else {
                // output the numbers
                System.out.printf("%d\n", i);
            }
        }

    }
}

```

>[!note]
>Check the *statements* in the `if` condition... *there is only the print, no `pass`, etc*!

---

# Socials

- [**Instagram**](https://www.instagram.com/s.sunhaloo/)
- [**YouTube**](https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg)
- [**GitHub**](https://www.github.com/Sunhaloo)

---

S.Sunhaloo
Thank You!