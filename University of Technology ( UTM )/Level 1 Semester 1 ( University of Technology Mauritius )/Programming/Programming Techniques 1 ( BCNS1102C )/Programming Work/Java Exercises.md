---
Alias: Programming Techniques 1 ( Java Exercises ) - Week 3
Tag: uni, java
Module: BSNC1102C
Author: S.Sunhaloo
Date: 2024-05-24
Status: Completed
---

<p align="center">Database Design<br>Assignment 1<br>BCNS1103C / DBT1103C<br>SUNHALOO Shehzaad</p>

<p align="center">University of Technology, Mauritius</p>

---

### My Links

- [[Java Exercises#Socials | Link to Social]]

---

# Exercises on Java

# Exercise 1

Write a program to display the text "This is my first Java Program" on the screen.

```java

public class App {
    public static void main(String[] args) {
        
        // Exercise 1

        // display the message
        System.out.println("\nThis is my not first Java Program!\n");
        
    }
}

```

# Exercise 2

Write a simple Java Program to calculate the area of a Circle

```java

// import Scanner object
import java.util.Scanner;

public class App {
    public static void main(String[] args) {
        
        // Exercise 2

        // create a Scanner object to prompt the user to input radius
        Scanner input_radius = new Scanner(System.in);
        // DECLARE PI: DOUBLE
        double PI = 3.142;
        
        // prompt the user to enter value of radius
        System.out.print("\nPlease Enter Radius ( in centimeter ): ");
        // DECLARE radius: DOUBLE
        double radius = input_radius.nextDouble();

        // calculate the area
        // DECLARE area_circle: DOUBLE
        double area_circle = PI * radius * radius;

        // output the area
        System.out.printf("\nThe Area of Circle = %.2f cm^2\n\n", area_circle);

        // close the Scanner object to avoid resource leak
        input_radius.close();

    }
}

```

# Exercise 3

Modify the above $\uparrow$ ( *Exercise 2* ) to use a Constant for PI

```java

// import Scanner object
import java.util.Scanner;
// import the math library
import java.lang.Math;

public class App {
    public static void main(String[] args) {

        // DECLARE area_circle: DOUBLE
            // use the `pow()` function
        double area_circle = PI * Math.pow(radius, 2);

        // output the area
        System.out.printf("\nThe Area of Circle = %.2f cm^2\n\n", area_circle);

        // close the Scanner object to avoid resource leak
        input_radius.close();

    }
}

```

# Exercise 4

Write a program to display the numbers 1 - 5 on screen using print methods

```java

public class App {
    public static void main(String[] args) {
        
        // Exercise 4

        // DECLARE x: INTEGER
        for(int x = 1; x < 6; x++){
            // using `print()` function so that is goes on 1 line
            System.out.print(x);
        }

        System.out.println("\n");

        // DECLARE i: INTEGER
        for(int i = 0; i < 6; i++){
            System.out.println(i);
        }

        System.out.printf("\n");

        // DECLARE y: INTEGER
        for(int y = 0; y < 6; y++){
            System.out.printf("%d", y);
        }

    }
}

```

# Exercise 5

Write a program or *program statements* which will calculate the sum, difference, product, quotient and remainder of 2 integer values. The results of these calculations should be stored in appropriately named variables

>In this case the user has not been prompted to enter the numbers

```java

public class App {
    public static void main(String[] args) {
        
        // Exercise 5

        // DECLARE num1: DOUBLE
        double num1 = 1;
        // DECLARE num1: DOUBLE
        double num2 = 2;

        // calculations

        // addition
        // DECLARE addition: DOUBLE
        double addition = num1 + num2;
        // subtraction
        // DECLARE subtraction: DOUBLE
        double subtraction = num1 - num2;
        // multiplication
        // DECLARE multiplication: DOUBLE
        double multiplication = num1 * num2;
        // division
        // DECLARE division: DOUBLE
        double division = num1 / num2;
        // remainder
        // DECLARE remainder: DOUBLE
        double remainder = num1 % num2;

        // display the results of calculations

        System.out.println("\nResults of Calculations:");

        System.out.printf("\nAddition = %.2f", addition);
        System.out.printf("\nSubtraction = %.2f", subtraction);
        System.out.printf("\nMultiplication = %.2f", multiplication);
        System.out.printf("\nDivision = %.2f", division);
        System.out.printf("\nRemainder = %.2f\n\n", remainder);

    }
}
	
```

# Exercise 6

Write a program to calculate the reciprocal of a number. The program should prompt the user to enter a number and should then calculate and display the reciprocal.

>If $x$ is the number $\Rightarrow$ Reciprocal = $\frac{1}{x}$

```java

// importing Scanner object
import java.util.Scanner;

public class App {
    public static void main(String[] args) {
        
        // Exercise 6

        // create out Scanner object
        Scanner input_num = new Scanner(System.in);

        System.out.println();

        // ask the user to input number
        System.out.print("Please Enter A Number: ");
        // DECLARE user_num: DOUBLE
        double user_num = input_num.nextDouble();

        // find the reciprocal
        double reciprocal = 1 / user_num;

        // output the result
        System.out.println("\nThe result of reciprocal is: " + reciprocal + "\n");
        
        // closing Scanner object to avoid resource leak
        input_num.close();

    }
}

```

# Exercise 7

Write a program to calculate the average of 3 numbers. The program should prompt the user to enter the 3 numbers. Obviously we then need to display the result of the calculation.

```java

// importing Scanner object
import java.util.Scanner;

public class App {
    public static void main(String[] args) {
        
        // Exercise 7

        // not like in Visual Basic where you need to do this
        /*
         * 
         * Console.WriteLine("Input Number 1: ")
         * Integer num1 = Console.Readline()
         * Console.WriteLine("Input Number 2: ")
         * Integer num2 = Console.Readline()
         * 
         */
        Scanner input_num = new Scanner(System.in);

        System.out.println();

        // ask the user to input the numbers

        System.out.print("Please Enter Number 1: ");
        // DECLARE num1: DOUBLE
        double num1 = input_num.nextDouble();
        System.out.print("Please Enter Number 2: ");
        // DECLARE num2: DOUBLE
        double num2 = input_num.nextDouble();
        // DECLARE num3: DOUBLE
        System.out.print("Please Enter Number 3: ");
        double num3 = input_num.nextDouble();

        // calculate the average of user's numbers
        // DECLARE average: DOUBLE
        double average = (num1 + num2 + num3) / 3;

        // display the result of calculations
        System.out.printf("\nAverage of Numbers = %.2f\n", average);

        // closing the Scanner object
        input_num.close();

    }
}

```

# Exercise 8

Write a program which converts a user specified temperature from Fahrenheit to Degree Celsius using the formula: $celsius = ( (fahrenheit - 32 ) *  5 ) / 9$ and output the answer.

```java

// importing Scanner object
import java.util.Scanner;

public class App {
    public static void main(String[] args) {
        
        // Exercise 8

        // create Scanner object
        Scanner input_temp = new Scanner(System.in);

        // ask the user to input the temperature
        System.out.print("Please Enter Temperate ( in Fahrenheit ): ");
        // DECLARE tempF: DOUBLE
        double tempF = input_temp.nextDouble();

        // convert the user temperature into Degrees Celsius
        // DECLARE tempC: DOUBLE
        double tempC = ( (tempF - 32) * 5 ) / 9;

        // output the converted temperature to user
        System.out.printf("\nTemperature ( Degrees Celcius ): %.2f\n\n", tempC);

        // closing the Scanner object
        input_temp.close();

    }
}

```

# Exercise 9

Write a program which prompts the user to enter the number of day, hours and minutes. The program will then calculate and display this as a total number of minutes

```java

// importing Scanner object
import java.util.Scanner;

public class App {
    public static void main(String[] args) {
        
        // Exercise 9

        // create Scanner object
        Scanner user_input = new Scanner(System.in);

        System.out.println("\nDays Converter\n");

        // ask the user to enter number of days, hours and minutes
        System.out.print("Please Enter the Number of Days: ");
        // DECLARE days: INTEGER
        int days = user_input.nextInt();
        System.out.print("Please Enter the Number of Hours: ");
        // DECLARE hours: INTEGER
        int hours = user_input.nextInt();
        System.out.print("Please Enter the Number of Minutes: ");
        // DECLARE minutes: INTEGER
        int minutes = user_input.nextInt();

        // conversion + addition of ---> get total amount of minutes 
        // DECLARE total_mins: INTEGER
        int total_mins = ( days * 24 * 60 ) + ( hours * 60 ) + minutes;

        // output the result of conversion and addition
        System.out.printf("\nTotal amount of Minutes = %d minutes\n\n", total_mins);

        // closing the Scanner object
        user_input.close();

    }
}

```

# Exercise 10

Write a program that displays a box, an oval and a diamond using asterisks ( * ).

```java

public class Main {
    public static void main(String[] args) {

        System.out.println("\nSquare / Box\n");

        System.out.println("*********");
        System.out.println("*       *");
        System.out.println("*       *");
        System.out.println("*       *");
        System.out.println("*       *");
        System.out.println("*       *");
        System.out.println("*       *");
        System.out.println("*       *");
        System.out.println("*********");

        System.out.println("\nOval\n");

        System.out.println("    ***    ");
        System.out.println(" *       * ");
        System.out.println("*         *");
        System.out.println("*         *");
        System.out.println("*         *");
        System.out.println("*         *");
        System.out.println("*         *");
        System.out.println(" *       * ");
        System.out.println("    ***    ");

        System.out.println("\nArrow\n");

        System.out.println("    *    ");
        System.out.println("   ***   ");
        System.out.println("  *****  ");
        System.out.println("    *    ");
        System.out.println("    *    ");
        System.out.println("    *    ");
        System.out.println("    *    ");
        System.out.println("    *    ");
        System.out.println("    *    ");

        System.out.println("\nDiamond\n");

        System.out.println("    *    ");
        System.out.println("   * *   ");
        System.out.println("  *   *  ");
        System.out.println(" *     * ");
        System.out.println("*       *");
        System.out.println(" *     * ");
        System.out.println("  *   *  ");
        System.out.println("   * *   ");
        System.out.println("    *    ");

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