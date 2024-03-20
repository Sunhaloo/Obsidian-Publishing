---
Alias: The Odin Project CSS Cascade
Tag: CSS, TheOdinProject, basics
Author: S.Sunhaloo
Type: CSS Specificity
Date: 2023-12-08
Status: Completed
---

## List of Contents



---

# Preview

We will now **combine** our knowledge of *selectors* with *C*!

What I mean by "*C*" is not the "*mother of all languages*" ( *my opinion - fuck you!* ); but the "*C*" in **CSS**

>[!info] What is CSS again?
>- C = Cascading
>- S = Style
>- S = Sheets

>[!tip] Remember Boys ( *and girls* )
>CSS will only do what we tell it to do!
>For Example:
>- If you wanted this specific paragraph to be blue, but instead if turned out like the other red paragraphs
>	- This is because **you** have not configured it well.
>- But we have an Exception: Default Style provided by the **Browse**.
>	- These default styles vary from Browser to Browser

# Specificity

I get it now!

Like the **CSS Declarations** have an order of priority you can say.

- *Inline* styles have the **highest** *specificity* compared to *selectors*
	- While each *selectors* has its **own** *specificity* level that contributes to how specific a declaration is.

## Specificity Order

### Highest *Priority* to Lowest *Priority*

<p align="center">Inline Styles<br>ID Selectors<br>Class Selectors | Type Selectors | Others</p>

**Specificity** will only be taken into account when an element ( *i.e tags* ) has **multiple**, **conflicting** declarations targeting it.

- An **ID** Selector will **always** beat any number of *class* selectors.
- A **Class** Selector will **always** beat any number of *type* selectors.
- A **Type** Selector will **always** beat any number of *less* specific selectors.

### Examples:

#### Example 1: Classes Selectors

```html

<div class="main">

	<div class="list subsection">Red Text</div>

</div>

```

```css

/* rule 1 */
.subsection {

	color: blue;

}

/* rule 2 */
.main .list {

	color: red;

}

```

As *rule 2* is more **specific**; it will be taking over *rule 1*. Hence, the text color will be <span style="color: red;">red</span>

#### Example 2: Classes and ID Selectors

```html

<div class="main">

	<div class="list" id="subsection">Blue Text</div>

</div>

```

```css

/* rule 1 */
#subsection {

	color: blue;

}

/* rule 2 */
.main .list {

	color: red;

}

```

As we have an **ID** Selector; it will take precedence over the *Class* Selector. Hence, the colour of the text will be <span style="color: cyan;">blue</span>

#### Example 3: A Bit More *Complex*

```html

<div class="main">

	<!-- Text Color will NOT be Blue -->
	<div class="list" id="subsection">Blue Text on Green Background</div>

</div>

```

```css

/* rule 1 */
#subsection {

	background-color: green;
	color: blue;

}

/* rule 2 */
.main #subsection {

	color: red;

}

```

In this example; we can see that the *first* rule is an **ID** Selector and the *second* rule combines the **ID** Selector with a **Class** Selector.

In this case; neither rule is *more specific* than the other.

- Hence, the *Cascade* will check the number of each selector type
	- Both rules have only 1 *ID* Selector
	- BUT, *rule 2* will have **higher** $\uparrow$ *specificity* as:
		- It has been combined with a class selector.

>[!note] In Simple Terms
>As the second rule is more *specific*; it will take effect over *rule's 1*
>```css
>
>color: blue;
>
>```

## Not Everything Adds Up to Specificity

### Example 1: 

```css

/* rule 1 */
.class.second-class {

	font-size: 12px;

}

/* rule 2 */
.class .second-class {

	font-size: 24px;

}

```

Here, the rules have the **same** *specificity*!

- Rule 1: [[CSS#Chaining Selectors | Chaining Method]]
- Rule 2: [[CSS#Descendant Combinator | Descendent Method]]

### Example 2:

```css

/* rule 1 */
.class.second-class {

	font-size: 12px;

}

/* rule 2 */
.class > .second-class {

	font-size: 24px;

}

```

This is the same thing as above; even though *rule 2* is using a *child combinator* ( $>$ ).

- It does **not** change it's *specificity*

### Example 3:

```css

/* rule 1 */
* {

	color: black;

}

/* rule 2 */
h1 {

	color: orange;

}

```

In this case; *rule 2* will have a **higher** ( $\uparrow$ ) *specificity* and <code><span style="color: orange">orange</span></code> would take effect for this element.

- Rule 2 uses the [[CSS#Type Selectors | Type Selectors]]
	- Has the **lowest** specificity value
- Rule 1 uses the Universal Selector
	- Has **no** specificity

# Inheritance

Check this out:

```html

<div id="parent">

	<div class="child"></div>

</div>

```

```css

#parent {

	color: red;

}

.child {

	color: blue;

}

```

Even though, we have an **ID** Selector which has a higher specificity; The reason that it will **not** be applied is because the *style* directly targets the `child` class.

### Rule Order

>[!note]
>Whichever rule was the **last** defined is the winner!

```css

.alert {

	color: red;

}

.warning {

	color: yellow;

}

```

If an element has both the `alert` and `warning` class, we would see that the last defined rule which is, in this case, `warning` will take effect over `alert`