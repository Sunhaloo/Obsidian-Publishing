---
Alias: Arrays, Tuples and Sets In Java
Tag: java, basics, 1D-Array, 2D-Array
Author: S.Sunhaloo
Type: Arrays ( 1D / 2D )
Date: 2024-06-12
Status: In-Progress
---

## List of Contents

- [[Arrays, Tuples, Sets - Java - Version Not Good#Importing Java Arrays Library| Java Arrays Library]]

## One Dimensional Arrays

- [[Arrays, Tuples, Sets - Java - Version Not Good#One Dimensional Arrays ( 1D-Arrays )| One Dimensional Arrays ( 1D-Arrays )]]
	- [[Arrays, Tuples, Sets - Java - Version Not Good#Creating 1D-Arrays| Creating 1D-Arrays]]

## Two Dimensional Arrays



---

### My Links

- [[Arrays, Tuples, Sets - Java - Version Not Good#Socials| Link to Social]]

---

## Importing Java Arrays Library

>[!warning]
>Java has a utility library called `Arrays`, where we can access it by importing `import java.utils.Arrays`
>
>Hence, where we are going use functions that are *in* the `Arrays` library, we are going to **import** it!

# One Dimensional Arrays ( 1D-Arrays )

>[!info]
>Java's Arrays ( *creation* ) syntax's is *similar* to [[Arrays - C | C]]
>>Take the word "*similar*" very lightly!

# Creating 1D-Arrays

```java

public class Main {
    public static void main(String[] args) throws Exception {

        // First Method

        // DECLARE ARRAY cars[8]: STRING
        String[] cars = {"Rx-7", "Supra", "AE-86","GT-86", "GTR-R32", "McLaren-P1", "Porsche-918-Spyder", "Koenisegg-Regera-R", "Lancer-MR9"};
        // DECLARE ARRAY numbers[4]: INTEGER
        int[] numbers = {1, 2, 3, 4, 5};
        // DECLARE ARRAY bool[1]: BOOLEAN
        boolean[] bool = {true, false};

        // Second Method
        
        // DECLARE ARRAY price[2]: DOUBLE
            // in this case we only have the size, no values has been added yet!
            // this is normally used, when we ONLY know the size of the array ( not the values )
        double[] price = new double[3];

        // adding the values
        price[0] = 250.99;
        price[1] = 40.95;
        price[2] = 2.99;

    }
}

```

>[!note] Data Types of Array
>This part will be similar to [[Java Language#Equivalent of `type()` Function | Type Function]] with Arrays.
>>I will be update the code above $\uparrow$; but I will only include the code snippet for *type function*
>```java
>// NO need to convert to Object / Wrapper / Referenced data type
>System.out.println("\n" + cars.getClass().getSimpleName());
>System.out.println(numbers.getClass().getSimpleName());
>System.out.println(bool.getClass().getSimpleName());
>System.out.println(price.getClass().getSimpleName() + "\n");
>```
>>[!tip]
>><span style="color: green;">No</span> need to **convert** to [[Java Language#Primitive Data Types Type Function Usage | Object / Wrapper / Referenced]] datatype!

# Displaying 1D-Arrays

## Displaying Empty Arrays

>I will be including all the way in which we can print them in the single code block $\downarrow$

>[!warning]
>In java we **cannot** do things like:
>```python
># DECLARE ARRAY num[5]: INTEGER
>num = [None for x in range(6)]
>```
>Because Java is more traditional in the sense that we need to *declare* **first**, create the actual array in memory, then we can do things like adding, sorting, deleting values inside of the array!

```java



```

## Displaying Non-Empty Arrays

---

# Socials

- [**Instagram**](https://www.instagram.com/s.sunhaloo/)
- [**YouTube**](https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg)
- [**GitHub**](https://www.github.com/Sunhaloo)

---

S.Sunhaloo
Thank You!