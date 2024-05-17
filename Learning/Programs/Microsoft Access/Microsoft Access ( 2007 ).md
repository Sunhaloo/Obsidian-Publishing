---
Alias: MS Access Database
Tag: uni, db
Author: S.Sunhaloo
Date: 2024-05-08
Status: In-Progress
---

<p align="center">Introduction to Databases<br>Lab 2<br>BCNS1103C / DBT1103C<br>SUNHALOO Shehzaad</p>

<br>

<p align="center">University of Technology, Mauritius</p>

## List of Contents

- [[Microsoft Access ( 2007 )#Create a New Database File | Create a New Database File]]
	- [[Microsoft Access ( 2007 )#Switching Views | Switching Views]]
	- [[Microsoft Access ( 2007 )#Adding Data into Table | Adding Data into Table]]
- [[Microsoft Access ( 2007 )#Primary Key | Primary Key]]
- [[Microsoft Access ( 2007 )#Default Values, Field Validation Rules & Validation Text | Default Values, Field Validation Rules & Validation Text]]
- [[Microsoft Access ( 2007 )#Relationships | Relationships]]
	- [[Microsoft Access ( 2007 )#Delete Relationships | Delete Relationships]]
	- [[Microsoft Access ( 2007 )#Delete Tables | Delete Tables]]
- [[Microsoft Access ( 2007 )#Referential Integrity | Referential Integrity]]
- [[Microsoft Access ( 2007 )#Forms | Forms]]
	- [[Microsoft Access ( 2007 )#Query and Dynaset? | Query and Dynaset]]
	- [[Microsoft Access ( 2007 )#Form Controls | Form Controls]]
		- [[Microsoft Access ( 2007 )#Create Form Wizard | Form Wizard]]
		- [[Microsoft Access ( 2007 )#Adding Data using Form | Adding Data using Form]]
		- [[Microsoft Access ( 2007 )#Change the look of Form | Change the look of Form]]
			- [[Microsoft Access ( 2007 )#Form Property Sheet | Form Property Sheet]]
		- [[Microsoft Access ( 2007 )#Customer Entry Form | Customer Entry Form]]
		- [[Microsoft Access ( 2007 )#Order Entry Form | Order Entry Form]]

---

## My Links

- [[Microsoft Access ( 2007 )#Socials | Link to Socials]]

---

>[!warning]
>This is part of an assignment given by our lecturer. Hence, this file can be related to [[University Data View#Database Folder | Database Design]] $\rightarrow$ Spring Double Glazing Company.
>Because I would have never learned MS Access and would have gone straight to **mySQL** or **Oracle**.

>[!note]-
>I am using Microsoft Access 2007.
>But should be the same for everything

>[!info]
>Access is a **[[Overview of Database Management System 1#Relational Model| Relational]] Database Management System ( RDBMS or RDMS )**.
>This means that; all the data is organised into **two-dimensional** ( *2D-Relation* ) tables.
>---
>Rows $\Rightarrow$ Data Records / Records
>Columns $\Rightarrow$ Data Fields / Fields

# Create a New Database File

I think you know how to do that without any tutorial or anything, right? ( *I fucking hope so* ).

>The file extension for Micro-soft ( *get it... micro soft* ) Access is: `.accdb`

After clicking the <button>Create</button> button. You will be dropped straight into a table ( *Table 1* ) with the **Datasheet View**.

There are 2 types of views:

1. Datasheet View $\Rightarrow$ Looks like an Excel Sheet!
	- Normally used to add data into the table
2. Design View
	- Normally used to create the table ( *fields, data types of fields, etc* )

# Switching Views

To switch to the "**Design View**"; just **right**-click on the table in the *Navigation Pane* and select *Design View*.

This will prompt you to save the **table** ( *not the whole database, but that current table* ). Name that table `tblCustomer`

>[!tip]- Naming Conventions
>Similar to programming, make sure that you "*variables*" names are **meaningful**
>In addition, if you need to write for example `Spare Parts` just write it like you would in programming: `spare_parts`.
>For Example
>- If you are creating a Table
>	- use the prefix `tbl` and then put the actual name of the table
>- For Queries
>	- Use the prefix `qry`
>- For Forms
>	- Use the prefix `frm`
>- For Reports
>	- Use the prefix `rpt`

>Please Check the "Naming Conventions" above $\uparrow$.

# Adding Data into Table

Now we can easily start adding data to the table.

Add these following data:

<p align="center"><strong>Table:</strong> tblCustomer</p>

| Fields | Data Type | Field Size |
| ------ | --------- | ---------- |
| Customer_ID | Autonumber | - |
| Surname | Text | 30 |
| Name | Text | 30 |
| FirstName | Text | 30 |
| Address 1 | Text | 30 |
| Address 2 | Text | 30 |
| Address 3 | Text | 30 |
| Address 4 | Text | 30 |
| Phone | Text | 15 |
| PostCode | Text | 8 |

>[!note]
>An **AutoNumber** field automatically enters a unique number as each record.

It should look something like this:

![[MS Access Design View.png | 700]]

## Primary Key

### What is a Primary Key

We know that it is a unique field identifier ( *given to us in HSC* ).

A Primary Key **must** be:

- **Not Null**: Primary Key should always have a value
- **Stable**: Should / Does NOT change once entered
- **Unique**: Value should uniquely identify the record

>[!note]
>When drawing a database by hand; the **primary key** should always be **<ins style="color: red;">underlined</ins>**

### Set Primary Key in MS Access

We just need to simple **right**-click on the *field* that want to make primary key and then click on `Primary Key`.

>A little golden key will appear next to the "*selected*" field!

---

>[!warning]
>As I said in the beginning; this Markdown Document is part of my Lecture assignment; hence I will be using this "*task*" given to us as an example.

## Create More Tables

<p align="center"><strong>Table:</strong> tblStock</p>

| Fields | Data Type | Field Size |
| ------ | --------- | ---------- |
| Stock_ID | Autonumber | - |
| Description | Text | 50 |
| Selling Price | Currency | - |

> Set `Stock_ID` as Primary Key

<p align="center"><strong>Table:</strong> tblOrder</p>

| Fields | Data Type | Field Size |
| ------ | --------- | ---------- |
| Order_ID | Autonumber | - |
| Customer_ID | Number | Long Integer |
| Order Date | Date/Time | - |
| PaymentMethod | Text | 1 |

> Set `Order_ID` as Primary Key

We can see that in this case; `Customer_ID` can be called a **Foreign Key**

<p align="center"><strong>Table:</strong> tblOrderLine</p>

| Fields | Data Type | Field Size |
| ------ | --------- | ---------- |
| OrderLine_ID | Autonumber | - |
| Order_ID | Number | Long Integer |
| Stock_ID | Number | Long Integer |
| Quantity | Number | Byte |

---

# Default Values, Field Validation Rules & Validation Text

>[!tip] Data should be **validated** before it get *stored*!

## Default Values

This is like when you are entering some information; it will automatically enter a *default value*.

For example you are booking an airline ticket and they have a section called "*Today's Date*" to fill. Instead of you needing to fill that section, it will **automatically** input that data for you.

## Validation in MS Access

>Remember Validation and Verification in HSC
>This is him now!

Validation can be achieved through:

- Table Design
- Form Design
- Coding
- Lookup Tables

Validation should happen at the **first** level $\Rightarrow$ In MS Access this means that it is better to include the validation as part of the **table** design rather than relying on *entry validation* at **form** level.

Below $\downarrow$ you can take a look what it looks like:

![[MS Access Default, Validation Rule and Text.png | 700]]

---

# Relationships

In HSC, we learnt about the ERD ( *Entity Relationship Diagram* ) Diagram; where we had to draw *fields* connecting to other *fields* and see how they where **related**.

## Types of Relationships ( *learned in HSC* )

1. One to One ( 1:1 )
2. Many to One ( m:1 ) OR One to Many ( 1:m )
3. Many to Many ( m:n )

>Now we are going to learn how to actually do these things in Linux... WTF am I saying... In MS Access.
>I like Linux; I am sorry, I <span style="color: pink;">LOVE</span> Linux! But here I am on Windows using MS Access... WWWWHHHHHYYYYY!

## Setup Relationships in MS Access

In MS Access, *table* **relationships** are setup in the "**Relationships Window**". In the 2007 version of Access. You just need to find `Database Tools` in the Ribbon Menu and you are going to see a button named <button>Relationships</button>.

### Steps

>[Here](https://www.youtube.com/watch?v=DlGEECPru3E) is a good video on how to setup Relationships

1. Close all / any of the **Tables** you have opened
	- We cannot implement relationships while **Tables** are opened!
2. Switch to "*Database Window*" by pressing the `F11` Key
3. Find the <button>Relationships</button> button ( in the `Database Tools` Tab )
4. "*Show Tables*" Menu $\Rightarrow$ Add the tables you want to relate
	- If you did **not** setup any relationships, the "*Show Tables*" menu will automatically pop up.
	- If the "*Show Tables*" menu does not pop up; you can easily find the button <button>Show Table</button> in the Ribbon Menu.
5. Drag the **field** that you to to relate from one table to related *field* in the other table.
	>[!note]- In this Case
	>We have:
	>- Each customer may place many orders
	>- Each order may have many order lines
	>- Each order line is for a particular item of stock
6. In most cases; you will only drag the **primary key** of one table to another's table **foreign key**.
	```mermaid
	graph LR
	A[Primary Key] --->| to | B[Foreign Key]
	```
7. Then after connecting it; a new menu will appear.
	![[Edit Relationships Menu.png | 340]]
	- Please $\checkmark$ on
		1. Choose Enforce Referential Integrity
		2. Choose both Cascade *option*
	- Click on the big ass <button>Create</button> button
8. Repeat Steps `5` to `7`

>What is a Foreign Key?
>In HSC, we learnt that a **Foreign Key** is a key that is a *Primary Key* in another Table.

## Delete Relationships

Just simply click on the connecting arrow and press `Del` on the keyboard!

## Delete Tables

Sometimes you might accidentally add the **same** Table twice.

- If the table does not have any relationships; then just **right**-click on the table, an option called `Hide Table` will appear
- If the table **has** a / many relationships;
	- We need to first, delete the relationships and then
	- Proceed to `Hide Table`

---

# Referential Integrity

## What is Referential Integrity?

>Source: https://www.ibm.com/docs/en/informix-servers/14.10?topic=integrity-referential

It refers to the relationships between **Tables**. As you know, every table in a *database* has a **primary key**. If you are going to link ( *add relationships* ) with / to other tables in that database. The primary key in one table can / must become a **foreign key** in another.

>This was also explained above $\uparrow$

When you **delete** a row that contains a *primary key* or **update** it with a different primary key. You essentially *destroy* the **meaning** of any rows that contain that value as a **foreign key**. Referential Integrity is the logical dependency of a foreign key on a primary key.

>[!tip]- Definition Given By Lecturer
>System of rules to ensure that relationships between records in related tables are valid.
>Hence, the user cannot accidently change, update or delete any data.

### Rules of Referential Integrity

- Cannot enter a value in the foreign key field of the related table that does not exist in the primary key of the primary table
	>You cannot add something ( *data* ) that does not exists in the primary table.
- You cannot delete a record from a primary table if matching records exists in related table
	>You cannot delete something in the primary table that also exists in another table.

>[!info]
>Hence, that is why we have $\checkmark$ the  `Enforce Referential Integrity` check box
>- Prevents us from breaking these rules mentioned above $\uparrow$; else a warning / error message will appear
>This option can be **over-written** by checking $\checkmark$ `Cascade Updated Related Fields` and `Cascade Delete Related Records`
>- When `Cascade Updated Related Fields` are $\checkmark \ \Rightarrow$ changing a *primary key* **value** in the **primary** table will automatically update the matching values in all related records
>- When `Cascade Delete Related Records` are $\checkmark \ \Rightarrow$ deleting a **record** in *primary table* **deletes** any related records in the related table.

---

# Forms

Microsoft's Tutorial / Guide on Forms: https://support.microsoft.com/en-us/office/introduction-to-forms-e8d47343-c937-44e8-a80f-b6a83a1fa3ae#bmsimpleformtool

### What is a Form?

>[!tip]- Definition
>It is a database object that you can use to **create** a *user interface* for a database application.

>[!tip]- Teacher's Definition
>Arrangement of **controls** that one can use to *view*, *add* or *edit* data in Access.

>[!note]
>It will only display the information that you need in the way that you want to see it!
>Usually best to produce query on which to base a form
>	- Query will create a *Dynaset* / Subset of the desired data in the desired order

### Why are Forms Used?

- Easier to view, add and edit data
- Speeds up the use of database
- No need to search for what we need
- Visually Attractive
	- Making is more pleasant and efficient
- Prevent incorrect data from being entered

### Purposes of Forms

- Data Entry and Data Manipulation
- UI Design
	- Menus can be created to open other forms / reports
	- Create Dialog boxes to accept user inputs

### Conditions to Make Forms

>[!warning]
>The following conditions must be met in order to create Forms:
>- May be based on 1 or more tables / a query
>- Relationships of tables must be first created so that forms can use data from these tables
>- Record source are not required for *specialised* forms like: dialog boxes and menus

### Query and Dynaset?

>Please take a look at [[Microsoft Access ( 2007 )#What is a Form? | 'What is a Form']] first to get the context of this sub-heading.

![[Forms in Database.png | 650]]

>[!bug] NOTE
>Between the user query and form; there is the **Dynaset**
>```mermaid
>graph LR
>A[USER QUERY] --->|Dynaset| B[Form]
>```

In the diagram above; we can see that the *query* extract data from several *tables*. This produces a "**dynaset**" ( *see definition below $\downarrow$* ).
When data is changed **in** the *dynaset*, the underlying **table** is changed.

The dynaset may include data calculated in the query and derived from the data held in tables; but its **not** *actually* there $\Rightarrow$ as its only **temporary**.

>[!tip]- Definition of Dynaset
>Short for *dynamic set*; It is a temporary set of data taken from 1 or more tables in the underlying file. It is **dynamically** linked back to the database.
>- Can be updated if file is **not** locked in or only in `ReadOnly`
>- Allows the user to **view** and **update** data contained in the dynaset
>
>>Ohhhh!!! this means that if you update from the dynaset; it will "*automatically*" update the database

>[!note]
>This whole process is **outcome** based $\rightarrow$ Application developer needs to analyse what the desired output of system is in order to design the appropriate query.

# Form Controls

>Understanding Form Controls by [Oracle](https://docs.oracle.com/en/applications/jd-edwards/development-tools/9.2.x/eotfd/understanding-form-controls.html)

The most popular controls are:

1. Static Text / Labels ( *teacher called it "labels"* )
	- Label text boxes / place text on the form
2. Text Boxes
	- Display and Edit text data from underlying data source
3. Combo Boxes / Drop-Down List / Boxes
	- To select *pre-defined* items
4. Buttons
	- Trigger actions / commands within the form or application

>[!note]
>>I do not know what the fuck this means but here it is:
>
>A control that is **linked** to a field in an underlying table / query is **bound** to the field.
>	- Any changes made to the *control* also **change** the data in the field
>A control that is **<span style="color: red;">not</span>** linked is called "**unbound**".
>	- Use them as temporary storage location for data; for example:
>		- To show a result of a calculation on *other* controls
>>So by "*control*" he means $\rightarrow$ text boxes, etc?!?

## Create Form Wizard

This wizard will speed up the process of creating a form as it does all the basic work.

>[!tip]
>If you have created many forms, you may use *Form Wizard* to quickly lay out the controls on your form.
>Then you can switch to Design view to customise your form.

>[!warning]-
>Do not forget that this is my university work and not a complete documentation;
>I will be using the same examples that I have been using from above $\uparrow$

In the *ribbon menu*; select the "*Create*" tab and then you will be able to see the <button>Form</button>. After you click on it a new window / tab will appear.

Press `Ctrl + S` to save and then rename the Form as `frmStock` ( *following good naming principle* ).

Here is what is should look like $\downarrow$:

![[Form - Intial Window.png | 600]]

>[!tip]- What is a Sub-Form?
>If you have linked ( *related / relationship* ) with another table; you will be able to see the other table's "*table*" ( *WTF am I saying* ).

The forms contains *Text Box Controls* **bound** to all the fields from the underlying Stock Table.

>This form can be used to **enter**, **view** or **edit** data.

>[!info]
>The `Esc` key allows for "*rollback*" ( *similar to NixOS rollback thingy $\rightarrow$ like going back to previous version* ) $\Rightarrow$ Undoing the last action or at other times, undoing a **whole** record.

Go ahead and add some records / data into the Stock table **using** the *Form* we just created.

>Ahh you cannot add anything right? right?

This is because we are not in the "*correct*" view. To be able to use the form to **add** data; Go in the ribbon menu, find the **Format** tab ( *while you have opened the `frmStock`* ) and press the <button>View</button>

In the drop-down menu of "*View*"; there are 3 options:

- Form View
- Layout View $\rightarrow$ you are **currently** on this view
- Design View

Hence, to be able to **add** data **from** the *form*; we need to switch to "**Form View**".

>Please go ahead and **add** some records with the form.

### Adding Data using Forms

>[!warning]
>Please proceed with caution here; as if you have made a mistake here; you might need to remake the table and form if you delete something in the middle. This is because of shitty `AutoNumber`.
>There are way to go around this; but it will be a long, very long journey.

Just carefully add the required records / data into the forms.

You will see that in the `tblStock`, the records will not be updating. To **update** the `tblStock` ( *make the values appear* )

### Change the look of Form

#### What is a Property?

>[!tip]- Definition
>It is an **attribute** of an *object* that defines one of the object's characteristics, such as size, colour, screen location or behaviour

To change these characteristics / properties $\uparrow$; find the <button>Property Sheets</button> button; head over to the **form** ( *that is currently being worked on* ). Then change the layout back to `Layout View`.
After that, in the *ribbon menu* you will find the "**Arrange**" tab. Then you will be able to see the <button>Property Sheets</button>.

Or switch to the `Design View` and then click on this button ( *as shown in the photo below $\downarrow$* )

![[Forms - Another Way of Propery Sheet.png | 500]]

Now, everything is an object; what I mean by that is that the *labels* `Stock_ID`, `Description` and other parts like the logo of the form can all be "*customised*".

>Take a look of what I am talking about; this is in `Design View`.

![[Form - Design View.png | 500]] $\rightarrow$ see how everything can be changed.

>Hence we need to select the right "*object*" to customise.

#### Form Property Sheet

On the `Property Sheet`; head over to the `All` tab.

The first thing that you are going to see is:

| Record | tblStock |
| ------ | -------- |

This is because it shows the *table* that is supplying the data which the form will show.

#### Customise the Following Properties

##### General Settings

| Property | Value |
| -------- | ----- |
| Scroll Bars | Neither |
| Record Selectors | No |
| Border Style | Dialog |
| Min Max Buttons | None |
| Width | $8^{\text{"}}$ or $20.19 \ cm$ |
| Caption | Stock |
| Dividing Lines | No |

##### Form Header Bar

Now select the *Form Header Bar* ( *check the in the above $\uparrow$ photo* )

| Height | 0.5 |
| ------ | --- |

>For some reason its; not letting me change the `Height` of the *Form Header*

##### Detail Bar

Again check the above $\uparrow$ photo if you cannot find it.

| Height | $4^{\text{"}}$ or $10.16 \ cm$ |
| ------ | --- |

##### Disable Ability to Enter `Stock_ID`

To disable this property / feature; select the **input box** and then change the property `Enabled` to "*No*"

Finally your form should now look like this:

![[Form - Final Form ( haha ).png | 500]]

>Notice how we now **cannot** enter anything in the `Stock_ID` input box

>[!warning]
>There are no `Toolbox` in the newer version of Microsoft Access ( *the teacher here is using MS Access 2000* )
>I recommend these 2 links:
>- [Link 1](https://apps.kennesaw.edu/files/pr_app_uni_cdoc/doc/acc2007_l1-20120614-153928.pdf)
>- [Link 2](https://apps.kennesaw.edu/files/pr_app_uni_cdoc/doc/acc2007_l2-20120614-154003.pdf)
>
>Instead it is replaced with "*Controls*" $\downarrow$
>
>![[Forms - Toolbox Alternative.png]]
>>[!bug]
>>Need to enter `Design View` to be able to see these options!!!

#### Further Customisation

##### Add Today's Date to Header

- Select `Text Box` and then place it in the desired location of **in** the *Header*
- Delete the `Label` that comes with it

Change the following properties ( *just select the text box and right-click and hit properties* )

| Property | Value |
| -------- | ----- |
| Control Source | =Date() $\Rightarrow$ Read the date from the Computer |
| Format | Long Date |
| Enabled | No |
| Locked | Yes |

#### Change the Tab Order

>I think this heading need to go with the other customisations


#### Using Combo Boxes

>[!note] Again, what is a Combo Box?
>These are pre-defined sets of data; they are basically drop-down lists / boxes.

We use combo boxes; when data is already in the field; what I mean is; when you are going to create the form **for** [[Microsoft Access ( 2007 )#Order Entry Form | Order Table]]

To place a Combo Box; we first need to find where 'Combo Box' is located.

In MS Access 2007 it can be found like this:

1. Switch to the `Design View` ( *on the form* )
2. Go to the '**Design**' tab and head over to `Controls`

- Here it is located at:
	![[Forms - Combo Box on Control - Design Tab.png]]

- Click on this icon and place the Combo Box in a desired location

Now when you are going to place it on the form at your desired location; a window / pop-up will appear looking like this:

![[Form - Combo Box Wizard.png | 400]]

- Just select "<span style="color: green;"><em>I want the combo box to look up the values in a table or query</em></span>"

<p align="center">Table to Include</p>

As we are going to have pre-defined values from the `tblCustomber` table select **this very** table in the next menu.

- The `View` should be set to '**Tables**'

<p align="center">Attributes to Add</p>

Now it is going to tell you to enter the fields / attributes to include in the Combo Box; in this case we need:

1. 'Surname'
2. 'First Name'
3. 'Customer_ID'

Hence is should become like:

![[Form - Combo Box Wizard ( Select Fields ).png | 400]]

<p align="center">Sort in Ascending Order</p>

Sort the Field / Attribute 'Surname' and 'FirstName' in `Ascending` order.

This is how it should look like $\downarrow$:

![[Form - Combo Box Wizard ( Sorting Order ).png | 400]]

>[!info] Teacher's PDF File
>He did not sort it here; he did a long way round; this is because in MS Access *2000*, he did not have that menu ( *the screenshot above $\uparrow$* ); To change the sorting in **his** method ( *here is a little run down of this method* ):
>- Open the Property Sheets of the `Combo Box` ( *drop down thing* )
>- Find the property `Row Source`; **Right-Click** on it then we press on `Build...` ( *the icon is a weird one* )
>	- Close the Property Sheets ( *because I will stay open* )
>- You will be headed to the "**Query Builder**"
>	- ![[Form - Query Builder ( Another Way to Sort Order ).png | 300]]
>	- Here, we just need to change the value of `Sort` for 'Surname' and 'FirstName' $\rightarrow$ Set it to `Ascending`
>- Then Close and Save the Query Builder


<p align="center">Adjust the Size of Fields / Columns</p>

>Do I need to say something about this, okay I will say something about this

Grab your mouse, move the cursor to the table you want to change the size of; then click on `m1` ( *play some games then you will know that is `m1`* ) and then change the size... ( *emotional damage* )

<p align="center">Remember Value / Store Value</p>

When you reach this very menu; in our case we need to select the *second* option, like so $\downarrow$:

![[Form - Combo Box Wizard ( Remember - Store Values ).png | 400]]

<p align="center">Label / Name the Combo Box</p>

Again in our case just rename the Combo Box to `Select Customer`

>This was part of [[Microsoft Access ( 2007 )#Order Entry Form | Order Table]]; just head over to it and the continue it there. Thanks!

#### Create Combo Boxes using Lookup Tables

Again, we are now going to create another Combo Box in the same `frmOrder` form with Lookup Tables.

<h5 align="center">Steps</h1>

1. Open `tblOrder` in `Design View`
2. Select the `Payement Method` Field and Below where we can change options like `Field Size`, etc
	- There is a tab called `Lookup`, press it.
3. Now change the Field Properties to match those options below $\donwarrow$

	| Property | Value |
	| -------- | ----- |
	| Display Control | Combo Box |
	| Raw Source Type | Value List |
	| Raw Source | C;Cash;F;Finance |
	| Bound Column | 1 |
	| Column Count | 2 |
	| Column Heads | No |
	| Column Widths | `NIL` ( *do not insert any value* ) |
	| List Rows | 8 |
	| List Width | Auto |
	| Limit to List | No |

	Should Look something like this:
	![[Form - Combo Box With Lookup ( properties ).png | 285]]

4. Delete the **original** `Payment Method` Label / Control.
5. In the `frmOrder` Form; press `Alt + F8` to open up the "**Field List**"
	- This is because I could **not** find the *Field List* icon ( *in MS Access 2007* )
	Should Look something like this $\downarrow$

	![[Form - Combo Box With Lookup ( Field List ).png | 285]]

6. Double Click on the `PaymentMethod` and then it will appear on the form

>End Result should look something like [[Microsoft Access ( 2007 )#Order Entry Form]] ( *check the final version of Order Entry Form Below* )

### Customer Entry Form

>[!note]-
>If you are following this tutorial from [sunhaloolearns.netlify.app](https://sunhaloolearns.netlify.app); you might now be wondering "*WTF is happening*"; this is because you do **not** have the teacher's 💩 PDF notes.

We are now going to create a **form** for the `tblCustomer`, at the end it should look something similar to this $\downarrow$:

![[Form - What is Should look like.png | 650]]

>Lets see if I can make it similar to this... see you in some minutes

![[Form - My Customer Table.png | 650]]

<span style="color: orange;">Need to ask the teacher about the order table!!!</span>

### Order Entry Form

Similarly we need to make our Order Form look like this $\downarrow$:

>As we need to use Combo Boxes; head over to it [[Microsoft Access ( 2007 )#Using Combo Boxes | here]]!

![[Form - What is Should look like - Order Table.png | 650]]

>[!warning]
>This screenshot above $\uparrow$ is <span style="color: red;"><strong>NOT</strong></span> the *Final* version.

>[!note]
>My version has `Select Customer` instead of `Customer_ID`; this is because; I am a fool and the documentation that I got is questionable.
>The "*correct*" version is **My Version**

- My Version

![[Form - My Order Table ( NOT Final Version ).png | 650]]

#### Order Entry Form ( Final Version )

![[Form - My Order Table ( Final Version ).png | 650]]

---

# Socials

- [**Instagram**](https://www.instagram.com/s.sunhaloo/)
- [**YouTube**](https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg)
- [**GitHub**](https://www.github.com/Sunhaloo)

---

S.Sunhaloo
Thank You!