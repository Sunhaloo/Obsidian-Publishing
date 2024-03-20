---
Alias: C Random Program Codes
Tag: C
Author: S.Sunhaloo
Type: Random Program Codes
Date: 2024-02-17
Status: HOLD
---

## List of Contents

- [[Random C Program Codes#Code 1 | Code 1]]
- [[Random C Program Codes#Code 2 | Code 2]]
- [[Random C Program Codes#Code 3 | Code 3]]

---

## My Links

- [[Random C Program Codes#Socials | Links to Socials]]

---

# Code 1

## Sample 1

The code below will allow the user to enter **radius** of a circle in centimeters and will calculate the **circumference** and **area** of that circle.

```C

// Circumference and Area Calculator

#include <stdio.h>
#include <math.h>

int main()

{

    // Allow user to input the radius of circle
    float user_radius;

    printf("Please Enter The Radius ( in centimeters ) of Circle: ");
    scanf("%f", &user_radius);

    // Calculate the Circumference and Area
    float circumference;
    float area;

    circumference = 2 * 3.141592 * user_radius;
    area = 3.141592 * ( pow(user_radius, 2) );

    printf("Value of Radius = %0.2f | Circumference = %0.2f | Area = %0.2f\n", user_radius, circumference, area);

    return 0;

}

```

## Sample 2

```C

// Circumference and Area Calculator

#include <stdio.h>

int main()

{

	const double PI = 3.141592;
	double user_radius;
	double circumference;
	double area;
	
	// Ask the user to enter radius of circle
	printf("Please Enter The Radius ( in centimeters ) of Circle: " );
	scanf("%lf", &user_radius);
	
	// Calculate Circumference and Area
	circumference = 2 * PI * user_radius;
	area = PI * user_radius * user_radius;
	
	printf("Value of Radius = %0.2lf | Circumference = %0.2lf | Area = %0.2lf\n", user_radius, circumference, area);

	return 0;

}

```

---

# Code 2

## Sample 1

Simple Hypotenuse Calculator.

```C

// Hypotenuse Calculator

#include <stdio.h>
#include <math.h>

int main()

{

    printf("Hypotenuse Calculator\n");

    // Declaring Variables
    double Base, Height, c_length;

    // Ask the user to enter the length and width
    printf("Please Enter The Length ( in centimeters ) of Base of Triange: ");
    scanf("%lf", &Base);
    printf("Please Enter The Length ( in centimeters ) of Height of Triange: ");
    scanf("%lf", &Height);

    // Calculate the Hypotenuse
    c_length = sqrt((pow(Base, 2) + pow(Height, 2)));

    // Output the length of Hypotenuse
    printf("The Length of Hypotenuse = %0.2lf\n", c_length);


    printf("\n");

	return 0;

}

```

# Code 3

This code will be able to **covert** *Celsius* to *Fahrenheit* or vice versa depending on what the user has selected to convert.

```C

// Include standard input / output header
#include <stdio.h>
// Include string manipulation library / header
#include <ctype.h>

int main()
{

    // DECLARE temp_unit: CHAR
    char temp_unit;
    // DECLARE temperature: FLOAT
    float temperature;

    // Ask the user to enter the unit of temperature
    printf("Is The Temperature Fahrenheit (F) or Celcius (C)? --> ");
    scanf("%c", &temp_unit);

    // convert lowercase letter into uppercase letters
    // This is done using a function in <ctype.h> header
    temp_unit = toupper(temp_unit);

    // If unit of temperature is Celsius
    if(temp_unit == 'C'){
        printf("Your Unit is in Celsius!\n");

        // Ask the user to enter the temperature
        printf("Please Enter The Temperature: ");
        scanf("%f", &temperature);
        
        printf("\nConverting to Fahrenheit\n");

        printf("\n");

        // Conversion
        temperature = ((temperature * 9 / 5) + 32);

        // Output the temperature
        printf("The Temperature in Fahrenheit = %0.1f\n", temperature);
    }
    // If unit of temperature is Fahrenheit
    else if(temp_unit == 'F'){
        printf("Your Unit is in Fahrenheit!\n");

        // Ask the user to enter the temperature
        printf("Please Enter The Temperature: ");
        scanf("%f", &temperature);

        printf("\nConverting to Celsius\n");

        printf("\n");

        // Conversion
        temperature = ((temperature -32) * 5 / 9);

        // Output the temperature
        printf("The Temperature in Celsius = %0.1f\n", temperature);
    }

    return 0;

}

```

# Code 4

This is a the simplest calculator that has been destined upon mankind. Do whatever you want with it.

>This could have also been written with `switch`. But because we had 5 conditions, I just used `if` statements.

```C

// Include standard input / output header
#include <stdio.h>
// Include <stdlib.h> ---> To be able to use `exit()` function
#include <stdlib.h>

int main()
{

    // DECLARE num1: DOUBLE
    double num1;
    // DECLARE num2: DOUBLE
    double num2;
    // DECLARE result: DOUBLE
    double result;
    // DECLARE operation: CHAR
    char operation;

    // Selection of Operation Screen / Output

    printf("\nPlease Choose From The Following\n");

    printf("\n1. Addition = A\n");
    printf("\n2. Subtraction = S\n");
    printf("\n3. Multiplication = M\n");
    printf("\n4. Divide = D\n");

    printf("\nSelect Operation by Choosing 'A', 'S', 'M' or 'D'\n");

    // Ask the user to select operation
    printf("Please Enter Your Selection: ");
    scanf("%c", &operation);

    // Conditions and Statements
    if(operation == 'A'){
        printf("\nAddition Calculator\n");
        
        // Ask the user to enter first value
        printf("Please Enter First Number: ");
        scanf("%lf", &num1);
        // Ask the user to enter second value
        printf("Please Enter First Number: ");
        scanf("%lf", &num2);

        // Calculation
        result = num1 + num2;

        // Output result
        printf("Result of Addition = %lf\n", result);

        printf("\n");
    }
    else if(operation == 'S'){
        printf("\nSubtraction Calculator\n");
        
        // Ask the user to enter first value
        printf("Please Enter First Number: ");
        scanf("%lf", &num1);
        // Ask the user to enter second value
        printf("Please Enter First Number: ");
        scanf("%lf", &num2);

        // Calculation
        result = num1 - num2;

        // Output the result
        printf("Original Result of Subtraction = %lf\n", result);

        // Converting to negative / positive ---> Depends on how you see it
        result = result * -1;

        // Output result
        printf("Result of 'Negative' Subtraction = %lf\n", result);

        printf("\n");
    }
    else if(operation == 'M'){
        printf("\nMultiplication Calculator\n");

        // Ask the user to enter first value
        printf("Please Enter First Number: ");
        scanf("%lf", &num1);
        // Ask the user to enter second value
        printf("Please Enter First Number: ");
        scanf("%lf", &num2);

        // Calcuation
        result = num1 * num2;

        // Output result
        printf("Result of Multiplication = %lf", result);

        printf("\n");
    }
    else if(operation == 'D'){
        printf("\nDivision Calculator\n");

        // Ask the user to enter first value
        printf("Please Enter First Number: ");
        scanf("%lf", &num1);
        // Ask the user to enter second value
        printf("Please Enter First Number: ");
        scanf("%lf", &num2);

        // Calcuation
        result = num1 / num2;

        // Output result
        printf("Result of Division: %lf", result);

        printf("\n");
    }
    else{
        // If user enters something other than 'A', 'S', 'M' or 'D'
        printf("You Have Done / Entered Something Wrong!");
        
        // Exits the program
        exit(0);
    }

    return 0;

}

```

>[!note]
>We have added `<stdlib.h>`;
>This will also use the `exit()` function which is the same thing found in Python ( *I miss Python, where I do not need to include a fucking library to use basic functions* )

---

# Socials

- [**GitHub**](https://www.github.com/Sunhaloo)
- [**Instagram**](https://www.instagram.com/s.sunhaloo/)
- [**YouTube**](https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg)

---
Thank You!