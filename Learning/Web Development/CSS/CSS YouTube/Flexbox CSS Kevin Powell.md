---
Alias: CSS Flexbox Kevin Powell's Tutorial
Tag: CSS, YouTube, tutorial, basics
Author: S.Sunhaloo, Kevin Powell
Date: 2023-12-23
Type: CSS Flexbox
Link: https://www.youtube.com/watch?v=u044iM9xsWU
Status: Completed
---

## List of Contents

- [[Flexbox CSS Kevin Powell#Starting Tutorial | Starting Tutorial]]
- [[Flexbox CSS Kevin Powell#Code | Code]]

---

>[!tip]- Flexbox Cheat Sheet
>	Click [here](https://kevin-powell.ck.page/25792a66b4) to take a look at his Flexbox Cheat Sheet
>>[!warning]
>>Needs to subscribe to his newsletter; *What a bummer*!

---

# Starting Tutorial

So whenever we put `display: flex;` meaning that we are now using **flexbox**.

- *Block* Level Elements becomes *flex* **items**

## What does a Flex Item Wants to Do?

It wants to be as **small** as it can *possibly* get while maintaining *everything* on **1 line**

One more thing, the *children* items have a lot of **control** over the different behaviours that are currently taking place.
The *parent* will set the **ground** rule but the *children* can also have *control* or sometimes **ultimate control**


## [[CSS - Flexbox#Flex Grow| Flex Grow]]

In the example; from what I can understand is that `flex-grow` or `flex: 1` will allow the content ( *in this case `<li>`* ) to grow and fill the space


## [[CSS - Flexbox#Flex Shrink| Flex Shrink]]

This one is similar to [[Flexbox CSS Kevin Powell#Flexbox Flex Grow Flex Grow | Flex Grow]]. But now, it will **shrink** to fit the smaller *window*

## Flex Wrap

This is new to me and was not covered in [[The Odin Project Data View | The Odin Project]]. Basically, we will have something called *overflow* where if we continue to decrease the *window* size; the contents will just disappear in a way.

Thus we use `flex-wrap: wrap` to allow the *contents* to **wrap**.

- This is used in the **Parent** *items*


# Code

```html

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Flexbox YouTube Tutorial</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    
    <h1>Flexbox Kevin Powell's Tutorial</h1>

    <header>
        <nav>
            <ul class="nav-list">
                <li><a href="#">Home</a></li>
                <li><a href="#">About</a></li>
                <li><a href="#">Service Information</a></li>
                <li><a href="#">Blog</a></li>
                <li><a href="#">Contact</a></li>
            </ul>
        </nav>
    </header>

</body>
</html>

```

```css

.nav-list {

    display: flex;
    gap: 1rem;
    flex-wrap: wrap;
    /* the line below will use the cross axis instead of main axis */
    /* flex-direction: column; */
    justify-content: center;
    /* the line below will make all of the list go to the right */
    /* justify-content: flex-end */
    /* the line below is very rare to use */
    /* justify-content: space-around; */
    /* instead we can use the line below */
    /* justify-content: space-evenly; */

    margin: 0;
    padding: 0;
    list-style-type: none;

}

.nav-list li {

    border: 3px dotted blue;
    /* flex-grow: 1; */
    /* flex-shrink: 1 */
    /* flex-basis: auto; */

}

header {

    border: 5px solid red;

}

```