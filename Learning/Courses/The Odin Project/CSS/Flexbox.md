---
Alias: Flexbox CSS
Tag: CSS, TheOdinProject, basics
Author: S.Sunhaloo
Date: 2023-12-20
Type: CSS Flexbox
Status: Completed
---

## List of Contents

- [[Flexbox#Flex Containers and Flex Items| Flex Containers and Flex Items]]
- [[Flexbox#Growing and Shrinking| Growing and Shrinking]]
- [[Flexbox#Axes | Axes]]
- [[Flexbox#Alignment | Alignment]]

# Start Flexing

It is a way to **arrange** items into *rows* or *columns*.
These items will *flex* ( *grow* / *shrink* ) depending on what rules that you have defined.

## Interactive Examples

For you to understand *Flexbox*; we need to show you some code and you need to **play** ( *like you play with your...* ) with the code and experiment with it.

Thus I will be including the links to them.

- [First Interactive Example](https://www.theodinproject.com/lessons/foundations-introduction-to-flexbox#lets-flex)

## Flex Containers and Flex Items

Flexbox is not just a **single** CSS *property* but a whole toolbox of properties that you can use to put things where you need them.

Some of these *properties* belong to the ***flex container*** while some belongs to the ***flex item***

- A flex **container** is *any* element ( *i.e tags, etc* ) that has `display: flex` on it.
- A flex **item** is any element that lives directly *inside* the flex container

![[flex container and flex item.png]]

### Confusion Incoming!!!

A element can be **both** a flex *container* and a flex *item* ( *insert head exploding / prophecy meme here* ).

In other words, you can put `display: flex` on a flex **item** and then use *flexbox* to arrange its children.

![[both flex container and flex item.png]]

>I get it now, its like the *Russian Doll Thing*


### Example

Here is an example of how we can create and nest multiple flex **containers** and **items** to build complex layouts. The following image was achieved using **only** *flexbox* to

- arrange
- size
- place

these various elements

![[flex box powerful tool.png]]

## More Help

Here are some additional tutorials for Flexbox:

1. [Interneting is Hard](https://internetingishard.netlify.app/html-and-css/flexbox/index.html)
2. [Scrim on Flexbox](https://scrimba.com/learn/flexbox/your-first-flexbox-layout-flexbox-tutorial-canLGCw)

# Growing and Shrinking

## The Flex Shorthand

The `flex` declaration is a shorthand for 3 *properties* that you can set on a flex **item**.

- These *properties* affect how flex **items** *size* themselves within their container.

>[!note] What are Shorthand Properties?
>***Shorthand properties*** are CSS properties that let you set the values of multiple other CSS properties simultaneously. Using a shorthand property, you can write more concise (and often more readable) style sheets, saving time and energy.

In this case, `flex` is actually

- `flex-grow`
- `flex-shrink`
- `flex-basis`

For Example:

```css

div {

	flex: 1;

}

```

The `flex: 1` means that:

- `flex-grow: 1`
- `flex-shrink: 1`
- `flex-basis: 0`

If you see the *flex* shorthand with only 1 value; this means that this value is being applied to `flex-gow`

So when we put `flex: 1` on our divs, this corresponded to `flex: 1 1 0`

### Flex Grow

It only expects a single number as its value ( because he it a mother-fucking *CHAD* ), that number is used as flex-item's *growth factor*

When we *write* `flex: 1` in every div inside our container, we are telling the div to **grow** the *same* amount ( *linearly* ).

But if we *write* `flex: 2`, it means that the div would **grow** *2x* the size of others.

- [Second Interactive Example - Flex Grow](https://www.theodinproject.com/lessons/foundations-growing-and-shrinking#Flex-grow)

### Flex Shrink

What does the word *shrink* means? Well if you do not know; you have a problem!

>Hint: It is the opposite of "*grow*"

- `flex-shrink` only ends up being applied if the size of all flex **items** is *larger* than their parent **container**

The default shrink factor is `flex-shrink: 1`, which means that the items will shrink evenly.

- If you do **not** want an item to *shrink*
	- You can use: `flex-shrink: 0`
- If you want your items to *shrink* at a **higher** $\uparrow$ rate
	- You can increase the value for `flex-shrink`
		- Example: `flex-shrink: 4`

>[!note]
>Flex **Items** do **not** necessarily respect your given values for `width`
>- This is **not** a *bug*, but it could be confusing behaviour if you are not expecting it.

### Flex Basis

It simply sets the **initial size** of the flex **item**.

This means that if we are going to be applying `flex-grow` or `flex-shrink`, its going to *grow* or *shrink* from the baseline size.

- Shorthand value defaults to `flex-basis: 0%`

	Using `auto` as in `flex-basis: auto` tells the item to check for a **width declaration**

> #### Important note about flex-basis:
> 
> There is a difference between the default value of `flex-basis` and the way the `flex` shorthand defines it if no `flex-basis` is given. The actual default value for `flex-basis` is `auto`, but when you specify `flex: 1` on an element, it interprets that as `flex: 1 1 0`. If you want to _only_ adjust an item’s `flex-grow` you can simply do so directly, without the shorthand. Or you can be more verbose and use the full 3 value shorthand `flex: 1 1 auto`, which is also equivalent to using `flex: auto`.

> #### What is flex: auto?
> 
> If you noticed, we mentioned a new flex shorthand `flex: auto` in the previous note. However we didn’t fully introduce it. `flex: auto` is one of the shorthands of flex. When `auto` is defined as a flex keyword it is equivalent to the values of `flex-grow: 1`, `flex-shrink: 1` and `flex-basis: auto` or to `flex: 1 1 auto` using the flex shorthand. Note that `flex: auto` is not the default value when using the flex shorthand despite the name being “auto” which may be slightly confusing at first. You will encounter and learn more about `flex: auto` and its potential use-cases when reading through the assignment section.

### Flex Wrap

This was not covered in [[The Odin Project Data View | The Odin Project]], but learned it from this [video](https://www.youtube.com/watch?v=u044iM9xsWU)

![[Flexbox CSS Kevin Powell#Flex Wrap]]

#### More Flex Help

- [MDN Doc](https://developer.mozilla.org/en-US/docs/Web/CSS/flex)


# Axes

## Flex Direction

The **orientation** of *items* within a flex **container** can be controlled by the the *property* `flex-direction`

- The most confusing thing about *flexbox* is that it can work either **horizontally** or **vertically**.
	- But we have some rules that changes the direction depending on what you are trying to do
- The **default** direction for flex **container** is either `horizontal` or `row`
	- But we can change the direction to `vertical` or `column`

For Example:

```css

.flex-container {

	flex-direction: column;

}

```

## Here comes The Axes

- No matter which direction we are using, we need to visualise our flex-containers as having 2 axes:

	1. Main Axis $\Rightarrow x \ axis$
	2. Cross Axis $\Rightarrow y \ axis$

It is the direction of these axes that changes when the `flex-direction` is *changed*

- `flex-direction: row` $\Rightarrow$ Puts **main** axis *horizontal* ( left to right $\rightarrow$ )
- `flex-direction: columns` $\Rightarrow$ Puts the **main** axis *vertical* ( top to bottom $\downarrow$ )

Here is the third [Interactive Example](https://www.theodinproject.com/lessons/foundations-axes#axes
)
From the Interactive Example for above $\uparrow$; We need to remember [[Flexbox#Flex Basis | Flex Basis]]. And what does *flex basis* do?

It will initialise a **baseline size**! Thus if we only do `flex: 1` or even `flex: 1 1`. It will **not** work as the baseline size will be equal to 0.

$$Baseline \ Size = 0 \Rightarrow Not \ Going \ To \ Work$$

Thus we need to give it a baseline *height* and in this example they gave the rule `height: 70px`... Why not `width: 70px`? This is because we have changed the *flex-direction* to **column**.

> There are situations where the behavior of flex-direction could change if you are using a language that is written top-to-bottom or right-to-left, but you should save worrying about that until you are ready to start making a website in Arabic or Hebrew.

### Flex Box Visual Cheat sheet

This is a website that combines every Flex Box property and puts and imaged next to it. Click [here](https://flexbox.malven.co) to visit the website.

For an interactive version; Click [here](https://scrimba.com/learn/flexbox/main-axis-and-cross-axis-flexbox-tutorial-cz94MT8) to go to that website.

# Alignment

![[Flexbox Alignment]]