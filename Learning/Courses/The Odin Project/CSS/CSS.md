---
Alias: The Odin Project CSS
Tag: CSS, TheOdinProject, basics
Author: S.Sunhaloo
Type: CSS Introduction
Date: 2023-11-26
Status: Completed
---

## List of Contents

- [[CSS#First of All | First of All]]
- [[CSS#Basic Syntax | Basic Syntax]]
- [[CSS#Selectors | Selectors]]
	- [[CSS#Universal Selectors | Universal Selectors]]
	- [[CSS#Type Selectors | Type Selectors]]
	- [[CSS#Class Selectors | Class Selectors]]
	- [[CSS#ID Selectors | ID Selectors]]
	- [[CSS#Grouping Selectors | Grouping Selectors]]
	- [[CSS#Chaining Selectors | Chaining Selectors]]
- [[CSS#Descendant Combinator | Descendant Combinator]]

# First of All

To be able to use CSS file with HTML file. We need to link them together with this tiny piece of code in the *HTML* file

### HTML File

```html

<!-- link tag -->

<link rel="stylesheet" href="index.css">

```

- Now we can go into the "*index.css*" file ( *or whatever its fucking called* ) and then start to use it.

>[!info] Some Information on `link` tag
>Placed inside the `<head>` tag
>- Self Closing Tag
>- Attributes Includes:
>	- `rel` = Specifies the relationship between *HTML* file and *CSS* file
>	- `href` = As we know, it find the **location** on the file

>[!note] Some *pros*
>Some *pros* of writing the Properties **separately**
>1. HTML file will be **cleaner** and **smaller**
>2. CSS is edited in **one** place only
>	- Handy for websites with many pages that all share similar styles

# Basic Syntax

```css

div.bold-text{
	font-weight: 700;
}

```

### Explanation

- `div.bold-text` is the **selector**
- `font-weight` is the **property**
- `700` is the **value**

## Selectors

Refers to the HTML *elements* to which CSS rules will be applied to. Here are some common ( *most widely used $\rightarrow$* but more do exists ) selectors used

### Universal Selectors

It will select elements of any type. The syntax is an `*`.

In the example below; every *element* will have the colour *purple*

```css

* {
	color: purple;
}

```

### Type Selectors

Selects all elements of the give element type

#### HTML File

```html

<div>Hello, World!</div>
<div>Hello, World!</div>
<p>Hi...</p>
<div>Hello, World!</div>

```

#### CSS File

```css

div {
	color: grey;
}

```

In this case, only the text **inside** the `div` element will be *grey* in color. The text **inside** the `p` element will still be black

### Class Selectors

Selects **all** elements in a give class; it is an *attribute* placed **inside** an HTML element.

#### HTML File

```html

<div class="test">This is a test text</div>

```

#### CSS File

```css

.test {
	color: green;
}

```

>[!note] Class Selectors Usage
>- Classes are not required to be **specific** to a particular *element*
>- You can use the **same** class on as **many** element as you want

### ID Selectors

Similar to [[CSS#Class Selectors | class selectors]]; they will select an element with the given ID

- It is another **attribute** that you place **inside** of and *element*

#### HTML File

```html

<div id="title">About Page</div>

```

#### CSS File

```css

#title {
	background-color:grey;
}

```

>[!info]
>Instead of using `.` like in the "*class*" selector; we use `#` for "*id*" selectors

>[!warning]
>- Do **not** *overuse* the "*id*" selector to much
>	- Most of the time, "*class*" selectors will work fine
><p align="center" style="color: white:">You should use IDs sparingly ( <em>if at all</em> )</p>

### Grouping Selectors

We use this when some *selectors* have the same declarations.

#### Example:

```css

/* class "read" */
.read {
	color: white;
	background-color: black;
	/* class "read" unique declarations */
}

/* class "unread" */
.unread {
	color: white;
	background-color: black;
	/* class "unread" unique declarations */
}

```

In the above $\uparrow$ example; we can see that we have 2 **different** classes. But if you take a close look at both classes, you will be able to see that their "*unique declarations*" is the **same**.

Hence we can re-write it as:

```css

/* class "read" and class "unread" will share the same declarations */
.read,
.unread {
	color: white;
	background-color: black;
}

/* unique declarations */

/* class "read" unique declarations */
.read {
	font-family: Arial, Helvetica, sans-serif;
}

/* class "unread" unique declarations */
.unread {
	font-family: 'Times New Roman', Times, serif;
}

```

For the **similar** declarations, we can *group* them together
But they can still have their own **unique** declarations but just *re-writing* them again

- If you have a lot of "*classes*" or "*id*" that are similar; you the second one as it is **faster** to write

### Chaining Selectors

Look at the `CSS` code below

```html

<div>
	<div class="subsection header">Followers</div>
	<p class="subsection preview">This is where we keep all of our followers</p>
</div>

```

In this scenario we find that both the `div` and `p` element has the **class** attribute called "*subsection*" ( look at first word only ).

What if we only want to change the `div` element?

```css

.subsection.header {
	color: green;
}

```

#### Explanation

- `.subsection.header` will any element that has both the `subsection` and `header` classes.
	- There is not `<space>` in between them
- Can also be used in conjunction with "*id*" selectors

#### Example

```html

<div>
	<div class="subsection header">Followers</div>
	<p class="subsection" id="preview">This is where we keep all of our followers</p>
</div>

```

Hence, the code will become like this:

```css

/* manipulating the "div" element only */
.subsection.header {
	color: purple;
}

/* manipulating the "p" element only */
/* grouping both class and id */
.subjection#preview {
	color: blue;
}

```

In general you **cannot** *chain* more than one [[CSS#Type Selectors | type selectors]] from the above $\uparrow$ ( *like check it's HTML and CSS* )

- We cannot have `divp` or `<divp>` this does not fucking exists ma dude

### Descendant Combinator

Allows us **combine** multiple *selectors* differently that either *grouping* or *chaining* them - they show a **relationship** between the selectors

- Only cause elements that match the last selector to be selected if they also have an ancestor ( *parent, grandparent, etc* ) that matches the previous selector

#### Check this Example

##### HTML File

```html

<div class="ancestor">

	<!-- 1 -->

	<div class ="contents">

		<!-- 2 -->

		<div class="contents"><!-- 3 --></div>

	</div>

</div>

<div class="contents"><!-- 4 --></div>

```

##### CSS File

```css

.ancestor .contents {

	background-color="#ff0048"

}

```

In the above $\uparrow$ example, the "*descendant combinator*" will only **select** *1, 2, 3* but **NOT** *4*.

- This is because *4* is not **nested** inside the "*ancestor*" class
- For the nested part; there is really **no** limit to this

In the next part we are going to start playing with **properties**.

>I think it deserves its "*own*" notes / file so that we can add more as we learn. Hence;

## Properties

![[CSS Properties]]