---
Alias: Web Development - HTML Tables - Week 8
Tag: HTML, uni, basics
Module: WAT1119C
Author: S.Sunhaloo
Type: Tables
Date: 2024-06-27
Status: In-Progress
---

## List of Contents

- [[HTML - Tables#Creating Tables | Creating Tables]]
	- [[HTML - Tables#Create the following Table | Create the following Table]]
	- [[HTML - Tables#Customisation of Tables | Customisation of Table]]
- [[HTML - Tables#Row-Span and Col-Span | Rowspan and Colspan]]
	- [[HTML - Tables#`rowspan` | Rowspan]]
	- [[HTML - Tables#`colspan` | Colspan]]

---

### My Links

- [[HTML - Tables#Socials | Link to Socials]]

---

# Creating Tables

To simple table in HTML, we are going to be mainly using these tree tags:

1. `table` $\Rightarrow$ Creation of actual table
2. `th` $\Rightarrow$ Header for Table ( *similar to markdown's table header* )
3. `tr` $\Rightarrow$ Table row... a row in a table
4. `td` $\Rightarrow$ Table data, where we are going to actually store the data in the **cell**

## Create the following Table

| Make | Model | Year |
| ---- | ----- | ---- |
| Mazda | RX-7 FD3S | 1994 |
| Audi | RS6 Avant | 2024 |
| Porsche | GT3 RS 911 | 2024 |

>*Below $\downarrow$ lies the HTML Code*

```html

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tables</title>
</head>
<body>

    <!--
        border = "0" ==> no border; some might say that its not going to be a table
        hence, added a border with `border = "1"`
        align the table so that its in the center
        make the table take 50% of the screen landscape-wise
    -->
    <table border="1" align="center" width="50%">
        <!--
            make a row only for table header
            using the `tr` tag
        -->
        <tr>
            <!--
                make table header with `th` tag
                align all the text to center
            -->
            <th align="center">Make</th>
            <th align="center">Model</th>
            <th align="center">Year</th>
        </tr>
        <!-- make another row for first ( row ) data -->
         <tr>
            <!--
                use the tag `td` to input data into a cell
                align all text in cell in the center
            -->
             <td align="center">Mazda</td>
             <td align="center">RX-7 FD3S</td>
             <td align="center">1994</td>
         </tr>
        <!-- make another row for second ( row ) data -->
         <tr>
            <!--
                use the tag `td` to input data into a cell
                align all text in cell in the center
            -->
             <td align="center">Audi</td>
             <td align="center">RS6 Avant</td>
             <td align="center">2024</td>
         </tr>
        <!-- make another row for third ( row ) data -->
         <tr>
            <!--
                use the tag `td` to input data into a cell
                align all text in cell in the center
            -->
             <td align="center">Porsche</td>
             <td align="center">GT3 RS</td>
             <td align="center">2024</td>
         </tr>
    </table>
    
</body>
</html>

```

>[!info]- Output
>![[HTML Simple Table.png]]

## Customisation of Tables

# Row-Span and Col-Span

## `rowspan`

## `colspan`

---

# Socials

- **Instagram**:https://www.instagram.com/s.sunhaloo/
- **YouTube**:https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg
- **GitHub**:https://www.github.com/Sunhaloo

---

S.Sunhaloo
Thank You!