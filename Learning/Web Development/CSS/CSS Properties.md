---
Alias: The Odin Project CSS Properties
Tag: CSS, TheOdinProject, basics
Author: S.Sunhaloo
Type: CSS Properties
Date: 2023-11-27
Status: Completed
---

## List of Contents

- [[CSS Properties#Colour and Background Colour | Colour and Background Colour]]
- [[CSS Properties#Typography Basics and Text-Alignment | Typography Basics and Text-Alignment]]
- [[CSS Properties#Image Manipulation | Image Manipulation]]

---

# Colour and Background Colour

## Colour Property

>[!info] Changes the *text* color
>- Can be used with:
>	1. HEX Values ( "*most used and the standard*" )
>	2. RGB Values
>	3. HSL Values


### Example: Changing *Text* Colour to grey

```css

html {

	color: grey;

}

```

```css

html {

	color: 808080;

}

```

- Both have the same effect
	- This is just to show you that for simple colours;
	- CSS can allow you to write it in English

## Background Colour

What can I say about this one; "*You are a fucking idiot if you do not understand this one!*"

### Example: Change *Background* Colour to Black

```css

html {

	background-color: black;

}

```

```css

html {

	background-color: #000000;

}

```

# Typography Basics and Text-Alignment

## Font Family

- Can be *single-valued* or *comma-separated list* of values

Determines what fonts each element uses

### Font Categories

1. **Serif** fonts
	- *Times New Roman*
	> I hate this font
	> - I hate *serif* fonts in general
1. ***Sans*** **Serif** fonts
	- Roboto
	- Ubuntu
	- Helvetica
	>These are the fonts that I like

>[!info] What if We do **NOT** have a Font?
>I we do **not** have a font then, the browser will automatically use the **next font** available
>>[!note] What is the Default Font?
>>If we have not specified any fonts to use;
>>- The browser will use `Times New Roman` ( "*fucking disgusting*" )


### Example: Changing the Font

```css

html {

	font-family: Arial;

}

```

```css

html {

	font-family: Arial, Helvetica, Times New Roman; 

}

```

## Font Size

Do I need to say something about this part; Okay I will say it. "*Go Fuck Yourself!*"

### Example: Changing the Font Size

```css

.class {

	font-size: 16px

}

#id {

	font-size: 12 px

}

```

## Text Alignment

The function / property `text-align` will align the **text** *horizontally* $\longleftrightarrow$

### Example: Aligning some things!

```css

html {

	text-align: center;

}

.ordered_list
.unordered_list {

	text-align: right;

}

```

# Image Manipulation

## Image Height

To keep an image's proportions correct; we need to use the `auto` value for the property `height`

```css

img {

	height: auto;

}

```


### Else

- The image's height can be anything that your heart desired

## Image Width

- Same as [[CSS Properties#Image Height | height]] but instead of `height`; we use `width`

```css

img {

	width: 250px;

}

```

## Combination of Height and Width

### Example:

```html

<img src="C:\Users\user_name\Desktop\test.png" alt="Landscape Photo" id="piece_of_shit"

```

```css

#piece_of_shit {

	height: auto;
	width: 500px;

}

```