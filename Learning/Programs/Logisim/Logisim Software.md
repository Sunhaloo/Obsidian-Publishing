---
Alias: Computer Architecture and Organisation ( Logisim Software ) - Week 3
Tag: uni, theory
Module: ICDT 1206Y
Author: S.Sunhaloo
Date: 2024-08-07
Status: In-Progress
---

>[!note]
>This file / note / documentation was created on my laptop.
>Hence, the screenshots will not be of the same quality in terms of cropping the images.
>Because I am using a trackpad.
>>I hate trackpads.

## List of Contents

- [[Logisim Software#Download and Installation | Download and Installation]]
- [[Logisim Software#First Look | First Look]]
- [[Logisim Software#Drawing Gates | Drawing Gates]]
	- [[Logisim Software#Adding the Gates | Adding Gates]]
	- [[Logisim Software#Adding Wires | Adding Wires]]
	- [[Logisim Software#Adding Inputs | Adding Inputs]]
	- [[Logisim Software#Adding Text | Adding Text]]
- [[Logisim Software#Testing | Testing]]
	- [[Logisim Software#Testing the Half-Adder Circuit]]

---

### My Links

- [[Logisim Software#Socials | Link to Socials]]

---

# Download and Installation

Logisim is a software that was is pretty old; 2011 old to be exact.

Here is the link to download Logisim: https://sourceforge.net/projects/circuit/

>[!note]
>When I tried to install it on **Windows** I got the error saying that it needs Java Runtime Environment version `1.5.0`.
>I was confused because I have the latest version of Java installed using the `winget` command.
>But no worries; once you click on the <button>Ok</button>, it will redirect you to Java 8 download website.
>Hence, download and install Java 8 and finally run the software.

## Linux Users

### Debian Based Distributions

```console
sudo apt-get install logisim
```

### Arch Based Distributions

>[!bug] Check Later!!!

---

# First Look

When you are going to open the application, you will be greeted with $\downarrow$:

![[Logisim Screen.png | 1000]]

>I am running this on Linux ( Linux Mint - *on my laptop* )
>I used Arch ( BTW ) on Desktop!

---

# Drawing Gates

I am going to try to draw the *[[Logic Gates#Simplified Version of Half-Adder | Simplified Version of Half-Adder]]*.
It looks something like this:

![[Half-Adder Simplified Diagram.png]]

## Opening the Gates Folder

Double-click on the '*Gates*' folder you will see a bunch of gates that we can use.

>*Obviously, what are we going to do... Sit there and watch like a moron*

![[Logisim - Gates Folder.png]]

### Using the Gates

Click on the gate that you want and then; move your mouse cursor to the **Canvas**.
You will be able to see what gate that you have chosen.

Whenever you are ready, left-click and hence, your selected gate will appear.

### Drawing Simplified Half-Adder Circuit

#### Adding the Gates

Here are the "*ingredients*" $\downarrow$:

- 2 AND ( $\land$ ) Gates
- 1 OR ( $\vee$ ) Gate
- 1 NOT ( $\neg$ ) Gate

>Go ahead and place these gates on the Canvas!

>[!info]
>You **cannot** use `<Ctrl>` + Scroll Wheel to zoom in or out.
>You need to actually press the zoom in / out button found in the **bottom** left corner of the program
>![[Logisim - Zoom In or Out.png]]

#### Adding Wires

You can easily add wires by dragging from the **points** that are *in* the diagrams

>[!note]
>You can join your gates so that you don't need to add any wires...
>This is nice when you are just experimenting, but <span style="color: red;">it's fucking ugly</span>!!!

>I am not showing you how to add the wires, because a toddler ( *or a monkey if you wish* ) can do that!

#### Adding Inputs

If you go back above $\uparrow$ or in any logic gate diagram, there will always be 1 or more **Inputs** and 1 *Output*

>[!note]
>There is an 'Input/Output' folder, but we are **not** going to be using them.

Instead we are going to use these $\downarrow$:

>See for yourself!

![[Logisim - Input and Output Toolbar.png]]

In this case we are going to need:

- 2 Inputs
- 1 Output

The diagram should look something like this $\downarrow$:

![[Logisim - Half Adder ( After Wiring and Input ).png | 750]]

#### Adding Text

Adding text is a great way to document and show someone what you have created.

In the toolbar you are going to find $A$.

>Here is what it looks like

![[Logisim - Toolbar ( Text Tool ).png]]

>I have added the text, mine currently looks like this $\downarrow$

![[Logisim - Half Adder ( After Adding Text ).png | 750]]

>[!tip]-
>As you can see here, I have used different font sizes and font family. The **default** *font-size* is `12` and *font-family* is `SansSerif Plain`.
>But we can change these here $\downarrow$:
>
>![[Logisim - Edit Font Family and Size.png]]
>
>>This is know as the *Attribute Table*

# Testing

Now we have drawn our [[Logic Gates#Half-Adder | Half-Adder]] Circuit, we are going to test them but *turning* on the **Inputs**.

To turn on / off our circuit we need to *poke* ( *that is what is in the lecturer's [[Computer Architecture - Organisation - Logisim Software.pdf | PDF]] File* ).
This is done with the "*hand*" tool found in the [[Logisim - Toolbar ( Text Tool ).png | toolbar]].

## Half-Adder Truth Table

The table below will show you the truth table for a half-adder

| X | Y | S | C |
| - | - | - | - |
| 0 | 0 | 0 | 0 |
| 0 | 1 | 1 | 0 |
| 1 | 0 | 1 | 0 |
| 1 | 1 | 0 | 1 |

>Where 'S' $\Rightarrow$ *Sum* and 'C' $\Rightarrow$ *Carry*

### Testing the Half-Adder Circuit

The table $\downarrow$ will show the result that I got when *poking* the inputs.

| X | Y | S | C |
| - | - | - | - |
| 0 | 0 | 0 | 0 |
| 0 | 1 | 1 | 0 |
| 1 | 0 | 1 | 0 |
| 1 | 1 | 0 | 1 |

As you can see we have the **same** outputs!

# Creating Bundles



---

# Socials

- **Instagram**: https://www.instagram.com/s.sunhaloo
- **YouTube**: https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg
- **GitHub**: https://www.github.com/Sunhaloo

---

S.Sunhaloo
Thank You!