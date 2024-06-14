---
Alias: Math Library / Module in Java
Tag: java, basics
Author: S.Sunhaloo
Type: Math
Date: 2024-06-06
Status: Completed
---

## List of Contents

- [[Java Math Library#Round Function | Round Function]]
- [[Java Math Library#Power Function | Power Function]]
- [[Java Math Library#ABS Function | ABS Function]]
- [[Java Math Library#Max Function | Max Function]]
- [[Java Math Library#Min Function | Min Function]]
- [[Java Math Library#PI in Java | PI in Java]]
- [[Java Math Library#Ceil Function | Ceil Function]]
- [[Java Math Library#Floor Function | Floor Function]]
- [[Java Math Library#Square Root Function | Square Root Function]]

---

### My Links

- [[Java Math Library#Socials| Link to Social]]

---

>[!tip]
>You do **not** need to do `import java.lang.Math` to be able to use these functions.
>This is because its **available** by *default*; no need to explicitly import it ( *i.e write `import ...` $\uparrow$* )
>This holds true for any version of Java / JDK.
>>*Nice Then*!


# Math Functions

>[!warning] NOTE
>When using `Math.whatever_you_need_here()` $\leftarrow$ this is of *type* `double` ( *or `Double` if you wish to create an Object* )
>
>You can obviously [[Java Language#Data Types Conversion / Type Cast | Type Cast]] it; but the way that I am going to be using it; I will be using `double`.
>Nevertheless, I might some where I *cast* them.
>>In addition, `double` leads to more precision!

## Round Function

>[!tip] Usage
>```java
>Math.round(x)
>```

```java

public class Main {
    public static void main(String[] args) throws Exception {

        // pass values directly in function
        // DECLARE first_round: DOUBLE
        double first_round = Math.round(3.5);

        // as they are Primitive Datatypes; we can use `printf`
        System.out.printf("\n'3.5' Rounded = %.1f\n", first_round);

        // variable to hold the value ---> not passing directly into function
        // DECLARE num: FLOAT
        float num = 5.13745f;

        // using type cast to convert `double` into `float`
        // DECLARE second_round: FLOAT
        float second_round = (float) Math.round(num);

        // output the the screen
        System.out.printf("\nVariable `num` Rounded-Off %.1f\n\n", second_round);

    }
}

```

## Power Function

>"Powwaahhh" [James May impersonating Jeremy Clarkson](https://www.youtube.com/watch?v=julCVK6idn8&t=38s)

>[!tip] Usage
>```java
>Math.pow(x , y)
>```

```java

public class Main {
    public static void main(String[] args) throws Exception {

        // pass values directly in function
        // DECLARE first_pow: DOUBLE
        double first_pow = Math.pow(12, 12);

        // as they are Primitive Datatypes; we can use `printf`
            // `%.0f` ==> '0' for "don't display decimal numbers"
        System.out.printf("\nWhat is (12^12)? = %.0f\n", first_pow);

        // variable to hold the value ---> not passing directly into function
        // DECLARE base: float
        float base = 5.4f;
        // DECLARE :exponent INTEGER
        int exponent = 12;

        // DECLARE second_pow: INTEGER
        double second_pow = Math.pow(base, exponent);

        // output the the screen
        System.out.printf("\n(5.4^12) = %.8f\n\n", second_pow);

    }
}

```

## ABS Function

>Again, as I have been saying "*not the Anti-Lock Braking System*" or "*ABS*"!

>[!tip] Usage
>```java
>Math.abs(x)
>```

```java

public class Main {
    public static void main(String[] args) throws Exception {

        // pass the value directly
        // output the result to screen
            // Just found out that it automatically like ... do the little `%.xf` thing ( where x is number )
        System.out.println("\nPositive of '-5' = " + Math.abs(-5) + "\n");

        // DECLARE negative_num: FLOAT
        float negative_num = -6.456f;
        // DELCARE positive_num: FLOAT
        float positive_num = (float) Math.abs(negative_num);

        // output the result to the screen
        System.out.printf("Postive Number = %.3f\n\n", positive_num);

    }
}

```

## Max Function

>[!tip] Usage
>```java
>Math.max()
>```

### Example 1: Converting Python Code into Java

```python

print(max(1, 2, 3, 4, 5))

```

>Its not as simple as you think

```java

public class Main {
    public static void main(String[] args) throws Exception {

        // pass in values directly
        System.out.println("\nMaximum Value Between ( 1, 2, 3, 4, 5 ) = " + Math.max(1, Math.max(2, Math.max(3, Math.max(4, 5)))) + "\n");

    }
}

```

>[!tip]
>Its better if you just make an [[Arrays, Tuples, Sets - Java - Version Not Good| array]] of integers and find the maximum value; as you are going to be doing below $\downarrow$

### Example 2: Using Arrays

```java

public class Main {
    public static void main(String[] args) throws Exception {

        // DECLARE ARRAY numbers[4]: INTEGER
        int [] numbers = {1, 2, 3, 4, 5};
        // intialise a variable to hold the first value of array
        int max = numbers[0];

        // iterate through the array
        for(int i = 0; i < numbers.length; i++){

            // compare first value of array to the rest ---> using the for loop
            max = Math.max(max, numbers[i]);

        }

        // output the answer to the screen
        System.out.printf("\nMaximum Value = %d\n\n", max);

    }
}

```

>[!info]
>Why have we declared `int max = numbers[0]` ( *$\leftarrow$ take the first value of array* )?
>>[!note]
>>This is because the `Math.max()` function works by making a **comparison** with the value; <span style="color: green;">You need to pass in <strong>2 values</strong></span> inside the `()`!
>

>[!warning]
><span style="color: red;">Do <strong>not</strong></span> *declare* variable `max` inside the `for` loop; as somethings happen with memory and we cannot use it outside the `for` loop.

## Min Function

>Now we know that we need to make a comparison when using; I am not going to be writing the same explanation again;
>Lets go programming then!!!

### Example 1: Passing Value Directly

```java

public class Main {
    public static void main(String[] args) throws Exception {

        // pass in values directly
        System.out.println("Minimum Value = " + Math.min(1, Math.min(2, Math.min(3, Math.min(4, 5)))));

    }
}

```

### Example 2: Using Arrays

```java

public class Main {
    public static void main(String[] args) throws Exception {

        // DECLARE ARRAY numbers[5]: INTEGER
        int[] numbers = {1, 2, 3, 4, 5};
        // initialise a variable to hold the first value of array
            // because again; we need to make the comparison
        int min = numbers[0];

        // iterate through the array
        for(int i = 0; i < numbers.length; i++) {

			// compare first value wiht other values ---> through iteration
            min = Math.min(min, numbers[i]);

        }

        // output the result on the screen
        System.out.printf("\nMinimum Value = %d\n\n", min);

    }
}

```

## PI in Java

In [[Python Math Module#PI in Python | Python]], to use PI ( *more accurate value* ), we **need** to import `import math` to be able to just do `math.pi`

But here, we do *not* need to!

```java

public class Main {
    public static void main(String[] args) throws Exception {

        // PI in Java
        // i do not know what to write here... lets go to coding
        
        // display PI directly
        System.out.println("\nValue of PI = " + Math.PI);

        // DECLARE PI: DOUBLE
            // PI in this case is a constant
        final double PI = Math.PI;

        // display the contents of variable PI
            // need to add `%.15f`, else will only display 6 decimal places
        System.out.printf("\nValue of PI = %.15f\n\n", PI);

    }
}

```

## Ceil Function

>I need someone explain me Ceil and Floor methods / functions
>Because its not what I wrote down in the Python Notes

```java

public class Main {
    public static void main(String[] args) throws Exception {

        // DECLARE PI: DOUBLE
        double PI = Math.PI;

        // applying `Math.ceil()` function
        double ceiled = Math.ceil(PI);
        
        // output the value of variable PI
        System.out.println("\nPI = " + PI);

        // output result to the screen
        System.out.printf("\nValue after Applying Function = %.4f\n\n", ceiled);

    }
}

```

### Output of `Math.Ceil` Function

```console

3.141592653589793

Value after Applying Function = 4.0000

```

## Floor Function

```java

public class Main {
    public static void main(String[] args) throws Exception {

        // DECLARE PI: DOUBLE
        double PI = Math.PI;

        // applying `Math.ceil()` function
        double flooring = Math.floor(PI);
        
        // output the value of variable PI
        System.out.println("\nPI = " + PI);

        // output result to the screen
        System.out.printf("\nValue after Applying Function = %.4f\n\n", flooring);

    }
}

```

### Output of `Math.floor` Function

```console

PI = 3.141592653589793

Value after Applying Function = 3.0000

```

## Square Root Function

```java

public class Main {
    public static void main(String[] args) throws Exception {

        // squarooting I guess! ( with type cast )

        // DECLARE num: INTEGER
        int num = (int) Math.sqrt(144);
        // DECLARE x: FLOAT
        float x = (float) Math.sqrt(5.904f);
        // DECLARE PI: DOUBLE
        double PI = Math.PI;

        // display the results to screen
        System.out.printf("\nSquare root of 144 = %d\n", num);
        System.out.printf("\nSquare root of 5.904(f) = %f\n", x);
        System.out.printf("\nSquare root of `Math.PI` = %f\n\n", PI);

    }
}

```

>[!info]
>Here I used Type Cast
>So `Math.sqrt()` is **not** of type `double`!!!

## Trigonometry Functions

>As I said, I am not going to be writing any explanation here

```java

public class Main {
    public static void main(String[] args) throws Exception {

        // Sine
        System.out.println("\nSine of PI / 6 = " + (Math.sin(Math.PI / 6)));
        // Cosine
        System.out.println("\nCosine of 0 = " + Math.cos(0));
        // Tangent
        System.out.println("\nTangent of 90 = " + Math.tan(90) + "\n");

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