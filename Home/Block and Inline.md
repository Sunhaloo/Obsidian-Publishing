---
Alias: CSS and HTML Block | Inline
Tag: HTML, CSS, TheOdinProject, basics
Author: S.Sunhaloo
Date: 2023-12-20
Type: Block and Incline
Status: Completed
---

## List of Contents

- [[Block and Inline#Introduction | Introduction]]
- [[Block and Inline#Block V/s Inline | Block v/s Inline]]
- [[Block and Inline#Divs and Spans | Divs and Spans]]

# Introduction

As we know we have the [[Box Model]] which has shown us that everything can be fit into a **rectangular box**. But we can also manipulate these *boxes*.

But we can modify the *box calculation* by changing the `display` *property*

CSS has two box types:

1. Block / `block`
2. Inline / `inline`

- `display`: Controls how [[HTML]] elements appear on the webpage.

# Block v/s Inline

## Block Elements

Most of the elements (  *i.e tags - like I call them tags* ) that we have learned so far are **block** elements.

This means that:

```css

display: block;

```

- Block elements on the page *stacked* **atop** each other
	- Each new element *starting* on a **new line**
	- Examples:
		1. Heading Elements
		2. Paragraphs Elements
		3. Image Elements

# Inline Elements

- They do **not** start on a *new line*
	- Examples:
		1. `<a>` Tag
		2. Divs
		3. Spans

*Padding* and *Margin* behave differently on **inline** elements.

>[!note]
>In general, you do **not** want to put extra *padding* or *margin* on **inline** elements

## The Middle Ground Inline-Block

They behave like **inline** elements but with a **block-style** padding and margin.

```css

display: inline-block;

```

- Useful tool to know about
	- Nevertheless, in practice, most probably going to be using `flexbox` to line up a bunch of boxes

# Divs and Spans

They have no particular meaning to their content. They are just generic boxes that can contain anything.

`div` is a **block-level** element by *default*. Divs allow us to divide the page into different blocks and apply styling to those blocks.

## Divs

```html


<div class="introduction">
   <h2>Introduction</h2>
</div>

<div class="main-content">
   <h2>Main Content</h2>
</div>

<div class="contact-us">
   <h2>Contact Us</h2>
</div>

```

```css

div {
  padding: 30px;
  text-align: center;
  margin-bottom: 10px;
  color: #EEEEEE;
}

.introduction {
  background-color: #548CA8;
}

.main-content {
  background-color: #476072;
}

.contact-us {
  background-color: #334257;
}

```

## Spans

```html

<p>
  Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
  eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad
  minim veniam, <span class="highlight">quis nostrud <a href="https://www.dictionary.com/browse/exercitation">exercitation</a>
  ullamco laboris</span> nisi ut aliquip ex ea commodo consequat.   
</p>

```

```css

.highlight {
  background-color: yellow;
}

```

# Normal Flow

This concept is implied in the [[The Box Model | Box Model]] but isn't laid out specifically.

For more information about *normal flow*; head over to ["Normal Flow" from MDN](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Normal_Flow)

## More Help

The *Digital Ocean* tutorial has a couple of great examples that clarify the difference between `inline` and `inline-block`. Click [here](https://www.digitalocean.com/community/tutorials/css-display-inline-vs-inline-block) to learn more about it