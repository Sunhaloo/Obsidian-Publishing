---
Alias: Maths for CS - Permutations and Combinations
Tag: uni, maths
Module: BCNS1101C
Author: S.Sunhaloo
Date: 2024-06-26
Status: Completed
---

## List of Contents

- [[Permutations and Combinations#Permutations| Permutations]]
	- [[Permutations and Combinations#Factorial $n!$| Factorial]]
	- [[Permutations and Combinations#Permutations with Repetition | Permutations with Repetitions]]
	- [[Permutations and Combinations#Permutations of $n$ Different Objects ( $r$ ) | The Permutations that I know]]
- [[Permutations and Combinations#Combinations| Combinations]]
- [[Permutations and Combinations#Warning | Warning]]

---

### My Links

- [[Permutations and Combinations#Socials| Link to Socials]]

---

# Permutations v/s Combinations

![[Permutations and Combination Difference.png | 650]]

---

# Permutations

>[!tip]
>Permutations are used when the questions have keywords like:
>- *arrangements*
>- *stand in a line / queue*
>Or whenever we are placing things or we are saying that this person **has** to get there or whatever!

## Factorial $n!$

The notation $n!$ means "*$n$ factorial*"

$\Rightarrow$ 3$!$ = 3 $\times$ 2 $\times$ 1 = 6
$\Rightarrow$ 5$!$ = 5 $\times$ 4 $\times$ 3 $\times$ 2 $\times$ 1 = 120
$\Rightarrow$ 9$!$ = 9 $\times$ 8 $\times$ ... $\times$ 3 $\times$ 2 $\times$ 1 = 362880

### Example 1

Find the number of different arrangements for the letter `BAG`.

- Way of writing `BAG`

| Ways |
| ---- |
| BAG |
| BGA |
| GBA |
| GAB |
| AGB |
| ABG |

There are in total, 6 ways to **place** the letters of the word `BAG`

Hence, in short we get

$$\Rightarrow 3! = 6 \leftarrow$$

>Therefore the number of **permutations** of $n$ different objects = $n!$

### Example 2

How can 9 policemen be arranged to stand in a line.

Number of ways ( no restriction ) = 9! = 362880 ways $\leftarrow$

---

## Permutations with Repetition

If in a set of $n$ objects, there are $n_{1}$ of the first kind and $n_{2}$ of the second kind, then the permutation of these object is given by:

$$\frac{n!}{n! \times n!}$$

### Example 1

Find the number of different arrangements of the letters of the word `VIOLIN`

- Solution

>Write it again like uncle does it, so that we can easily identify the repeating words

![[Word - VIOLIN.png]]

>Hence, as you can see we have 2 times the letter `I`!

$$\Rightarrow Number \ of \ ways \ ( no \ restriction ) = \frac{6!}{2!} = 360 \ ways \leftarrow$$

### Example 2

Find the number of different arrangement of the letters of the word `LANGUAGE`

- Solution

>Again just write it like the way that uncle do it!

$$\Rightarrow Number \ of \ ways \ ( no \ restriction ) = \frac{6!}{2! \times 2!} = 10080 \ ways \leftarrow$$

---

## Permutations of $n$ Different Objects ( $r$ )

The number of permutations of $n$ objects taken $r$ at a time is given by:

$$^{n}P_{r}$$

>[!info]
>Where:
>- $n$ = Total Objects
>- $r$ = Number of Objects needed

### Example 1

Eight different books are to be arranged in 5 empty place on a bookshelf. How many different ways can this be done?

$$\Rightarrow Number \ of \ ways \ ( no \ restriction ) = ^{8}P_{5} = 6720 \ ways \leftarrow$$

>[!note]
>We could have also done it like so:
>![[Permutations - Example 1 - Books.jpg | 450]]

### Example 2

Using some or all the digits 1, 2, 3, 4, 5 without repetition, determine how many different numbers can be found and how many are these divisible by 5.

![[Permutations - Example 2 - Digits Part 1.jpg | 450]]
![[Permutations - Example 2 - Digits Part 2.jpg | 450]]

---

## Permutations with Restriction

### Example 1

Find the different arrangements of the letters of the word `BOOK` in which the two letters `O` are consecutive.

![[Permutations - Example 1 - BOOK - O consecutive.jpg | 450]]

### Example 2

Find the different arrangements of the letters of the word `PARLOUR` in which the 2 `R` are not consecutive.

![[Permutations - Example 2 - PARLOUR.jpg| 450]]

### Example 3

Find the different arrangements of the letters of the word `ECONMICS` in which the letters `O` and `C` are not consecutive.

![[Permutations - Example 3 - ECONOMICS.jpg | 450]]

### Example 4

Find the different arrangement of the letters of the word `DESIGN` in which the first letter is `D`.

![[Permutations - Example 4 - DESIGN - D first letter.jpg | 450]]

### Example 5

In how many ways can three men and two women stand in a queue if two women must stand next to each other.

![[Permutations - Example 5 - 3 Men and 2 Women.jpg | 450]]

### Example 6

In how many ways can 4 boys and 3 girls stand in a queue if the 4 boys must stand next to each other.

![[Permutations - Example 6 - 4 Boys and 3 Girls.jpg | 450]]

---

# Combinations

>[!tip]
>This is the little brother to [[Permutations and Combinations#Permutations | permutations]] ( *that's how I look at it... I always feel like Permutations is superior to Combinations... DON'T JUGDE* )
>Yeah, for this one we do not need to care about the *arrangements* and only care about to overall "*combination*" ( *I know I know, you are saying "Go Fuck Youself"* )

>[!tip] Teacher's Explanations
>- It is the **selection** of a specified number of things from a large group
>- From a given set of $n$ objects, if a subset of $r$ objects is to be formed **without** *regard*, to the order, it is called a combination of $n$ objects, taken $r$ at a time:
>$$^{n}C_{r}$$
>>[!info]
>>Where:
>>- $n$ = Total Number of Objects
>>- $r$ = How much of the Objects we need

## Example 1

In how many ways can eleven football players be selected from a team of 15 to play a match?

$\Rightarrow Number \ of \ ways( select \ 11 \ players ) = ^{15}C_{11} = 1365 \ ways \leftarrow$

## Example 2

In how many ways can 3 boys and 5 girls be selected from a group of 5 boys and 10 girls to dance on a stage?

- Solution

$Number \ of \ ways( select \ 3 \ boys ) = ^{5}C_{3}$
$Number \ of \ ways( select \ 5 \ girls ) = ^{10}C_{5}$
$\Rightarrow Number \ of \ ways( select \ 3 \ boys \  and \ 5 \ girls ) = ^{5}C_{3} \times ^{10}C_{5} = 2520 \ ways \leftarrow$

## Example 3

A committee of 4 people is to be chosen from 4 women and 5 men. The committee must contain at <u>least</u> 1 woman. Calculate the number of different committees that can be formed.

>$\Rightarrow$ Minimum 1 Woman

![[Combinations - Example 5 Men and 4 Woman Committee.jpg | 450]]

## Example 4

A committee of 5 People is to be chose from 4 boys and 6 girls. The committee must contain at <u>most</u> 3 girls. Calculate the number of different committees that can be formed?

>$\Rightarrow$ Maximum 3 Girls

![[Combinations - Example 4 Boys and 6 Girls Committee.jpg | 450]]

---

# Warning

One thing; don't mix up Permutations with Combinations. They are separate and different things.
Take a look at the example below ( *this is a really easy example but one can easily make a mistake* ).

## Example: `SUNSET`

Find the number of 3-letter code words that can be formed from the letters of the word `SUNSET`

1. Using **neither** of the `S`
2. Using **both** `S`

### Solution

1. Using **neither** of the `S`

If you are **not** going to be using any `S`; then you can remove it from the list of `SUNSET`. Hence, we only have 4 letters *left*. Therefore we get the answer of:

$Number \ of \ way ( neither \ 'S' \ present ) = ^{4}P_{3} = 24 \ ways \leftarrow$

>This one was simple, really simple in fact.

2. Using **both** `S`

Now, this is where my friend made a big confusion... We are *doing* **Permutations** and **not** *Combinations*. Hence, we cannot have multiple positions.

>Let me show you the **correct** way first then I will talk about the mistake.

$Number \ of \ way ( both \ 'S' \ present ) = ^{4}P_{1} = 4 \ ways \leftarrow Good \ Answer$

This is because we have **placed** 1 `S` at the *first* position and another `S` at the *second* position.

But then she told me that we could also have these:

| Letter 1 | Letter 2 | Letter 3 |
| -------- | -------- | -------- |
| S | _ | S |
| S | S | _ |
| _ | S | S |

>[!bug] This is <u><em>NOT</em></u> Good!!!

This is because, again, we are **not** doing any *Combinations*!
Then the teacher came and finally I remembered why we do it in this way;

>[!tip] Conditions First!!!
>We need to perform the condition ( *here is was that <u>both</u> `S` should be present* ) and we care about the rest later!!!

>That's it and that's all that I have to say; Peace out Motherfucker!!!

---

# Socials

- **Instagram**:https://www.instagram.com/s.sunhaloo/
- **YouTube**:https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg
- **GitHub**:https://www.github.com/Sunhaloo

---

S.Sunhaloo
Thank You!