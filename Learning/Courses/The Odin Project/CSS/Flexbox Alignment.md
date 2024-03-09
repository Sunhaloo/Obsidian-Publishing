---
Alias: CSS Flexbox Alignment
Tag: CSS, TheOdinProject, basics
Author: S.Sunhaloo
Date: 2023-12-22
Status: Completed
---

## List of Contents

- [[Flexbox Alignment#Introduction | Introduction]]
- [[Flexbox Alignment#Justify Contents ( Main Axis / $x axis$ ) | Justify Contents]]
- [[Flexbox Alignment#Align Items ( Cross Axis / $y axis$ ) | Align Items]]
- [[Flexbox Alignment#Gap | Gap]]

# Introduction

What we have done with flexbox has used to rule `flex: 1` $\Rightarrow$ `flex-grow: 1` on all flex **items**

- Which makes them *grow* or *shrink* to fill all the available space

But sometimes ( *most of the time* ), this is **not** the desired effect

- Flex is very useful for arranging **items** that have a *specific size*

[Fourth Interactive Example](https://www.theodinproject.com/lessons/foundations-alignment#alignment) $\downarrow$ ( *we are going to be using these notes for the $4^{th}$ interactive example* )
 
## Justify Contents ( Main Axis / $x \ axis$ )

The rule `justify-content` aligns **items** across the **main** axis.

From what I just asked ChatGPT; I can see that there are many values that `justify-content` can take:

Here are some ( *I think this is all of them* ) of those values:

- flex-start
- flex-end
- center
- space-between
- space-around
- space-evenly

## Align Items ( Cross Axis / $y \ axis$ )

The rule `align-items` aligns **items** along the **cross** axis.

I again asked ChatGPT; Here are some of the values that `align-items` can take:

- flex-start
- flex-end
- center
- baseline
- stretch

>[!note]
>There is 1 thing we need to know about these 2 rules above $\uparrow$.
>They can ( *will* ) change the direction of their axes if we use:
>- `flex-direction: column`
>	- $\Rightarrow$ `justify-content` will align items *vertically* ( $y \ axis$ )
>	- $\Rightarrow$ `align-items` will align items *horizontally* ( $x \ axis$ )

## Gap

This will simply add a specified **space** between the flex **items** on a flex **container**,

- Similar to adding a *margin* to the items themselves

Nevertheless, there are not many resources because it is a pretty new thing. But is works *wonderfully* in all modern browsers; thus safe to use and very handy.

### More Help

1. Beautiful [Interactive Guide to Flexbox](https://www.joshwcomeau.com/css/interactive-guide-to-flexbox/) ( *just check the this website and it is very well done both in terms of the educational content and also the asthetics of it* )
2. [MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout/Typical_Use_Cases_of_Flexbox)
3. [Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)