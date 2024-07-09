---
Alias: Maths for CS - Logic Proposition
Tag: uni, maths 
Module: BCNS1101C
Author: S.Sunhaloo
Date: 2024-05-14
Status: Completed
---

## List of Contents

- [[Logic Proposition ( Logic Gates - Truth Tables )#Propositional Logic| Propositional Logic]]
	- [[Logic Proposition ( Logic Gates - Truth Tables )#Truth Table| Truth Table]]
	- [[Logic Proposition ( Logic Gates - Truth Tables )#Logical Connective| Logical Connective]] 
	- [[Logic Proposition ( Logic Gates - Truth Tables )#Translation ( English / Logical Proposition )| Translating English to Logical Proposition]]

---

### My Links

- [[Logic Proposition ( Logic Gates - Truth Tables )#Socials| Link to Social]]

---

>[!note]
>Refer to `C:/Obsidian/University Books/Maths for Science` for books on this topic / maths.
>"Discrete Mathematics and Its Applications" by Kenneth H. Rosen
>- Companion Website [here](https://highered.mheducation.com/sites/125967651x/information_center_view0/)
>- Interactive Demonstrations [here](https://highered.mheducation.com/sites/125967651x/student_view0/interactive_demonstrations.html)
>>I really recommend reading this book; has a lot to offer.

>[!warning]-
>I have my ways of doing logic gates ( *logic proposition* ). For Example:
>	The teacher will start will both values set to `True` or `1`
>	While I start will both values set to `False` or `0`
>I will try to also insert the teacher's / book's way; but I think my version is simpler / easier to understand.
>>This is my fucking notes; STFU!!!

---

# Propositional Logic

>[!tip]- Definition
>A proposition is a **statement** that is **either** *true* or *false* but <span style="color: red;">not</span> both.

Propositional Logic is concerned with statements to which the *Truth Values* `True` / `1` and `False` / `0` can be assigned.

>In short the *Truth Value* check whether our "*statements*" are actually `True` or `False`

>[!tip] Propositional Examples:
>"*Dogs are mammals*" $\Rightarrow$ *Truth Values* = `True` $\rightarrow$ `1`
>"$12 + 3 = 4 - 2$" $\Rightarrow$ *Truth Values* = `False` $\rightarrow$ `0`

>[!tip] **NOT** a Propositional Example:
>"*What time is it?*" $\Rightarrow$ This is <span style="color: red;">NOT</span> a Proposition;
>"*Read this carefully*" $\Rightarrow$ This is <span style="color: red;">NOT</span> a Proposition;
>---
>"$x \lt 3$" $\Rightarrow$ This is <span style="color: red;">NOT</span> a Proposition;
>This is because we **cannot** tell if $x$ is actually less than 3
>But ( *big butt* ), if you give $x$ a specific value than it can become a Propositional *statement*.
>$x = 2$; $x < 3 \Rightarrow$ This is `True`!

>[!info]
>The normal letter used for propositions are `p`, `q`, `r`, `s`.
>>I have been using `A`, `B`, `C` and `X` for all my life... 🤓

## Truth Table

>[!tip]- Definition
>It displays the relationship between *truth values* of propositions.

### How to know what values to use?

Remember we had something like this in HSC:

| A | B | C |
| - | - | - |
| 0 | 0 | 0 |
| 0 | 0 | 1 |
| 0 | 1 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 0 |
| 1 | 0 | 1 |
| 1 | 1 | 0 |
| 1 | 1 | 1 |

I used to learn it by heart; but there is a logical approach to it ( *logical hehe* ).

Take for example we have **2** variables `p` and `q`.

This will have 4 possibilities meaning its *truth table* will look something like this:

| p | q |
| - | - |
| 0 | 0 |
| 0 | 1 |
| 1 | 0 |
| 1 | 1 |

As computers process information in **binary** $\Rightarrow$ only 1 and 0. This means that there is only 2 possible "*states*" that is available.

Hence, if you have 2 variables; it means that you get $2^{2}$ possible combinations / possibilities.

#### But how do you know when to alternate the 1s and 0s?

Again, take the example of **2** variables; we have 4 possibilities. You can use the "*template*" below to get an idea.

| $2^{2}$ | $2^{1}$ |
| - | - |
| 0 | 0 |
| 0 | 1 |
| 1 | 0 |
| 1 | 1 |

At $2^{1} \Rightarrow$ You alternate every 1 value and at $2^{2} \Rightarrow$ You alternate every 2 values ( *refer to table above $\uparrow$* )

>[!tip]- What happens for $2^{3}$?
>Because computers only understand base 2 numbering system ( *i.e 1 or 0* ). We <span style="color: red;">cannot</span> have:
>
>| p |
>| - |
>| 0 |
>| 0 |
>| 0 |
>| 0 |
>| 1 |
>| 1 |
>| 1 |
>Hence, we need to alternate every **4** values... check the truth table above $\uparrow$ ( *check the variable `A`* )

## Logical Connective

>Also known as *logical operator, sentential connective or sentential operator* 
>- Part of [Logical Constant](https://en.wikipedia.org/wiki/Logical_constant)

It is a logic constant that is used to **connect** logical formulas

Here are some of the connectives that we use:

1. Negation Operator ( $\neg$ )
2. AND Operator ( $\land$ )
3. OR Operator ( $\vee$ )
5. Exclusive OR Operator [ XOR ] ( $\oplus$ )
6. Implication [ *if then* ] ( $\rightarrow$ or $\Rightarrow$ )
7. Biconditional [ *if and only if ( iff )* ] ( $\leftrightarrow$ or $\Leftrightarrow$ )

### Negation Operator ( $\neg$ )

This is basically the `NOT` gate in Logic Gates.

Example: Find '$\neg$ p' Give 'p'

| p | $\neg$ p |
| - | ------ |
| F | T |
| T | F |

### AND Operator ( $\land$ )

Again, this is our normal trusty `AND` gate.

In this case we have 2 variables; this means that we get a statement like so: 'p $\land$ q'

| p | q | p $\land$ q |
| - | - | ---------- |
| F | F | F |
| F | T | F |
| T | F | F |
| T | T | T |

>[!info]-
>This would be my version of the above $\uparrow$ *truth table*
>
>| p | q | p $\land$ q |
>| - | - | ---------- |
>| 0 | 0 | 0 |
>| 0 | 1 | 0 |
>| 1 | 0 | 0 |
>| 1 | 1 | 1 |
>But because in of the book; I am following the `T` and `F` thing; nevertheless I am not starting with `T` and `T`

### OR Operator ( $\vee$ )

What should I say here... that it is the same as in HSC? I am going to think about it and then tell you... right now I am going to get some milk... ( *I hope you know this meme* )

Similarly, here we are going to have the statement 'p $\vee$ q'

| p | q | p $\vee$ q |
| - | - | ---------- |
| F | F | F |
| F | T | T |
| T | F | T |
| T | T | T |

### Exclusive OR [ XOR ] Operator ( $\oplus$ )

Do I need to repeat again... go fuck yourself.

Here we are going to get the statement 'p $\oplus$ q'

| p | q | p $\oplus$ q |
| - | - | ---------- |
| F | F | F |
| F | T | T |
| T | F | T |
| T | T | F |

### Implication

>This means `if ... then ...`

Ahh, this is the only gate right now / for the moment that has **not** been done in HSC.

For this implication to be `False` 'p $\rightarrow$ q'; the **first** value should be <span style="color: green;">True</span> **and** the **second** value should be <span style="color: green;">False</span>

We need to be very **careful** when we are working with implication. Let's say that we have the statement 'p $\rightarrow$ q'; is truth table will look something like this $\downarrow$:

In this case we are saying that <span style="color: green;">'p' *implies* 'q'</span>

| p | q | p $\rightarrow$ q |
| - | - | ---------- |
| F | F | T |
| F | T | T |
| <span style="color: green;">T</span> | <span style="color: red;">F</span> | F |
| T | T | T |

But now what happens if we have 'p $\leftarrow$ q' or 'q $\rightarrow$ p'

Hence, in this case we are saying that <span style="color: red;">'p' *implies* 'q'</span>

| p | q | q $\rightarrow$ p |
| - | - | ---------- |
| F | F | T |
| <span style="color: red;">F</span> |<span style="color: green;">T</span>  | F |
| T | F | T |
| T | T | T |

Or you could have done it like this $\downarrow$:

| q | p | q $\rightarrow$ p |
| - | - | ---------- |
| F | F | T |
| F | T | T |
| <span style="color: green;">T</span> | <span style="color: red;">F</span> | F |
| T | T | T |

### Biconditional / Equality Operator ( $\leftrightarrow$ or $\Leftrightarrow$ )

>This means `if and only if`

Again something that we have not done in HSC. Very nice!

For this equality to be `True`, 'p $\leftrightarrow$ q': **both** values has to be *either* <span style="color: green;">True</span> **or** <span style="color: red;">False</span>

This is similar to XOR; but not really ( *same same, but different* )

Here we also have 2 variables; hence, we get the statement 'p $\leftrightarrow$ q'

| p | q | p $\leftrightarrow$ q |
| - | - | ---------- |
| F | F | T |
| F | T | F |
| T | F | F |
| T | T | T |

---

## Tautology

### What is a Tautology?

>[!tip]- Oxford Definition
>`LOGIC` $\rightarrow$ Statement that is true by necessity or by virtue of its logical form.

A compound proposition that is **always** `True`.

The **final** answer of a tautology is going to be always `True`; the *final* column should be **all** `True`.

- Example 1:

| Final Answer |
| ------------ |
| T |
| T |
| T |
| T |

- Example 2:

| Final Answer |
| ------------ |
| T |
| T |
| T |
| T |
| T |
| T |
| T |
| T |

## Contradiction

### What is a Contradiction?

>[!tip]- Oxford Definition
>Combination of statements, ideas, or features which are opposed to one another.

A compound proposition that is **always** `False`.

- Example 1:

| Final Answer |
| ------------ |
| F |
| F |
| F |
| F |

- Example 2:

| Final Answer |
| ------------ |
| F |
| F |
| F |
| F |
| F |
| F |
| F |
| F |

## Contingent

>[!tip]- Oxford Definition
>1. Subject to chance
>2. Occurring / existing only if ( certain circumstances ) are the case; dependent on.

A proposition that is neither a tautology nor a contradiction is called a **contingency**.

>Meaning just some regular answers like `True, True, False, True` $\leftarrow$ I just did *implication* proposition WTF.

---

# Translation ( English / Logical Proposition )

## Translating English to Logical Proposition

- Example 1:

"*You cannot ride the roller coaster if you under 4 feet tall unless you are older than 16 years old*"

>[!tip] Tips
>1. Always read the question 1 more time
>2. Check of logical propositions like:
>	- `OR`, `AND`, `IF THEN`, `IF AND ONLY IF`
>3. I would suggest underlining them

Hence, after following these tips we get:

"*You <ins>cannot</ins> ride the roller coaster <ins>if</ins> you under 4 feet tall <ins>unless</ins> you are older <ins>than</ins> 16 years old*"

>[!tip] Solution
>Let `q` = "*You **can** ride the roller coaster*", `r` = "*You are under 4 feet tall*", `s` = "*You are older than 16 years old*".
>
>This is translated to:
>'(r $\land \ \neg$ s ) $\rightarrow \ \neg$ q'
>
>Because `q` = "*You **can** ride the roller coaster*" and we need "*cannot*"; hence we need to get '$\neg$ q' at some point.
>
>For you to **<span style="color: red;">NOT</span>** ride the rollercoaster; you **need** to be under 4 feet tall and also **younger** than 16 years old.
>Hence, for this part we get:
>'(r $\land \ \neg$ s )'

- Example 2:

"*You can access the Internet from campus only if you are a computer science major or your are not a freshman*"

After following the tips, we get $\downarrow$:

"*You can access the Internet from campus only <ins>if</ins> you are a computer science major <ins>or</ins> your are <ins>not</ins> a freshman*"

>[!tip] Solution
>Let `a` = "*You can access the Internet from campus*", `b` = "*You are a computer science major*", `c` = "*You are a freshman*".
>
>This is translated to:
>'a $\rightarrow$ ( b $\vee \ \neg$ f)'
>
>For you to <span style="color: green;">access</span> the internet; you **need** to be a computer science major **or** <ins>*not</ins>* a freshman.

---

# Socials

- **Instagram**: https://www.instagram.com/s.sunhaloo/
- **YouTube**: https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg
- **GitHub**: https://www.github.com/Sunhaloo

---

S.Sunhaloo
Thank You!