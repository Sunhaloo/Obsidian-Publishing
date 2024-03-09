---
Alias: The Odin Project HTML
Tag:  HTML, TheOdinProject, basics
Author: S.Sunhaloo
Type: HTML
Date: 2023-11-09
Status: Completed
---

## List of Contents

- [[HTML#HTML v/s CSS v/s JavaScript / Python| HTML v/s CSS v/s JavaScript / Python]]
- [[HTML#HTML| HTML]]
	- [[HTML#Setting Up Basic HTML Structure / Boilerplate | Setting Up Basic HTML Structure]]
	- [[HTML#Writing Contents | Writing Contents]]

## HTML v/s CSS v/s JavaScript / Python

- **HTML ( *Hyper Text Markup Language* ):** The *building blocks* of a website; handles the structure, and raw data.
- **CSS ( Cascading Style Sheet ):** The *thing* that adds **style** to a website; beautifies the website
- **JavaScript / Python:** These add **functionality** to website; making a game or interactive buttons, and more.

# HTML

Before we get into things; I suggest knowing how to write comments

>[!tip] Writing Comments
>```html
>
><!-- Comments goes here -->
>
>```
>OR
>```html
>
><!--
>Comments can be
>MULTI-LINED !?!
>-->
>
>```

>[!tip]
>In VS Code, you can press <kbd>Ctrl</kbd> + <kbd>/</kbd> to **comment** and **uncomment** any  line!

# Setting Up Basic HTML Structure / Boilerplate

## Elements and Tags

From what I understand; there are tags ( "*which I already know*" ) and there are elements.

**Elements** are anything that are *surrounded* by tags.

```html

<p>This is an element surrounded by paragraph tags</p>

```

Where:

- `<p>` is the **opening** tag
- `This is an element surrounded by paragraph tags` is the content inside the tags
- `</p>` is the **closing** tag

>Think of the elements as **container** for *content*

>[!note]
>Some **tags** does not need to be closed!
>- Self Closing or Empty Elements
>>[!info]
>>List of Predefined Tags: [devloper.mozilla.org](https://developer.mozilla.org/en-US/docs/Web/HTML/Element)

>I think that you can use "*Element*" and "*tag*" interchangeably

## HTML Boilerplate

Every html file has a basic structure ( *the `<!DOCTYPE>` thing in VS Code* ). We are now going to be making a some *html* files.

### Steps

#### Make a Folder and a HTML File

- I suggest making a folder on the "*Desktop*" so that the file can be easily accessible even if you are a mouse user

>[!tip] Folder and HTML File Specifications
>**Folder Name:** Website
>**HTML File Name:** index.html

### The DOCTYPE

>[!tip]- What is the "*DOCTYPE*"
>As of this time of writing; **HTML5** is the latest version of *HTML*
>- The purpose is to let the **browser** know what version of *HTML* to user to **render** the document
>Nevertheless, we will **not** be using any other version of HTML ( "*because why would you!*" )

>[!tip] Usage
>```html
>
><!-- Browser will use HTML5 -->
><!DOCTYPE html>
>
>```

#### I have a confession

If you are using **VS Code** ( "*which you should be using*" ). You can just type `!` followed by <kbd>Tab</kbd> or <kbd>Enter</kbd> it will then give you this:

- I still do not know how to do that in Neovim / NVChad

```html

<!DOCTYPE html>

<html lang="en">

<head>

    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>

<body>
</body>

</html>

```

>But I will be following The Odin Project "*way*" also.

### HTML Element

We are now going to add our `<html>` tag!

```html

<!-- Browser will use HTML5 -->
<!DOCTYPE html>

<!--
html opening tag
with attribute language
-->
<html lang="en">

<!-- html closing tag -->
</html>

```

### Head Element

This is where we will place our **metadata** ( *data about the HTML file* )  about our webpages.

```html

<!-- Browser will use HTML5 -->
<!DOCTYPE html>

<!--
html opening tag
with attribute language
-->
<html lang="en">

<!-- head opening tag -->
<head>
<!-- head closing tag -->
</head>

<!-- html closing tag -->
</html>

```

>[!warning] NOTE
>Except for the [[HTML#Meta Element| meta element]], we should **not** write anything in the *head tag*

### Meta Element

The `<meta>` tag is a *self-closing* tag and **attributes** are passed into it.

Below $\downarrow$ are some `<meta>` tag that we need to add

#### Character / Charset Encoding

To use the encoding `UTF-8`, add this in the **head** tag

```html

<!-- place these inside the head element -->

<!-- controls the encoding -->
<meta charset="UTF-8">

```

#### Viewport / Layout

To control the layout; use the `<meta>` tag down below.

```html

<!-- controls the initial layout -->
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<!-- I think that the attributes are pretty self-explanatory -->

```

This is done so that **mobile** devices are able to *comfortably* view the website ( *according to their device's width* )

### Title Element

I think we all know that this does; it **display** the *name* of the page in the little tab bar.

```html

<!-- shows the name in the tab bar -->

<!--
opening and closing in one line
this is because, we do not need to write
multiple lines in the 'title' tag
-->
<title>YouTube</title>

```

>[!note]
>The [[HTML#Meta Element| "meta"]] and [[HTML#Title Element| title]] tag are placed inside the [[HTML#Head Element| head tag]]

### Body Tag

The `<body>` tag is where we are going to write our stuff. This is where all the contents ( *images*, *sounds*, and more ) will go.

- This is written **outside** the `<head>` tag and inside the `<html>` tag.

```html

<!-- body tag -->

<!-- opening tag -->
<body>

<!-- closing tag -->
</body>

```

## Final Code

The final code should look like this

```html

<!-- Browser will use HTML5 -->
<!DOCTYPE html>

<!--

    html opening tag
    with attribute language

-->
<html lang="en">

<!-- head opening tag -->
<head>

    <!-- controls the encoding -->
    <meta charset="UTF-8">

    <!-- controls the initial layout -->
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <!--

        opening and closing in one line
        because not writing many things

    -->
    <title>Test</title>

<!-- head closing tag -->
</head>

<!-- body opening tag -->
<body>

<!-- body closing tag -->
</body>

<!-- html closing tag -->
</html>

```

### Check Validation of Code

To check if your "*markup*" is good; go to [validator.w3.org](https://validator.w3.org/#validate_by_upload)

>I personally like to upload the whole file

# Writing Contents

## Paragraph

To write "*simple*" / normal text; you just need to type your "*text*" into the `<body>` tag

>[!tip] Usage
>```html
>
><p>This text is inside a paragraph tag</p>
>
>```

## Headings

What can I say about headings... They are headings! We have a selections of heading ( "*6 in total*" )

>[!tip] Usage
>```html
>
><!-- Headings Tag -->
>
><h1>Heading 1</h1>
>
><h2>Heading 2</h2>
>
><h3>Heading 3</h3>
>
><h4>Heading 4</h4>
>
><h5>Heading 5</h5>
>
><h6>Heading 6</h6>
>
>```

## Strong Element ( **Bold** )

The `<strong>`tag has an **opening** and **closing** tag. This can also be used in another *element*; for example, we need to *bold* something in a `<p>` tag. We need to place it inside the "*parent*" tag.

>[!tip] Usage
>- "*Bolding*" normal text
>```html
>
><strong>Bold Text</strong>
>
>```
>- `<strong>` inside another *tag*
>```html
>
><p><strong>Bold Text</strong> inside a "paragraph" tag</p>
>
>```

## "*EM*" Element ( *italic* )

The `<em>` just as the [[HTML#Strong Element ( **Bold** ) | strong]] tag has an **opening** and **closing** tag. Again, this can be used in another *element*; for example, we need to *italicize* something in a `<p>` tag. We need to place it inside the *parent* tag.

>[!tip] Usage
>- "*Italicizing*" normal text
>```html
>
><em>Italicized Text</em>
>
>```
>- `<strong>` inside another *tag*
>```html
>
><p><em>Italicized Text</em> inside a "paragraph" tag</p>
>
>```

## List

### Unordered Lists

An *unordered* list will have **bullet points** instead of *numbers*

>[!tip] Usage
>```html
>
><!-- Unordered List -->
><ul>
>
>	<li>Ayrton Senna</li>
>	<li>Michael Schumacher</li>
>	<li>Lewis Hamilton</li>
>	<li>Sebastien Vettel</li>
>	
></ul>
>
>```
>- Both the `<ul>` and `<li>` tag have **opening** and **closing** tags
>- The `<li>` tag is *indented* inside the `<ul>` tag


### Ordered Lists

An *ordered* list will have **numbers** instead of *bullet points*

>[!tip] Usage
>```html
>
><!-- Ordered List -->
><ol>
>
>	<li>Mercedes</li>
>	<li>Ferrari</li>
>	<li>McLaren</li>
>	<li>Williams</li>
>	
></ol>
>
>```
>- Both the `<ol>` and `<li>` tag have **opening** and **closing** tags
>- The `<li>` tag is *indented* inside the `<ol>` tag


### Full Code

```html

<!-- browser will use HTML5 -->
<!DOCTYPE html>

<!--

    html opening tag
    with attribute language

-->
<html lang="en">

<!-- head opening tag -->
<head>

    <!-- controls the encoding -->
    <meta charset="UTF-8">

    <!-- controls the initial layout -->
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <!--

        opening and closing in one line
        because not writing many things

    -->
    <title>Test</title>

<!-- head closing tag -->
</head>

<!-- body opening tag -->
<body>

  

    <!-- this is normal typed text -->
    This is a normal text!

    <!-- there should be not space in between these 2 lines -->
    This is another sentence in the webpage

    <!-- this is a paragraph tag -->
    <p>This text is inside a paragraph and it is the first paragraph in this webpage</p>

    <!-- notice the space between the 2 "paragraph" tag -->
    <p>This is a second paragraph in this webpage</p>

    <!-- heading Tag -->

    <h1>Heading 1</h1>
    <h2>Heading 2</h2>
    <h3>Heading 3</h3>
    <h4>Heading 4</h4>
    <h5>Heading 5</h5>
    <h6>Heading 6</h6>

    <!--

        normal bold text

    -->

    <strong>Bold Text</strong>
    <!--

        "strong" tag inside another tag

     -->
     <p><strong>Bold Text</strong> inside a "paragraph" tag</p>

    <!--

        normal italicized text

    -->
    <em>Italicized Text</em>

    <!--

        "em" tag inside another tag

    -->
    <p><em>Italicized Text</em> inside a "paragraph" tag</p>

    <!-- Lists -->

    <!-- Unordered Lists -->
    <ul>

        <li>Ayrton Senna</li>
        <li>Michael Schumacher</li>
        <li>Lewis Hamilton</li>
        <li>Sebastien Vettel</li>

    </ul>

    <!-- Ordered List -->

    <ol>

        <li>Mercedes</li>
        <li>Ferrari</li>
        <li>McLaren</li>
        <li>Williams</li>

    </ol>

<!-- body closing tag -->
</body>

<!-- html closing tag -->
</html>

```

# Links and Images

In the past, I have placed every element in a single "*index.html*" file. But now, I am realising that we should create another file for every "*new*" element.

>[!tip] Links and Images
>**FOLDER Name:** links-images
>**HTML File Name:** links_images.html

## Anchor Element

The `<a>` element is used to create links. The `<a>` tag has an **opening** and **closing** tag.

- It is defined by *wrapping* the text or another HTML

### A Link that does Nothing

>[!tip] Usage
>```html
>
><!-- make a link that points to nothing -->
><a>click me</a>
>
>```
>- The `<a>` has an **opening** and **closing** tag.


### A Link that points to a Website

#### Link will open in the *same* tab

To make a functional link; we need to use the `<a>` element and **pass** some *attributes* inside the **opening** tag.

>[!tip] Usage
>```html
>
><!-- make a link that points to YouTube -->
><a href="https://www.youtube.com">YouTube</a>
>
>```
>- The `<a>` has an **opening** and **closing** tag.
>	- Attribute `href` is written inside the **opening** tag

#### Link opens in a new / another tab

>[!tip] Usage
>```html
>
><!-- make a link what will open in another tab -->
><a href="https://www.youtube.com" target="_blank">YouTube</a>
>
>```
>- The `<a>` has an **opening** and **closing** tag.
>	- Attribute `href` ( *specifies the destination link* ) is written inside the **opening** tag
>	- Attribute `target` ( *specifies where the link source will be opened* ) is written inside the **opening** tag
>		- If we do not specify `_blank` in the `target` attribute
>		- It will default back to `_self`, which is the same as [[HTML#Link will open in the *same* tab | above]]


>[!warning] NOTE
>To prevent **phishing** ( attacks ) and **tabnabbing** attacks; we are going to add another attribute in the **opening** tag of`<a>`.
>LET ME SHOW IT FIRST
>```html
>
><!--
>	makes a link that will open in another tab
>	creates a security layer
>-->
><a href="https://www.youtube.com" target="_blank" rel="noopener noreferrer">YouTube</a>
>
>```
>You may have noticed that we snuck in the `rel` attribute above. This attribute is used to describe the **relation** between the *current* page and the *linked* document.
>
>The `noopener` value **prevents** the opened link from *gaining access* to the webpage **from** which it was opened. The `noreferrer` value **prevents** the *opened* link from knowing which **webpage** or **resource** has a link (or ‘reference’) to it. It also includes the `noopener` behaviour and thus can be used by itself as well.
>>This is from the [Odin Project](https://www.theodinproject.com/lessons/foundations-links-and-images#opening-links-in-a-new-tab) itself

## Absolute and Relative Links

### Absolute Links

Links that "*links*" other website from our page. Basically what we have been doing above $\uparrow$. It is in the form of `protocol://domain/path`. An example could be `https://www.instagram.com/s.sunhaloo/`

### Relative Links

These are link that are found **within** our website / webpage itself. It assumes that the domain name is the same.

- It only included the file path to the other page

#### STEPS:

##### Making an About Page inside the Same Folder

- Create another HTML file called "*about.html*"
- Copy the following code into the HTML file

```html

<!DOCTYPE html>
<html lang="en">

<head>

    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Links and Images</title>

</head>

<body>

    <!-- make a big heading for about page -->
    <h1>About Page</h1>
  
</body>

</html>

```

- Go back to the `links_images.html` file and paste the code into the file

```html

<!-- link about page -->
<a href="./about.html" target="_blank">About Page</a>

```

##### Make Another Folder

- You can name it whatever you want
- Make another HTML file again whatever name you would like to choose
	- Then paste the code below in the file you just created

```html

<!DOCTYPE html>
<html lang="en">

<head>

    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>About Version 2</title>

</head>

<body>

    <h1>About Version 2</h1>
    <p>This is another about page with a different path</p>
    <p>Check the <code>links_images.html</code> file!</p>

</body>

</html>

```

- Go back to the `links_images.html` file and paste the code into the file

```html

<!-- link about page -->
<a href="./about_V2/about_V2.html" target="_blank">About Page Version 2</a>

```

Here is a sneak peak of what my file directory /structure looks like:

![[tree_link_images_structure.PNG]]

### Full Code

#### Main Webpage

```html

<!DOCTYPE html>
<html lang="en">

<head>

    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Links and Images</title>

</head>

<body>

    <!-- make a Homepage Header -->
    <h1>Homepage</h1>

    <!-- make a link that points to nothing -->
    <a>click me</a>

    <!--

        this has not been covered yet!
        but I know that it does

     -->

    <br>

    <!--

        makes a link that points to YouTube
        opens inside the same tab

     -->
    <a href="https://www.youtube.com">YouTube</a>

     <br>

    <!--

        make a link that points to YouTube
        opens on another tab

     -->
    <a href="https://www.youtube.com" target="_blank">YouTube</a> in another tab

    <br>

     <!--

        make a link that points to YouTube
        opens on another tab
        make it a "secure" link

      -->
    <a href="https://www.youtube.com" target="_blank" rel="noopener noreferrer">YouTube</a> opens in another tab + is "secure"

    <br>

    <!-- link about page -->
    <a href="./about.html" target="_blank">About Page</a>

    <br>

    <!-- link about page version 2 -->
    <a href="./about_V2/about_V2.html" target="_blank">About Page Version 2</a>

</body>

</html>

```

#### About Page ( "*Version 1*" )

```html

<!DOCTYPE html>
<html lang="en">

<head>

    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Links and Images</title>

</head>

<body>

    <!-- make a big heading for about page -->
    <h1>About Page</h1>
    <p>This is the about page</p>

</body>

</html>

```

#### About Page ( *Version 2* )

```html

<!DOCTYPE html>
<html lang="en">

<head>

    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>About Version 2</title>

</head>

<body>

    <h1>About Version 2</h1>
    <p>This is another about page with a different path</p>
    <p>Check the <code>links_images.html</code> file!</p>

</body>

</html>

```

## Images ( Image Element )

I think we all know where this is going; we need to know how to add images or else we are going to die! Not really, but it would be really boring if we only displayed *text* in a website.

To add an image in a webpage / website; we use the `<img>` tag which is a **self-closing** tag.

#### Image from the Internet

>[!tip] Usage
>```html
>
><img src="https://www.theodinproject.com/mstile-310x310.png">
>
>```
>- The `<img>` is a self-closing tag
>- Attribute `src` ( *short for **source*** )
>	- Will specify the source of a resource; such as location of image, audio or other external content
>	- I can embed an image using both **absolute** and **relative** paths
>	- The exact meaning of `src` can change depending on the HTML element it is used with

#### Image from Local Machine

##### STEPS

- Create another folder in the current working directory called "**Images**"
- Choose any image or download one if you do not have one
	- Side Note: [Wallhaven](https://wallhaven.cc) has really cool wallpapers
- Here is screenshot of what my folder structure looks like
![[tree_link_images_folder.PNG]]

>[!tip] Usage
>```html
>
><img src="./images/N Accurate Precise.png">
>
>```
>- It is basically the same thing with the `<img>` tag and the `src` attribute
>- Now in the `src` attribute we pass our *path* of the image file we are going to use!

### Alt Attribute

The `alt` attribute is placed inside the `<img>` tag; I will allow use to describe an image.

- This is used with people with disabilities. Hence, the *Screen Reader* will be able to read the description of the image

>[!tip] Usage
>```html
>
><img src="https://w.wallhaven.cc/full/2y/wallhaven-2y6zl6.png" alt="Japanese Style 8 Bit Artwork">
>
>```
>- It is basically the same thing with the `<img>` tag and the `src` attribute
>- Now we are going to add the `alt` attribute and "*describe*" the image


### Width / Height Attribute

If the image is too **small** or too **big**; we can change the size of the image ( *change the resolution* ). We just need to add `width` and `height` attribute **in** the `<img>` tag.

>[!tip] Usage
>```html
>
><img src="https://w.wallhaven.cc/full/2y/wallhaven-2y6zl6.png" alt="Japanese Style 8 Bit Artwork" width="1280" height="720">
>
>```
>- It is basically the same thing with the `<img>` tag and the `src` and `alt` attributes
>- Now we are going to change the image size with
>	- `width` and `height`


### Full Code

>I have placed the images *tutorial* in the same code as the *links* tutorial

```html

<!DOCTYPE html>
<html lang="en">

<head>

    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Links and Images</title>

</head>

<body>

    <!-- make a Homepage Header -->
    <h1>Homepage</h1>

    <!-- make a link that points to nothing -->
    <a>click me</a>

    <!--

        this has not been covered yet!
        but I know that it does

     -->

    <br>

    <!--

        makes a link that points to YouTube
        opens inside the same tab

     -->
    <a href="https://www.youtube.com">YouTube</a>

     <br>

    <!--

        make a link that points to YouTube
        opens on another tab

     -->
    <a href="https://www.youtube.com" target="_blank">YouTube</a> in another tab

    <br>

     <!--

        make a link that points to YouTube
        opens on another tab
        make it a "secure" link

      -->
    <a href="https://www.youtube.com" target="_blank" rel="noopener noreferrer">YouTube</a> opens in another tab + is "secure"

    <br>

    <!-- link about page -->
    <a href="./about.html" target="_blank">About Page</a>

    <br>

    <!-- link about page version 2 -->
    <a href="./about_V2/about_V2.html" target="_blank">About Page Version 2</a>

    <br>

    <!-- add an external image -->

    <!--

        this image is actually 558x558 px
        the name of the image file is:
        mstile-310x310.png
        this does not mean that the size of the image is 310x310 px

     -->
    <img src="https://www.theodinproject.com/mstile-310x310.png">

     <br>

    <!-- add an image from local machine -->

    <!--

        because the image is 5120 × 3200 px
        i have decided to add the attributes
        "width" and "height"

     -->
    <img src="./images/N Accurate Precise.png" height="768" width="1024">

     <br>

     <!-- adding the "alt" attribute with `<img>` tag -->

     <!--

        this image is also to big for my liking
        i will also be changing the width and the height

      -->
     <img src="https://w.wallhaven.cc/full/2y/wallhaven-2y6zl6.png" alt="Japanese Style 8 Bit Artwork" height="720" width="1280">

     <br>

</body>

</html>

```

# Commit Messages

I think there are important and I have never "*heard*" of them. Yes, yes, there are "*commit message*" in **GitHub**, but to be honest with you I do not really understand it.
Thus, I have made a separate note for it and will be linking it to this page

- [[Commit Message]]