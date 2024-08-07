---
Alias: Database Design ( Assignment 1 - Oracle 10g ) - Week 15
Tag: uni, db
Module: BCNS1103C / DBT1103C
Author: S.Sunhaloo
Date: 2024-07-16
Status: Completed
---

## List of Contents

### Setup Core User

- [[Computer - Computer Spare Parts Shop in Oracle 10g#Setting Up the Core System User| Setting Up the Core System User]]
	- [[Computer - Computer Spare Parts Shop in Oracle 10g#Setup Username and Password| Setup Username and Password]]
	- [[Computer - Computer Spare Parts Shop in Oracle 10g#Grant Permission to Company's Account| Grant Permissions to Company's Account]]

---

### Data Definition Language and Data Manipulation Language

- [[Computer - Computer Spare Parts Shop in Oracle 10g#Creation of Tables and Insertion of Values| Creation of Tables and Insertion of Values]]
	- [[Computer - Computer Spare Parts Shop in Oracle 10g#Creation of Tables| Creation of Tables]]
		- [[Computer - Computer Spare Parts Shop in Oracle 10g#Customer Table| Customer Table]]
		- [[Computer - Computer Spare Parts Shop in Oracle 10g#Employee Table| Employee Table]]
		- [[Computer - Computer Spare Parts Shop in Oracle 10g#Computer Parts Table| Computer Parts Table]]
		- [[Computer - Computer Spare Parts Shop in Oracle 10g#Service Table| Service Table]]
		- [[Computer - Computer Spare Parts Shop in Oracle 10g#Stock Table| Stock Table]]
		- [[Computer - Computer Spare Parts Shop in Oracle 10g#Order Parts Table| Order Parts Table]]
		- [[Computer - Computer Spare Parts Shop in Oracle 10g#Delivery Table| Delivery Table]]
	- [[Computer - Computer Spare Parts Shop in Oracle 10g#Manipulation of Data| Manipulation of Data]]
		- [[Computer - Computer Spare Parts Shop in Oracle 10g#Insert Values into Customer Table| Insert into Customer Table]]
			- [[Computer - Computer Spare Parts Shop in Oracle 10g#Modifying Customer Table| Modify Customer Table]]
			- [[Computer - Computer Spare Parts Shop in Oracle 10g#Delete Specific Value and Record| Delete Specific Value and Record from Customer Table]]
		- [[Computer - Computer Spare Parts Shop in Oracle 10g#Insert Values into Employee Table| Insert into Employee Table]]
		- [[Computer - Computer Spare Parts Shop in Oracle 10g#Insert Values into Computer Parts Table| Insert Into Computer Parts Table]]
		- [[Computer - Computer Spare Parts Shop in Oracle 10g#Insert Values into Service Table| Insert Into Service Table]]
		- [[Computer - Computer Spare Parts Shop in Oracle 10g#Insert Values into Stock Parts Table| Insert Into Stock Parts Table]]
		- [[Computer - Computer Spare Parts Shop in Oracle 10g#Insert Values into Order Parts Table| Insert Into Order Parts Table]]
		- [[Computer - Computer Spare Parts Shop in Oracle 10g#Insert Values into Delivery Table| Insert Into Delivery Table]]

---

### Setting Up Other Users

- [[Computer - Computer Spare Parts Shop in Oracle 10g#Setting Up Other Users| Setting Up Other Users]]
	- [[Computer - Computer Spare Parts Shop in Oracle 10g#Manager| Manager Account]]
		- [[Computer - Computer Spare Parts Shop in Oracle 10g#Grant Manager Permissions| Grant Permissions to Manager]]
		- [[Computer - Computer Spare Parts Shop in Oracle 10g#Testing Manager Account| Testing Manager Account]]
	- [[Computer - Computer Spare Parts Shop in Oracle 10g#Sales Representative| Sales Representative Account]]
		- [[Computer - Computer Spare Parts Shop in Oracle 10g#Grant Sales Representative Permissions| Grant Permissions to Sales Representative]]
		- [[Computer - Computer Spare Parts Shop in Oracle 10g#Testing Sales Representative Account| Testing Sales Representative Account]]
	- [[Computer - Computer Spare Parts Shop in Oracle 10g#Technician| Technician Account]]
		- [[Computer - Computer Spare Parts Shop in Oracle 10g#Grant Technician Permissions| Grant Technician Permissions]]
		- [[Computer - Computer Spare Parts Shop in Oracle 10g#Testing Technician Account| Testing Technician Account]]
	- [[Computer - Computer Spare Parts Shop in Oracle 10g#Cashier| Cashier Account]]
		- [[Computer - Computer Spare Parts Shop in Oracle 10g#Grant Cashier Permissions| Grant Cashier Permission]]
		- [[Computer - Computer Spare Parts Shop in Oracle 10g#Revoking Permissions| Revoke Cashier Permissions]]
		- [[Computer - Computer Spare Parts Shop in Oracle 10g#Testing Cashier Account| Testing Cashier Account]]
	- [[Computer - Computer Spare Parts Shop in Oracle 10g#Delivery| Delivery Account]]
		- [[Computer - Computer Spare Parts Shop in Oracle 10g#Grant Delivery Permission| Grant Delivery Permission]]
		- [[Computer - Computer Spare Parts Shop in Oracle 10g#Testing Delivery Account| Testing Delivery Account]]

---

### Miscellaneous

- [[Computer - Computer Spare Parts Shop in Oracle 10g#Output List of Users| Output List of Users]]

---

### My Links

- [[Computer - Computer Spare Parts Shop in Oracle 10g#Socials| Link to Socials]]

---

# Setting Up the Core System User

>[!info]
>This user will be considered to be the [[Database Administrator]] of the Company ( *Computer - Computer Spare Parts Shop* )
>This user `computer_parts` will be responsible for ( *initially* ) creating, inserting, altering, updating and deleting our tables.

## Setup Username and Password

```console

Username: computer_parts
Password: spare_parts

```

To create our user go ahead and run the command below $\downarrow$:

```SQL

CREATE USER computer_parts IDENTIFIED BY "spare_parts";

```

After that, we need to check if we actually created the user `computer_parts`.
The command below $\downarrow$ will select the fields `username`, `account_status` and date `created` from the Table `dba_users`.

>Only the `SYS` / `SYSTEM` user has this table ( *i.e `dba_users`* )

```SQL

SELECT username, account_status, created FROM dba_users WHERE username = 'COMPUTER_PARTS';

```

>We need to use `username = 'COMPUTER_PARTS'` instead of using `username = 'computer_parts'`.
>Because once you create a user in Oracle 10g; it will convert it from `computer_parts` to `COMPUTER_PARTS` ( *basically all caps!* )

You should get an output that look similar to this:

```console

"USERNAME","ACCOUNT_STATUS","CREATED"
"COMPUTER_PARTS","OPEN","13-JUL-24"

```

>[!warning]
>These commands above need to be run in the `SYS` / `SYSTEM` account.
>Else, its **not** going to be successful if you run them in a normal account.

## Grant Permission to Company's Account

Because this is the "*main*" account of the company / the Database Administrator of the Company. We need to grant this user every possible permissions like `CONNECT`, `RESOURCE` and `TABLESPACE`

To achieve this we need to use the command give below $\downarrow$:

```SQL

GRANT CONNECT, RESOURCE, UNLIMITED TABLESPACE TO computer_parts;

```

>If you need explanations on what these privileges to; head over to [[Oracle 10g - SQL Commands]] to learn more about them.

### Verify Permissions of Company's Account

To check if user `computer_parts` has been granted privileges; run this command again in the `SYS` / `SYSTEM` account:

```SQL

SELECT * FROM dba_role_privs WHERE grantee = 'COMPUTER_PARTS';

```

The output of this should look something like this:

```console

"GRANTEE","GRANTED_ROLE","ADMIN_OPTION","DEFAULT_ROLE"
"COMPUTER_PARTS","CONNECT","NO","YES"
"COMPUTER_PARTS","RESOURCE","NO","YES"

```

>Nevertheless, I do **not** know the command to make it show that the user has `UNLIMITED TABLESPACE`.

>[!success]
>You have now created the user `computer_parts` which is identified by the password `spare_parts`!
>You can now logout of this `SYS` / `SYSTEM` account and head over to the login page and enter the credentials for the newly created user.

---

# Creation of Tables and Insertion of Values

## Creation of Tables

In the company Sun's Systems, we have 7 tables and they are as follows:

- Customer
- Employee
- Computer Parts
- Service
- Stock
- Order
- Delivery

### Customer Table

```SQL

CREATE TABLE Customer (
    CustomerID NUMBER PRIMARY KEY NOT NULL,
    FirstName VARCHAR(30),
    LastName VARCHAR(30),
    Address VARCHAR(120),
    MobileNumber NUMBER(8),
    Gender CHAR(1),
    CONSTRAINT mobile_length CHECK ( LENGTH ( MobileNumber ) = 8 ),
    CONSTRAINT gender_chk CHECK ( Gender IN ( 'M', 'F' ) )
);

```

This $\uparrow$ is the command that we need to create our `Customer` table.

In this table we have 2 **constraints**; they are:

- `mobile_length`
	- It checks whether the **length** of the phone number entered is 8
- `gender_chk`
	- It checks whether that the gender entered is either `M` or `F`

#### Verify Creation of Table `Customer`

To verify if we have corrected created our table `Customer` we can either use `DESCRIBE` or `SELECT` commands

>[!info]
>I will show you how to use / what the syntax looks like for the `DESCRIBE` command
>But I will be using the `SELECT` command; Why? Because it provides a `.csv` file that can be exported.
>>Nevertheless, the `DESCRIBE` command is **better**!!!

- Using `DESCRIBE` Command

```SQL

DESCRIBE Customer;

```

- Using `SELECT` Command

```SQL

SELECT owner, table_name, status FROM all_tables WHERE owner = 'COMPUTER_PARTS' AND table_name = 'CUSTOMER';

```

>[!tip] Explanation
>This command above will select the fields `owner`, `table_name` and `status` from the table `all_tables` and only select the record where we have `table_name = 'CUSTOMER'`.
>>Actually we have `all_tables` and also `dba_tables` Tables.
>>But the `dba_tables` can only be run if you **have** *DBA* privileges.

You should get a result that looks something like this:

```console

"OWNER","TABLE_NAME","STATUS"
"COMPUTER_PARTS","CUSTOMER","VALID"

```

### Employee Table

```SQL

CREATE TABLE Employee (
    EmployeeID NUMBER PRIMARY KEY NOT NULL,
    FirstName VARCHAR(30),
    LastName VARCHAR(30),
    Department VARCHAR(60) NOT NULL,
    DateOfBirth DATE,
    MobileNumber NUMBER(8) NOT NULL,
    Gender CHAR(1) DEFAULT 'M',
    Salary NUMBER,
    CONSTRAINT salary_chk_employee CHECK ( Salary >= 20000 ),
    CONSTRAINT mobile_length_employee CHECK ( LENGTH ( MobileNumber ) = 8 ),
    CONSTRAINT gender_chk_employee CHECK ( Gender IN ( 'M', 'F' ) ),
    CONSTRAINT dept_chk_employee CHECK ( Department IN ( 'Manager', 'Cashier', 'Sales Representative', 'Technician' ) )
);

```

In this table we have 4 **constraints**; they are:

- `salary_chk`
	- It checks whether the salary is equal to or more than '20000'
- `mobile_length_employee`
	- It checks whether the **length** of the phone number entered is 8
- `gender_chk_employee`
	- It checks whether that the gender entered is either `M` or `F`
- `dept_chk_employee`
	- It checks whether department entered is either `Manager` / `Cashier` / `Sales Representative` / `Technician`

>[!note]
>You might have noticed that we have `mobile_length_employee` and `gender_chk_employee` instead of `mobile_length` and `gender_chk`!
>This is because we **need** to have different *constraints* name in a tablespace. As we are using a **Relational Database Management System** ( RDBMS )
>>As you know; [[Microsoft Access ( 2007 ) | Microsoft Access is also RDBMS]]
>
>>[!warning]
>>If you use the same constraint **name**; you will get this error message:
>>```console
>>ORA-02264: name already used by an existing constraint
>>```

#### Verify Creation of Table `Employee`

>As I said; I will **not** be using the `DESCRIBE` command because I cannot export it as a `.csv` file.
>I will also not do any screenshots as one must know how to read a `.csv` file... *I am not on the computer that has Oracle 10g installed*

```SQL

SELECT owner, table_name, status FROM all_tables WHERE owner = 'COMPUTER_PARTS' AND table_name = 'EMPLOYEE';

```

The output after running the command $\uparrow$ is going to be:

```console

"OWNER","TABLE_NAME","STATUS"
"COMPUTER_PARTS","EMPLOYEE","VALID"

```

### Computer Parts Table

>[!info]
>What is the point of this `ComputerParts` table? As we are going to create a `Stock` table later on.
>
>The point of this table is to have a *catalogue* of products that we can refer to.
>While our `Stock` table will be used to keep track of the products that are currently available to sell to customers.

```SQL

CREATE TABLE ComputerParts (
    PartID NUMBER PRIMARY KEY NOT NULL,
    PartMake VARCHAR(40),
    PartName VARCHAR(120),
    Category VARCHAR(15) NOT NULL,
    Tested CHAR(1) NOT NULL,
    Price NUMBER DEFAULT 250 NOT NULL,
    Warranty NUMBER,
    CONSTRAINT chk_Category CHECK ( Category IN ( 'CPU', 'GPU', 'RAM', 'Storage-HDD', 'Storage-SSD', 'Storage-NVMe', 'Fans', 'Motherboard', 'PSU', 'Case', 'Wiring' ) ),
    CONSTRAINT chk_Tested_parts CHECK ( Tested IN ( 'Y', 'N' ) ),
    CONSTRAINT chk_Price_parts CHECK ( Price >= 250 ),
    CONSTRAINT chk_Warranty_parts CHECK ( Warranty BETWEEN 0 AND 10 )
);

```

Again, in this table we also have 4 **constraints**:

- `chk_Category`
	- Check if the category of the computer part falls in that list of values ( *check above $\uparrow$* )
- `chk_Tested_parts`
	- We check to see if the computer part has been tested or not
- `chk_Price_parts`
	- Here we make sure that the price of a computer part does not fall below 250 rupees
- `chk_Warranty_parts`
	- Checks if the warranty of the part is between 0 and 10 years inclusive
	
#### Verify Creation of Table `ComputerParts`

```SQL

SELECT owner, table_name, status FROM all_tables WHERE owner = 'COMPUTER_PARTS' AND table_name = 'COMPUTERPARTS';

```

Here is the output after querying:

```console

"OWNER","TABLE_NAME","STATUS"
"COMPUTER_PARTS","COMPUTERPARTS","VALID"

```

### Service Table

```SQL

CREATE TABLE  Service (
	ServiceID NUMBER PRIMARY KEY NOT NULL,
	CustomerID NUMBER NOT NULL,
	Service VARCHAR(15),
	ServiceDate DATE NOT NULL,
	Price NUMBER,
	CONSTRAINT fk_CustomerID FOREIGN KEY ( CustomerID ) REFERENCES Customer ( CustomerID ),
	CONSTRAINT service_chk CHECK ( Service IN ( 'Consultation', 'Repair', 'Build' ) ),
	CONSTRAINT price_chk CHECK ( Price BETWEEN 500 AND 1000 )
);

```

In this case, we have 3 **constraints**; namely:

- `fk_CustomerID`
	- After creating the attribute / field `CustomerID`
	- We make it become a Foreign Key using the command you see above $\uparrow$
- `service_chk`
	- Checks if service type is either `Consultation`, `Repair` or `Build`
- `price_chk`
	- We check if the price of the service falls between 500 and 1000 inclusive.

#### Verify Creation of Table `Service`

```SQL

SELECT owner, table_name, status FROM all_tables WHERE owner = 'COMPUTER_PARTS' AND table_name = 'SERVICE';

```

We will get the output:

```console

"OWNER","TABLE_NAME","STATUS"
"COMPUTER_PARTS","SERVICE","VALID"

```

#### Add `DEFAULT` Value to `Price` Attribute

I want to add a default value of `500` so that when the user does now specify the amount; it will automatically be `500`.

To achieve this, we need to use the command below $\downarrow$:

```SQL

ALTER TABLE Service MODIFY Price DEFAULT 500;

```

>[!tip]
>In this case, you can run the `DESCRIBE Service` command to be able to see the changes.

### Stock Table

```SQL

CREATE TABLE StockParts (
	StockID NUMBER PRIMARY KEY NOT NULL,
    PartID NUMBER NOT NULL,
    PartMake VARCHAR(40),
    PartName VARCHAR(120),
    Category VARCHAR(15),
    BuyingPrice NUMBER,
    SellingPrice NUMBER,
    FOREIGN KEY ( PartID ) REFERENCES ComputerParts ( PartID ),
    CONSTRAINT Category_chk CHECK (Category IN ( 'CPU', 'GPU', 'RAM', 'Storage-HDD', 'Storage-SSD', 'Storage-NVMe', 'Fans', 'Motherboard', 'PSU', 'Case', 'Wiring' ) ),
    CONSTRAINT BuyingPrice_chk CHECK ( BuyingPrice >= 0 ),
    CONSTRAINT SellingPrice_chk CHECK ( SellingPrice >= BuyingPrice )
);

```

>Here we used another method to create our **Foreign Key**.

In this table we also have 3 **constraints**; they are:

- `Category_chk`
	- It will check it the category of the computer part fall in the list of values
- `BuyingPrice`
	- The buying price of the product / computer part should be:
		- $\gt$ 0 and $\lt$ Selling Price
- `Selling Price`
	- The selling price of the part should be $\gt$ the buying price

#### Verify Creation of Table `StockParts`

```SQL

SELECT owner, table_name, status FROM all_tables WHERE owner = 'COMPUTER_PARTS' AND table_name = 'STOCKPARTS';

```

This should be the output after running the command above $\uparrow$:

```console

"OWNER","TABLE_NAME","STATUS"
"COMPUTER_PARTS","STOCKPARTS","VALID"

```

#### Add another Column to `StockParts` Table

We need to add another column / field / attribute `Quantity` to our `StockParts` Table.

To add this attribute, we need this command below $\downarrow$:

```SQL

ALTER TABLE StockParts ADD ( Quantity NUMBER NOT NULL );

```

### Order Parts Table

```SQL

CREATE TABLE OrderParts (
    OrderPID NUMBER PRIMARY KEY NOT NULL,
    CustomerID NUMBER NOT NULL,
    FirstName VARCHAR(30),
    LastName VARCHAR(30),
    OrderDate DATE,
    PartID NUMBER NOT NULL,
    PartMake VARCHAR(30),
    PartName VARCHAR(30),
    Price NUMBER NOT NULL,
    PaymentMethod CHAR(1) NOT NULL,
    FOREIGN KEY ( CustomerID ) REFERENCES Customer( CustomerID ),
    FOREIGN KEY ( PartID ) REFERENCES ComputerParts( PartID ),
    CONSTRAINT Price_chk_OrderParts CHECK ( Price >= 250 ),
    CONSTRAINT PaymentMethod_chk_OrderParts CHECK ( PaymentMethod IN ( 'C', 'F' ) )
);

```

In this table we have 2 **Foreign Keys** and 2 **constraints**:

- `Price_chk_OrderParts`
	- Checks if our price is equal to or greater than 250
- `PaymentMethod_chk_OrderParts`
	- It will check from a list of values if `PaymentMethod` entered is either `C` or `F`

#### Verify Creation of Table `OrderParts`

```SQL

SELECT owner, table_name, status FROM all_tables WHERE owner = 'COMPUTER_PARTS' AND table_name = 'ORDERPARTS';

```

You should get the results after running the above $\nwarrow$:

```console

"OWNER","TABLE_NAME","STATUS"
"COMPUTER_PARTS","ORDERPARTS","VALID"

```

### Delivery Table

```SQL

CREATE TABLE Delivery (
    DeliveryID NUMBER PRIMARY KEY NOT NULL,
    CustomerID NUMBER NOT NULL,
    FirstName VARCHAR(30),
    LastName VARCHAR(30),
    Address VARCHAR(30),
    MobileNumber NUMBER(8) NOT NULL,
    OrderDate DATE,
    PartID NUMBER NOT NULL,
    PartMake VARCHAR(30),
    PartName VARCHAR2(120),
    Price NUMBER NOT NULL,
    FOREIGN KEY ( CustomerID ) REFERENCES Customer ( CustomerID ),
    FOREIGN KEY ( PartID ) REFERENCES ComputerParts( PartID ),
    CONSTRAINT Price_chk_Delivery CHECK ( Price >= 250 ),
    CONSTRAINT mobile_chk_Delivery CHECK ( LENGTH( MobileNumber ) = 8 )
);

```

In this table we also have 2 **Foreign Keys** and 2 **constraints**:

- `Price_chk_Delivery`
	- Checks if our price is equal to or greater than 250
- `mobile_chk_Delivery`
	- It will check if the length of the phone number entered is 8

#### Verify Creation of `Delivery` Table

```SQL

SELECT owner, table_name, status FROM all_tables WHERE owner = 'COMPUTER_PARTS' AND table_name = 'DELIVERY';

```

You should get the output $\downarrow$ after running the command:

```console

"OWNER","TABLE_NAME","STATUS"
"COMPUTER_PARTS","DELIVERY","VALID"

```

## Manipulation of Data

### Insert Values into Customer Table

To insert any value in any table; we use the `INSERT INTO` command. Let's go ahead and try to *add* some values into the `Customer` Table

---

#### But First!

As you can see during our creation of our tables. We have the attribute `MobileNumber`. I am not going to waste time thinking about what "*numbers*" to write there.
Hence, I am going to make a simple Python Program that will:

- Create 100 numbers in the Mauritius Mobile Phone Format
- Output these values / phone numbers to a file ( *not opening / writing to any file $\rightarrow$ doing that straight from the Terminal* )

```python

# import random module
import random as rd

# number of lines to output
for i in range(100):

    # pre-pend the random values with the number '5'
    print("5", end='')
    
    # number of characters / numbers to output in a line
    for j in range(7):

        # create the random number variable
        rand_num = rd.randint(0, 9)
        # output the value on the same line
        print(rand_num, end='')

    # change line
    print()

```

To make the code output to a file ( *for example `out.txt`* ), we need to run the command in the Terminal ( Bash / Powershell )

```bash

python test.py > out.txt

```

>- `test.py` $\Rightarrow$ Our Python File
>- `out.txt` $\Rightarrow$ Our Output File

>[!tip] Output
>Here is part / sneak peek at the file `out.txt`
>```console
>54452882
>58473284
>52811651
>53434029
>```

>Hence, we can use these numbers as insert values for the field / column `MobilePhone`!

---

#### Back to Insertion of Values into Customer Table

The commands that are found in the code block below $\downarrow$ are used to insert value into the `Customer` Table

```SQL

INSERT INTO Customer (CustomerID, FirstName, LastName, Address, MobileNumber, Gender)
VALUES (1, 'Carlos', 'Sainz', 'Old Moka Road', 52080842, 'M');

INSERT INTO Customer (CustomerID, FirstName, LastName, Address, MobileNumber, Gender)
VALUES (2, 'Lewis', 'Hamilton', 'New Moka Road', 53348245, 'M');

INSERT INTO Customer (CustomerID, FirstName, LastName, Address, MobileNumber, Gender)
VALUES (3, 'Jane', 'Doe', 'Central Avenue', 51234567, 'F');

INSERT INTO Customer (CustomerID, FirstName, LastName, Address, MobileNumber, Gender)
VALUES (4, 'Emily', 'Clark', 'Bay Street', 52345678, 'F');

INSERT INTO Customer (CustomerID, FirstName, LastName, Address, MobileNumber, Gender)
VALUES (5, 'John', 'Smith', 'Greenwood Lane', 53456789, 'M');

```

>You should **not** get any error when inserting these values!

>[!warning]
>If you copy everything and try to paste it into the input box in Oracle 10g '*SQL Commands*'. It will <span style="color: red;"><strong>not</strong></span> work!
>
>>[!tip] Fix
>>You will **have** to insert *each* `INSERT` commands **separately**!
>>
>>>I do not know the reason why we need to insert **record** one by one
>>>I just checked in [Apex Oracle](https://apex.oracle.com) also and its the **same** story.

#### Check if Constraint is Working

We are going to add a value where the **length** of `MobileNumber` is $\gt$ '8'

Insert this values below $\downarrow$:

```SQL

INSERT INTO Customer (CustomerID, FirstName, LastName, Address, MobileNumber, Gender)
VALUES (6, 'test-FirstName', 'test-LastName', 'test-Address', 12345678910, 'M');

```

>[!bug]
>You **should** get an *error*!
>The error should be something like:
>```console
>ORA-01438: value larger than specified precision allowed for this column
>```

#### Verify Insertion of Values ( `Customer` Table )

We are going to *check* if our values added are correct and does not have any errors
To view the values in the `Customer` Table; run the following command below $\downarrow$:

```SQL

SELECT * FROM Customer;

```

You should get the output:

```console

"CUSTOMERID","FIRSTNAME","LASTNAME","ADDRESS","MOBILENUMBER","GENDER"
"1","Carlos","Sainz","Old Moka Road","52080842","M"
"2","Lewis","Hamilton","New Moka Road","53348245","M"
"3","Jane","Doe","Central Avenue","51234567","F"
"4","Emily","Clark","Bay Street","52345678","F"
"5","John","Smith","Greenwood Lane","53456789","M"

```

### Modifying Customer Table

At this point we have:

- Created our `Customer` Table
	- Check if we created it correctly
- Inserted our values using `INSERT` command
	- Check if we inserted our values correctly

>We are successful in performing those actions $\uparrow$!!!

#### Add `NOT NULL` to `Customer`

Now, I want to **alter** the table so that we can add the *constraint* `NOT NULL` to the attribute / field `MobileNumber` and `Address`

To make this change happen; run the command:

```SQL

ALTER TABLE Customer MODIFY ( 
    Address VARCHAR(120) NOT NULL,
    MobileNumber NUMBER(8) NOT NULL,
);

```

>I think that the code it self-explanatory; but still

So we use the `ALTER` command to *alter* something in a table; in this case, our `Customer` Table.
As we are "*modifying*" the existing columns, we are going to use the `MODIFY` which forms part or our [[Database Languages#Data Definition Language ( DDL ) | Data Definition Language]].
In this case, we *re-wrote* our column name and its respective data type and added the `NOT NULL` *constraint*.

#### Add `DEFAULT` to `Customer`

I want to add a default value to the attribute / field `Gender` where `M` is going to be the **default** value.

To achieve this; we can run the following command:

```SQL

ALTER TABLE Customer MODIFY (
    Gender CHAR(1) DEFAULT 'M'
);

```

Here, we use the same command as above $\uparrow$ but instead of writing `NOT NULL`; we wrote `DEFAULT 'M'`.
This will make it so that when the user does not enter any value for the `Gender` column.
It will **automatically** add the value `M` to it!

#### Delete Specific Value and Record

I want to insert a *test* record and then delete the specific value from that record and also delete the whole record.

Add the following record into our `Customer` Table

```SQL

INSERT INTO Customer ( CustomerID, FirstName, LastName, Address, MobileNumber ) VALUES ( 6, 'test-FirstName', 'test-LastName', 'test-Address', 12345678 );

```

Verify that the record / row of value has been inserted as intended $\downarrow$:

```SQL

SELECT * FROM Customer;

```

Here is the output after our insertion:

```console

"CUSTOMERID","FIRSTNAME","LASTNAME","ADDRESS","MOBILENUMBER","GENDER"
"1","Carlos","Sainz","Old Moka Road","52080842","M"
"2","Lewis","Hamilton","New Moka Road","53348245","M"
"3","Jane","Doe","Central Avenue","51234567","F"
"4","Emily","Clark","Bay Street","52345678","F"
"5","John","Smith","Greenwood Lane","53456789","M"
"6","test-FirstName","test-LastName","test-Address","12345678","M"

```

>Notice how our `Gender` attribute got the *default* value `M` even though we did **not** specify any value to add!

##### Delete Specific Value

>[!warning]
>You <span style="color: red;">cannot</span> **delete** a *value* from an attribute / field that has the *constraint* `NOT NULL`
>
>>That all I am going to say, because I think that the above $\nwarrow$ was easy to understand!

To delete a **specific** value from a field; you can use the following command below $\downarrow$:

```SQL

UPDATE Customer
SET FirstName = ''
WHERE CustomerID = 6;

```

Verify if it actually remove the First Name from the record with `CustomerID` '6'

Run the following command:

```SQL

SELECT * FROM Customer WHERE CustomerID = 6;

```

You should get the output:

```console

"CUSTOMERID","FIRSTNAME","LASTNAME","ADDRESS","MOBILENUMBER","GENDER"
"6","","test-LastName","test-Address","12345678","M"

```

>[!success]
>We have managed to delete a specific value from the `Customer` table at the column `FirstName`

##### Delete Entire Record

>Okay, we have deleted a specific value from a table's.
>But how do we actually remove a whole record?

This is achieved using the command below $\downarrow$:

```SQL

DELETE FROM Customer WHERE CustomerID = 6;

```

We can verify if that record has been deleted using the following command:

```SQL

SELECT * FROM Customer;

```

You should get the output:

```console

"CUSTOMERID","FIRSTNAME","LASTNAME","ADDRESS","MOBILENUMBER","GENDER"
"1","Carlos","Sainz","Old Moka Road","52080842","M"
"2","Lewis","Hamilton","New Moka Road","53348245","M"
"3","Jane","Doe","Central Avenue","51234567","F"
"4","Emily","Clark","Bay Street","52345678","F"
"5","John","Smith","Greenwood Lane","53456789","M"

```

>[!success] Info
>Now we know the major / frequent command.
>We can now continue to insert values into the other tables.

>[!note]
>As from now on, I will only insert "*good*" values.
>Because from the above $\uparrow$; I showed you how to perform many things like `UPDATE`, `ALTER` and `DELETE`.
>We know that the **constraints** are working fine and the tables has been created correctly ( *again, scroll up if you need to check* )
>Hence, I will only be writing / typing the required things as from now on.
>
>>Until we get to the *Creation of other Users* then I will be explaining the process and the commands again.

### Insert Values into Employee Table

Here are the values that I inserted into the `Employee` table.

```SQL

INSERT INTO Employee (EmployeeID, FirstName, LastName, Department, DateOfBirth, MobileNumber, Gender, Salary)
VALUES (10, 'Eleanor', 'Wong', 'Manager', TO_DATE('18-07-1987', 'DD-MM-YYYY'), 54456789, 'F', 28000);

INSERT INTO Employee (EmployeeID, FirstName, LastName, Department, DateOfBirth, MobileNumber, Gender, Salary)
VALUES (11, 'Liam', 'Nguyen', 'Sales Representative', TO_DATE('25-04-1993', 'DD-MM-YYYY'), 57788900, 'M', 30000);

INSERT INTO Employee (EmployeeID, FirstName, LastName, Department, DateOfBirth, MobileNumber, Gender, Salary)
VALUES (12, 'Aria', 'Liu', 'Cashier', TO_DATE('12-09-1990', 'DD-MM-YYYY'), 58899001, 'F', 26000);

INSERT INTO Employee (EmployeeID, FirstName, LastName, Department, DateOfBirth, MobileNumber, Gender, Salary)
VALUES (13, 'Max', 'Smith', 'Technician', TO_DATE('15-11-1995', 'DD-MM-YYYY'), 59900123, 'M', 27000);

INSERT INTO Employee (EmployeeID, FirstName, LastName, Department, DateOfBirth, MobileNumber, Gender, Salary)
VALUES (14, 'Sophia', 'Garcia', 'Manager', TO_DATE('28-03-1989', 'DD-MM-YYYY'), 51123456, 'F', 29000);

```

Verify that all the values has been added correctly with $\downarrow$:

```SQL

SELECT * FROM Employee;

```

Here is the result after running the above $\uparrow$ command:

```console

"EMPLOYEEID","FIRSTNAME","LASTNAME","DEPARTMENT","DATEOFBIRTH","MOBILENUMBER","GENDER","SALARY"
"10","Eleanor","Wong","Manager","18-JUL-87","54456789","F","28000"
"11","Liam","Nguyen","Sales Representative","25-APR-93","57788900","M","30000"
"12","Aria","Liu","Cashier","12-SEP-90","58899001","F","26000"
"13","Max","Smith","Technician","15-NOV-95","59900123","M","27000"
"14","Sophia","Garcia","Manager","28-MAR-89","51123456","F","29000"

```

#### Delete `Gender` Attribute

Why are we deleting the `Gender` attribute from `Employee` table?

Simple Answer: I do **not** have a `Gender` field in my [[Computer - Computer Spare Parts Shop Requirements#Employee Table | Requirements Employee Table]]

To delete / drop this `Gender` column, we need to run the command found below $\downarrow$:

```SQL

ALTER TABLE Employee DROP COLUMN Gender;

```

>[!warning] Don't get scared!!!
>When you run the above $\uparrow$ command; you are going to see:
>```console
>Table dropped
>```
>Don't worry! It did **not** actually deleted the entire table.

##### Updated Employee Table ( *New Output* )

```SQL

SELECT * FROM Employee;

```

The results should be:

```console

"EMPLOYEEID","FIRSTNAME","LASTNAME","DEPARTMENT","DATEOFBIRTH","MOBILENUMBER","SALARY"
"10","Eleanor","Wong","Manager","18-JUL-87","54456789","28000"
"11","Liam","Nguyen","Sales Representative","25-APR-93","57788900","30000"
"12","Aria","Liu","Cashier","12-SEP-90","58899001","26000"
"13","Max","Smith","Technician","15-NOV-95","59900123","27000"
"14","Sophia","Garcia","Manager","28-MAR-89","51123456","29000"

```

>As you can see, we do **not** have our `Gender` attribute anymore!

### Insert Values into Computer Parts Table

Insert these values into our `ComputerParts` table.

>We are going to add a *lot* of values in this table... *compared to the other tables*

```SQL

INSERT INTO ComputerParts (PartID, PartMake, PartName, Category, Tested, Price, Warranty)
VALUES (1, 'Intel', 'Core i5-11400F', 'CPU', 'N', 5000, 3);

INSERT INTO ComputerParts (PartID, PartMake, PartName, Category, Tested, Price, Warranty)
VALUES (2, 'AMD', 'Ryzen 7 5800X', 'CPU', 'Y', 6500, 3);

INSERT INTO ComputerParts (PartID, PartMake, PartName, Category, Tested, Price, Warranty)
VALUES (3, 'NVIDIA', 'RTX 3060 Ti', 'GPU', 'Y', 12000, 2);

INSERT INTO ComputerParts (PartID, PartMake, PartName, Category, Tested, Price, Warranty)
VALUES (4, 'Corsair', 'Vengeance LPX 16GB', 'RAM', 'Y', 3000, 5);

INSERT INTO ComputerParts (PartID, PartMake, PartName, Category, Tested, Price, Warranty)
VALUES (5, 'Samsung', '970 EVO Plus 1TB', 'Storage-NVMe', 'N', 8000, 5);

INSERT INTO ComputerParts (PartID, PartMake, PartName, Category, Tested, Price, Warranty)
VALUES (6, 'Seagate', 'BarraCuda 2TB', 'Storage-HDD', 'N', 3500, 3);

INSERT INTO ComputerParts (PartID, PartMake, PartName, Category, Tested, Price, Warranty)
VALUES (7, 'Noctua', 'NH-D15 CPU Cooler', 'Fans', 'Y', 2000, 2);

INSERT INTO ComputerParts (PartID, PartMake, PartName, Category, Tested, Price, Warranty)
VALUES (8, 'MSI', 'B450 TOMAHAWK MAX', 'Motherboard', 'Y', 4000, 2);

INSERT INTO ComputerParts (PartID, PartMake, PartName, Category, Tested, Price, Warranty)
VALUES (9, 'EVGA', 'SuperNOVA 750 G5', 'PSU', 'Y', 6000, 5);

INSERT INTO ComputerParts (PartID, PartMake, PartName, Category, Tested, Price, Warranty)
VALUES (10, 'NZXT', 'H510 Elite', 'Case', 'N', 4500, 2);

```

>Again, you **cannot** copy this whole code block!
>You will have to copy and paste each of them separately.

>[!note]-
>The `Price` are fictional... *An NVIDIA RTX 3060 TI* does **not** costs only 12000
>Nevertheless, the price is in Mauritian Rupees

Let's verify that the values above $\uparrow$ has been added correctly:

```SQL

SELECT * FROM ComputerParts;

```

Here is the result after running the command:

```console

"PARTID","PARTMAKE","PARTNAME","CATEGORY","TESTED","PRICE","WARRANTY"
"1","Intel","Core i5-11400F","CPU","N","5000","3"
"2","AMD","Ryzen 7 5800X","CPU","Y","6500","3"
"3","NVIDIA","RTX 3060 Ti","GPU","Y","12000","2"
"4","Corsair","Vengeance LPX 16GB","RAM","Y","3000","5"
"5","Samsung","970 EVO Plus 1TB","Storage-NVMe","N","8000","5"
"6","Seagate","BarraCuda 2TB","Storage-HDD","N","3500","3"
"7","Noctua","NH-D15 CPU Cooler","Fans","Y","2000","2"
"8","MSI","B450 TOMAHAWK MAX","Motherboard","Y","4000","2"
"9","EVGA","SuperNOVA 750 G5","PSU","Y","6000","5"
"10","NZXT","H510 Elite","Case","N","4500","2"

```

### Insert Values into Service Table

```SQL

INSERT INTO Service (ServiceID, CustomerID, Service, ServiceDate, Price)
VALUES (1, 1, 'Consultation', TO_DATE('20-07-2024', 'DD-MM-YYYY'), 600);

INSERT INTO Service (ServiceID, CustomerID, Service, ServiceDate, Price)
VALUES (2, 2, 'Repair', TO_DATE('25-07-2024', 'DD-MM-YYYY'), 750);

INSERT INTO Service (ServiceID, CustomerID, Service, ServiceDate, Price)
VALUES (3, 3, 'Build', TO_DATE('30-07-2024', 'DD-MM-YYYY'), 900);

```

Verifying that our tables have been populated:

```SQL

SELECT * FROM Service;

```

This should be the output after running the above $\uparrow$ command:

```console

"SERVICEID","CUSTOMERID","SERVICE","SERVICEDATE","PRICE"
"1","1","Consultation","20-JUL-24","600"
"2","2","Repair","25-JUL-24","750"
"3","3","Build","30-JUL-24","900"

```

### Insert Values into Stock Parts Table

Use these command below $\downarrow$ to insert values into the table `StockParts`

```SQL

INSERT INTO StockParts (StockID, PartID, PartMake, PartName, Category, BuyingPrice, SellingPrice, Quantity)
VALUES (1, 1, 'Intel', 'Core i5-11400F', 'CPU', 4800, 5000, 10);

INSERT INTO StockParts (StockID, PartID, PartMake, PartName, Category, BuyingPrice, SellingPrice, Quantity)
VALUES (2, 3, 'NVIDIA', 'RTX 3060 Ti', 'GPU', 11500, 12000, 5);

INSERT INTO StockParts (StockID, PartID, PartMake, PartName, Category, BuyingPrice, SellingPrice, Quantity)
VALUES (3, 6, 'Seagate', 'BarraCuda 2TB', 'Storage-HDD', 3300, 3500, 20);

INSERT INTO StockParts (StockID, PartID, PartMake, PartName, Category, BuyingPrice, SellingPrice, Quantity)
VALUES (4, 10, 'NZXT', 'H510 Elite', 'Case', 4300, 4500, 8);

```

To check if we *added* the values correctly in our table; run the following command $\downarrow$:

```SQL

SELECT * FROM StockParts;

```

The output should be:

```console

"STOCKID","PARTID","PARTMAKE","PARTNAME","CATEGORY","BUYINGPRICE","SELLINGPRICE","QUANTITY"
"1","1","Intel","Core i5-11400F","CPU","4800","5000","10"
"2","3","NVIDIA","RTX 3060 Ti","GPU","11500","12000","5"
"3","6","Seagate","BarraCuda 2TB","Storage-HDD","3300","3500","20"
"4","10","NZXT","H510 Elite","Case","4300","4500","8"

```

### Insert Values into Order Parts Table

To insert values into the table `OrderParts` check out the code block below $\downarrow$:

```SQL

INSERT INTO OrderParts (OrderPID, CustomerID, FirstName, LastName, OrderDate, PartID, PartMake, PartName, Price, PaymentMethod) VALUES 
(1, 1, 'Carlos', 'Sainz', TO_DATE('15-07-2024', 'DD-MM-YYYY'), 1, 'Intel', 'Core i5-11400F', 5000, 'C');

INSERT INTO OrderParts (OrderPID, CustomerID, FirstName, LastName, OrderDate, PartID, PartMake, PartName, Price, PaymentMethod) VALUES 
(2, 3, 'Jane', 'Doe', TO_DATE('15-07-2024', 'DD-MM-YYYY'), 4, 'Corsair', 'Vengeance LPX 16GB', 3000, 'F');

INSERT INTO OrderParts (OrderPID, CustomerID, FirstName, LastName, OrderDate, PartID, PartMake, PartName, Price, PaymentMethod) VALUES 
(3, 4, 'Emily', 'Clark', TO_DATE('15-07-2024', 'DD-MM-YYYY'), 8, 'MSI', 'B450 TOMAHAWK MAX', 4000, 'C');

```

To verify if we have inserted values into `OrderParts` correctly; use the following command:

```SQL

SELECT * FROM OrderParts;

```

You should get the results:

```console

"ORDERPID","CUSTOMERID","FIRSTNAME","LASTNAME","ORDERDATE","PARTID","PARTMAKE","PARTNAME","PRICE","PAYMENTMETHOD"
"1","1","Carlos","Sainz","15-JUL-24","1","Intel","Core i5-11400F","5000","C"
"2","3","Jane","Doe","15-JUL-24","4","Corsair","Vengeance LPX 16GB","3000","F"
"3","4","Emily","Clark","15-JUL-24","8","MSI","B450 TOMAHAWK MAX","4000","C"

```

### Insert Values into Delivery Table

>Finally!!!

```SQL

INSERT INTO Delivery (DeliveryID, CustomerID, FirstName, LastName, Address, MobileNumber, OrderDate, PartID, PartMake, PartName, Price) VALUES 
(1, 2, 'Lewis', 'Hamilton', 'New Moka Road', 53348245, TO_DATE('15-07-2024', 'DD-MM-YYYY'), 3, 'NVIDIA', 'RTX 3060 Ti', 12000);

```

With the command below $\downarrow$, we can check if our data has been entered correctly:

```SQL

SELECT * FROM Delivery;

```

This needs to output:

```console

"DELIVERYID","CUSTOMERID","FIRSTNAME","LASTNAME","ADDRESS","MOBILENUMBER","ORDERDATE","PARTID","PARTMAKE","PARTNAME","PRICE"
"1","2","Lewis","Hamilton","New Moka Road","53348245","15-JUL-24","3","NVIDIA","RTX 3060 Ti","12000"

```

---

# Setting Up Other Users

The other users of this database system will be the:

- Manager ( *`Employee` Table* )
- Sales Representative ( *`Customer` and `ComputerParts` Table* )
- Technician ( *`Service` Table* )
- Cashier ( *`OrderParts` Table* )
- Delivery ( *`Delivery` Table* )

## Manager

The manager of Sun's System will be responsible for managing the `Employee` table.

```console

Username: computer_parts_MANAGER
Password: spare_parts

```

### Create Username and Password ( Manager )

User the `CREATE USER` command again to create the `computer_parts_MANAGER` user.

```SQL

CREATE USER computer_parts_MANAGER IDENTIFIED BY "spare_parts";

```

We can check if the user has been created properly using the command below $\downarrow$:

```SQL

SELECT username, account_status, created FROM dba_users WHERE username = 'COMPUTER_PARTS_MANAGER';

```

You should get the output:

```console

"USERNAME","ACCOUNT_STATUS","CREATED"
"COMPUTER_PARTS_MANAGER","OPEN","16-JUL-24"

```

### Grant Manager Permissions

As this is the Manager of the company; he needs to be able to:

- View
- Insert
- Update
- Delete

Records in the `Employee` table.

>By the way; what I mean by all of these permissions above $\nwarrow$ are that they are [[Database Languages#Data Manipulation Language ( DML ) | Database Manipulation Language ( DML )]] and **not** <span style="color: orange;">DDL</span>!
>What I mean is that they will only *manipulate* the values of their respective tables.
>Read the `NOTE` below $\downarrow$

>[!note]
>Why does the Manager does **not** have permission like `ALTER`, `DROP`?
>As I said we have our main [[Computer - Computer Spare Parts Shop in Oracle 10g#Setting Up the Core System User| user]] `computer_parts` which acts like the Database Administrator for the company.
>
>Hence, if you need to, for example, add another column / attribute to the table `Employee`
>The Manager will go ahead and ask `computer_parts` to do that for him.
>
>>Also, logically speaking; what we are about to it is to **connect** the `Employee` table with is **found** in our *`computer_parts`* user. Hence, if you are going to change the overall **structure** of the table.
>>It make total sense to do that from the main `computer_parts` user ( *who acts as our Database Administrator* )

```SQL

GRANT SELECT ON computer_parts.Employee TO computer_parts_MANAGER;

GRANT INSERT ON computer_parts.Employee TO computer_parts_MANAGER;

GRANT UPDATE ON computer_parts.Employee TO computer_parts_MANAGER;

GRANT DELETE ON computer_parts.Employee TO computer_parts_MANAGER;

```

>[!warning]
>These commands that I just listed above needs to be ran **separately**
>You encounter and error if you do not!

TO verify that our user has been granted these permission; we can use the command below $\downarrow$ to check:

```SQL

SELECT * FROM dba_tab_privs WHERE grantee = 'COMPUTER_PARTS_MANAGER';

```

Here is the output after running the above $\uparrow$ command:

```console

"GRANTEE","OWNER","TABLE_NAME","GRANTOR","PRIVILEGE","GRANTABLE","HIERARCHY"
"COMPUTER_PARTS_MANAGER","COMPUTER_PARTS","EMPLOYEE","COMPUTER_PARTS","DELETE","NO","NO"
"COMPUTER_PARTS_MANAGER","COMPUTER_PARTS","EMPLOYEE","COMPUTER_PARTS","UPDATE","NO","NO"
"COMPUTER_PARTS_MANAGER","COMPUTER_PARTS","EMPLOYEE","COMPUTER_PARTS","INSERT","NO","NO"
"COMPUTER_PARTS_MANAGER","COMPUTER_PARTS","EMPLOYEE","COMPUTER_PARTS","SELECT","NO","NO"

```

>[!warning]
>Everything that we have done so far has been done using the `SYS` / `SYSTEM` account!
>These commands were <span style="color: red;"><strong>not</strong></span> run in the `computer_parts` user.

>[!success]
>And just like that, we have been able to create our user `computer_parts_MANAGER`.
>Let's go ahead and user this newly created account

#### Testing Manager Account

You can now logout of the current `SYS` / `SYSTEM` account and go back to the login screen and enter the following credentials $\swarrow$

```console

Username: computer_parts_MANAGER
Password: spare_parts

```

After that you will be in the `computer_parts_MANAGER` account.

Let's go ahead and make sure that our permissions are working as intended.
Let's try adding a new record in the `Employee` table ( *which is found in `computer_parts` user* )

##### `INSERT` Record into `Employee` Table

To insert a value in a table which you do **not** *own*; use the command below $\downarrow$:

```SQL

INSERT INTO computer_parts.Employee (EmployeeID, FirstName, LastName, Department, DateOfBirth, MobileNumber, Salary)
VALUES (1, 'Michael', 'Johnson', 'Technician', TO_DATE('15-07-1985', 'DD-MM-YYYY'), 51234512, 25000);

```

Verify that our value has been inserted correctly

This is done trough the `SELECT` command but we need to specify that we are fetching the table from the `computer_parts` user.

```SQL

SELECT * FROM computer_parts.Employee WHERE EmployeeID = 1;

```

>Here we also used the `WHERE` command so that it will only show us the record where the `EmployeeID` is equal to '1'

Here is the output after running the above $\uparrow$ command:

```console

"EMPLOYEEID","FIRSTNAME","LASTNAME","DEPARTMENT","DATEOFBIRTH","MOBILENUMBER","SALARY"
"1","Michael","Johnson","Technician","15-JUL-85","51234512","25000"

```

##### `DELETE` Record from `Employee` Table

We are now going to delete that record that we just inserted.
The command and the way we write the `DELETE` command will be the same as we did above $\uparrow$.
Just that we are not going to specify that we are deleting a record found in user `computer_parts`'s `Employee` table.

```SQL

DELETE FROM computer_parts.Employee
WHERE StockID = 1;

```

The output must **not** contains the newly added user:

```console

"EMPLOYEEID","FIRSTNAME","LASTNAME","DEPARTMENT","DATEOFBIRTH","MOBILENUMBER","SALARY"
"10","Eleanor","Wong","Manager","18-JUL-87","54456789","28000"
"11","Liam","Nguyen","Sales Representative","25-APR-93","57788900","30000"
"12","Aria","Liu","Cashier","12-SEP-90","58899001","26000"
"13","Max","Smith","Technician","15-NOV-95","59900123","27000"
"14","Sophia","Garcia","Manager","28-MAR-89","51123456","29000"

```

>[!info]
>Obviously, these command were ran in the `computer_parts_MANAGER` account.

## Sales Representative

The sales representative of the company will have access to the `Customer` and `ComputerParts Table`.

```console

Username: computer_parts_SALES
Password: spare_parts

```

### Create Username and Password ( Sales Representative )

```SQL

CREATE USER computer_parts_SALES IDENTIFIED BY "spare_parts";

```

Verify that our user `computer_parts_SALES` has been created correctly; to achieve this we need to run the command found below $\downarrow$:

```SQL

SELECT username, account_status, created FROM dba_users WHERE username = 'COMPUTER_PARTS_SALES';

```

You should get the output:

```console

"USERNAME","ACCOUNT_STATUS","CREATED"
"COMPUTER_PARTS_SALES","OPEN","16-JUL-24"

```

### Grant Sales Representative Permissions

The Sales Representative needs to be able to:

1. `Customer` Table
	- View
	- Insert
	- Update
	- Delete
2. `ComputerParts` Table
	- View

Hence, we can run the following commands

##### `Customer` Table Permissions

```SQL

GRANT SELECT ON computer_parts.Customer TO computer_parts_SALES;

GRANT INSERT ON computer_parts.Customer TO computer_parts_SALES;

GRANT UPDATE ON computer_parts.Customer TO computer_parts_SALES;

GRANT DELETE ON computer_parts.Customer TO computer_parts_SALES;

```

Verify if the user `computer_parts_SALES` has these permissions mentioned above

```SQL

SELECT * FROM dba_tab_privs WHERE grantee = 'COMPUTER_PARTS_SALES';

```

The output after running the following $\nwarrow$:

```console

"GRANTEE","OWNER","TABLE_NAME","GRANTOR","PRIVILEGE","GRANTABLE","HIERARCHY"
"COMPUTER_PARTS_SALES","COMPUTER_PARTS","CUSTOMER","COMPUTER_PARTS","DELETE","NO","NO"
"COMPUTER_PARTS_SALES","COMPUTER_PARTS","CUSTOMER","COMPUTER_PARTS","UPDATE","NO","NO"
"COMPUTER_PARTS_SALES","COMPUTER_PARTS","CUSTOMER","COMPUTER_PARTS","INSERT","NO","NO"
"COMPUTER_PARTS_SALES","COMPUTER_PARTS","CUSTOMER","COMPUTER_PARTS","SELECT","NO","NO"
"COMPUTER_PARTS_SALES","COMPUTER_PARTS","COMPUTERPARTS","COMPUTER_PARTS","SELECT","NO","NO"

```

##### `ComputerParts` Table Permission

#### Testing Sales Representative Account

##### `Customer` Table Testing

Let's try inserting this test value into our `Customer` table ( *from our `computer_parts_SALES` account* )

```SQL

INSERT INTO computer_parts.Customer (CustomerID, FirstName, LastName, Address, MobileNumber, Gender) VALUES (6, 'Test', 'Mitch', 'Lane', 12345678, 'M');

```

We need to check if the values has been properly inserted:

```SQL

SELECT * FROM computer_parts.Customer WHERE CustomerID = 6;

```

You must get the following output $\downarrow$ after running the above $\uparrow$ command:

```console

"CUSTOMERID","FIRSTNAME","LASTNAME","ADDRESS","MOBILENUMBER","GENDER"
"6","Test","Mitch","Lane","12345678","M"

```

>As you can see from the lovely output; we have inserted this test value.
>
><span style="color: #d827ad;">Let's <em>dEleTe</em> it now</span> ( *that's what a w0m3n would say* )

To delete that value we just inserted. Go ahead and copy that command below:

```SQL

DELETE FROM computer_parts.Customer
WHERE CustomerID = 6;

```

Verify that the value inserted is gone for good!

```console

"CUSTOMERID","FIRSTNAME","LASTNAME","ADDRESS","MOBILENUMBER","GENDER"
"1","Carlos","Sainz","Old Moka Road","52080842","M"
"2","Lewis","Hamilton","New Moka Road","53348245","M"
"3","Jane","Doe","Central Avenue","51234567","F"
"4","Emily","Clark","Bay Street","52345678","F"
"5","John","Smith","Greenwood Lane","53456789","M"

```

>See, no pesky "*Mitch*"

##### `ComputerParts` Table Testing

Select all the values from the table `ComputerParts` from our current user `computer_parts_SALES`

```SQL

GRANT SELECT ON computer_parts.ComputerParts TO computer_parts_SALES;

```

You should get the following output:

```console

"PARTID","PARTMAKE","PARTNAME","CATEGORY","TESTED","PRICE","WARRANTY"
"1","Intel","Core i5-11400F","CPU","N","5000","3"
"2","AMD","Ryzen 7 5800X","CPU","Y","6500","3"
"3","NVIDIA","RTX 3060 Ti","GPU","Y","12000","2"
"4","Corsair","Vengeance LPX 16GB","RAM","Y","3000","5"
"5","Samsung","970 EVO Plus 1TB","Storage-NVMe","N","8000","5"
"6","Seagate","BarraCuda 2TB","Storage-HDD","N","3500","3"
"7","Noctua","NH-D15 CPU Cooler","Fans","Y","2000","2"
"8","MSI","B450 TOMAHAWK MAX","Motherboard","Y","4000","2"
"9","EVGA","SuperNOVA 750 G5","PSU","Y","6000","5"
"10","NZXT","H510 Elite","Case","N","4500","2"

```

## Technician

The technicians of the Company will have access to the table `Service`.

```console

Username: computer_parts_TECH
Password: spare_parts

```

### Create Username and Password ( Technician )

```SQL

SELECT username, account_status, created FROM dba_users WHERE username = 'COMPUTER_PARTS_TECH';

```

Verify that we have created our user:

```console

"USERNAME","ACCOUNT_STATUS","CREATED"
"COMPUTER_PARTS_TECH","OPEN","16-JUL-24"

```

### Grant Technician Permissions

The Technician should be able to:

- View
- Insert
- Update
- Delete

>Not less, not more!!!

You can give the user `computer_parts_TECH` these permission using the following commands below $\downarrow$:

```SQL

GRANT SELECT ON computer_parts.Service TO computer_parts_TECH;

GRANT INSERT ON computer_parts.Service TO computer_parts_TECH;

GRANT UPDATE ON computer_parts.Service TO computer_parts_TECH;

GRANT DELETE ON computer_parts.Service TO computer_parts_TECH;

```

We are now going to verify if we have actually granted these permission; ( *again* ) this is done using the following command:

```SQL

SELECT * FROM dba_tab_privs WHERE grantee = 'COMPUTER_PARTS_TECH';

```

Here are the results:

```console

"GRANTEE","OWNER","TABLE_NAME","GRANTOR","PRIVILEGE","GRANTABLE","HIERARCHY"
"COMPUTER_PARTS_TECH","COMPUTER_PARTS","SERVICE","COMPUTER_PARTS","DELETE","NO","NO"
"COMPUTER_PARTS_TECH","COMPUTER_PARTS","SERVICE","COMPUTER_PARTS","UPDATE","NO","NO"
"COMPUTER_PARTS_TECH","COMPUTER_PARTS","SERVICE","COMPUTER_PARTS","INSERT","NO","NO"
"COMPUTER_PARTS_TECH","COMPUTER_PARTS","SERVICE","COMPUTER_PARTS","SELECT","NO","NO"

```

#### Testing Technician Account

Let's try to update the following value.

>I am going to make the 'Service' for `ServiceID` = '3', from `Build` to `Repair`

```SQL

SELECT * FROM computer_parts.Service WHERE ServiceID = 3;

```

This is the original *values* for the `CustomerID` '3':

```console

"SERVICEID","CUSTOMERID","SERVICE","SERVICEDATE","PRICE"
"3","3","Build","30-JUL-24","900"

```

Updating it

```SQL

UPDATE computer_parts.Service
SET Service = 'Repair'
WHERE ServiceID = 3

```

This should be the **update** results:

```console

"SERVICEID","CUSTOMERID","SERVICE","SERVICEDATE","PRICE"
"3","3","Repair","30-JUL-24","900"

```

## Cashier

The cashier only needs to look and refer to the `OrderParts` table.
Because the Cashier only need to check the amount of money that the order costs.

Hence, we only need to `SELECT` data from our `OrderParts` table.

```console

Username: computer_parts_CASHIER
Password: spare_parts

```

### Create Username and Password ( Cashier )

To create the user, copy the following command below $\downarrow$:

```SQL

CREATE USER computer_parts_CASHIER IDENTIFIED BY "spare_parts";

```

To verify if the user has been created properly, run the command:

```SQL

SELECT username, account_status, created FROM dba_users WHERE username = 'COMPUTER_PARTS_CASHIER';

```

The output will look something like this:

```console

"USERNAME","ACCOUNT_STATUS","CREATED"
"COMPUTER_PARTS_CASHIER","OPEN","16-JUL-24"

```

### Grant Cashier Permissions

>I will be give the cashier most of the permissions that we gave to other users
>Then I will be showing how to remove ( *revoke* ) these permission

```SQL

GRANT SELECT ON computer_parts.OrderParts TO computer_parts_CASHIER;

GRANT INSERT ON computer_parts.OrderParts TO computer_parts_CASHIER;

GRANT UPDATE ON computer_parts.OrderParts TO computer_parts_CASHIER;

GRANT DELETE ON computer_parts.OrderParts TO computer_parts_CASHIER;

GRANT ALTER ON computer_parts.OrderParts TO computer_parts_CASHIER;

```

#### Revoking Permissions

To revoke these permission, study and then copy these commands below $\downarrow$:

```SQL

REVOKE INSERT ON computer_parts.OrderParts FROM computer_parts_CASHIER;

REVOKE UPDATE ON computer_parts.OrderParts FROM computer_parts_CASHIER;

REVOKE DELETE ON computer_parts.OrderParts FROM computer_parts_CASHIER;

REVOKE ALTER ON computer_parts.OrderParts FROM computer_parts_CASHIER;

```

To verify if we have actually one permission given to `computer_parts_CASHIER`

```SQL

SELECT * FROM dba_tab_privs WHERE grantee = 'COMPUTER_PARTS_CASHIER';

```

You should have only 1 permission after running the above $\nwarrow$:

```console

"GRANTEE","OWNER","TABLE_NAME","GRANTOR","PRIVILEGE","GRANTABLE","HIERARCHY"
"COMPUTER_PARTS_CASHIER","COMPUTER_PARTS","ORDERPARTS","COMPUTER_PARTS","SELECT","NO","NO"

```

#### Testing Cashier Account

>Obviously we are going to output the values of `OrderParts` because we only have 1 permission.

```SQL

SELECT * FROM computer_parts.OrderParts;

```

You should get these values $\downarrow$:

```console

"ORDERPID","CUSTOMERID","FIRSTNAME","LASTNAME","ORDERDATE","PARTID","PARTMAKE","PARTNAME","PRICE","PAYMENTMETHOD"
"1","1","Carlos","Sainz","15-JUL-24","1","Intel","Core i5-11400F","5000","C"
"2","3","Jane","Doe","15-JUL-24","4","Corsair","Vengeance LPX 16GB","3000","F"
"3","4","Emily","Clark","15-JUL-24","8","MSI","B450 TOMAHAWK MAX","4000","C"

```

## Delivery

As a delivery person; he or she only needs to **view** information. Hence, the `computer_parts_DELIVERY` user will only need to `SELECT` information from the `Delivery` table which ( *again* ) was created by the user `computer_parts`.

### Create Username and Password ( Delivery )

```SQL

CREATE USER computer_parts_DELIVERY IDENTIFIED BY "spare_parts";

```

To verify if we created `computer_parts_DELIVERY`, run the command $\downarrow$:

```SQL

SELECT username, account_status, created FROM dba_users WHERE username = 'COMPUTER_PARTS_DELIVERY';

```

You should get the output:

```console

"USERNAME","ACCOUNT_STATUS","CREATED"
"COMPUTER_PARTS_DELIVERY","OPEN","16-JUL-24"

```

### Grant Delivery Permission

As you know we only need to give the `SELECT` permission as `computer_parts_DELIVERY` only needs to look at the values of the table `Delivery`

>I should have picked better names like `tblDelivery` but I think `Delivery` look far better than `tblDelivery`
>Hence in this case, I <span style="color: red;"><strong>broke</strong></span> my own rule!
>The rule was "*Functionally over Aesthetics*" ( *crucify me* )

```SQL

GRANT SELECT ON computer_parts.Delivery TO computer_parts_DELIVERY;

```

Verify that we have give this and only this permission to the user:

```SQL

SELECT * FROM dba_tab_privs WHERE grantee = 'COMPUTER_PARTS_DELIVERY';

```

This should output $\swarrow$:

```console

"GRANTEE","OWNER","TABLE_NAME","GRANTOR","PRIVILEGE","GRANTABLE","HIERARCHY"
"COMPUTER_PARTS_DELIVERY","COMPUTER_PARTS","DELIVERY","COMPUTER_PARTS","SELECT","NO","NO"

```

#### Testing Delivery Account

Let's go ahead and select a value(s) from the table `Delivery`

```SQL

SELECT FirstName, LastName, Address, Price, MobileNumber FROM computer_parts.Delivery;

```

This needs to output something like this:

```console

"FIRSTNAME","LASTNAME","ADDRESS","PRICE","MOBILENUMBER"
"Lewis","Hamilton","New Moka Road","12000","53348245"

```

>Here we have selected 5 attributes / columns from the `Delivery` Table.

>[!success]-
>We are finished!

---

# Output List of Users


```SQL

SELECT * FROM dba_users;

```

Here is the output after running the above $\uparrow$ command:

```console

"USERNAME","USER_ID","PASSWORD","ACCOUNT_STATUS","LOCK_DATE","EXPIRY_DATE","DEFAULT_TABLESPACE","TEMPORARY_TABLESPACE","CREATED","PROFILE","INITIAL_RSRC_CONSUMER_GROUP","EXTERNAL_NAME"

"COMPUTER_PARTS_STOCK","40","944A2340AAEA45B5","OPEN","","","SYSTEM","TEMP","16-JUL-24","DEFAULT","DEFAULT_CONSUMER_GROUP",""
"COMPUTER_PARTS_CASHIER","41","C24A3719B3520565","OPEN","","","SYSTEM","TEMP","16-JUL-24","DEFAULT","DEFAULT_CONSUMER_GROUP",""
"COMPUTER_PARTS_MANAGER","45","DD6EAACA2B3956C0","OPEN","","","SYSTEM","TEMP","16-JUL-24","DEFAULT","DEFAULT_CONSUMER_GROUP",""

"AZMAAN","36","6E5461A9AB0148E5","OPEN","","","SYSTEM","TEMP","18-JUN-24","DEFAULT","DEFAULT_CONSUMER_GROUP",""

"COMPUTER_PARTS","39","B8CD090FA9ACF88E","OPEN","","","SYSTEM","TEMP","13-JUL-24","DEFAULT","DEFAULT_CONSUMER_GROUP",""

"JAMES_MAY","38","52FB7B3C27C70EA2","OPEN","","","SYSTEM","TEMP","11-JUL-24","DEFAULT","DEFAULT_CONSUMER_GROUP",""

"COMPUTER_PARTS_DELIVERY","44","2C497C374FB1185D","OPEN","","","SYSTEM","TEMP","16-JUL-24","DEFAULT","DEFAULT_CONSUMER_GROUP",""
"COMPUTER_PARTS_SALES","42","B09034EBEB747A2C","OPEN","","","SYSTEM","TEMP","16-JUL-24","DEFAULT","DEFAULT_CONSUMER_GROUP",""
"COMPUTER_PARTS_TECH","43","2CB8DAF03ED933E7","OPEN","","","SYSTEM","TEMP","16-JUL-24","DEFAULT","DEFAULT_CONSUMER_GROUP",""

"SYS","0","BCD44C40CD4DA320","OPEN","","","SYSTEM","TEMP","07-FEB-06","DEFAULT","SYS_GROUP",""
"SYSTEM","5","D759F2EFA2B34D7F","OPEN","","","SYSTEM","TEMP","07-FEB-06","DEFAULT","SYS_GROUP",""
"ANONYMOUS","28","anonymous","OPEN","","","SYSAUX","TEMP","07-FEB-06","DEFAULT","DEFAULT_CONSUMER_GROUP",""
"MDSYS","32","72979A94BAD2AF80","EXPIRED &amp; LOCKED","07-FEB-06","18-JUN-24","SYSTEM","TEMP","07-FEB-06","DEFAULT","DEFAULT_CONSUMER_GROUP",""
"OUTLN","11","4A3BA55E08595C81","EXPIRED &amp; LOCKED","18-JUN-24","18-JUN-24","SYSTEM","TEMP","07-FEB-06","DEFAULT","DEFAULT_CONSUMER_GROUP",""
"DIP","18","CE4A36B8E06CA59C","EXPIRED &amp; LOCKED","07-FEB-06","","SYSTEM","TEMP","07-FEB-06","DEFAULT","DEFAULT_CONSUMER_GROUP",""
"TSMSYS","20","3DF26A8B17D0F29F","EXPIRED &amp; LOCKED","07-FEB-06","","SYSTEM","TEMP","07-FEB-06","DEFAULT","DEFAULT_CONSUMER_GROUP",""
"FLOWS_FILES","34","364B78B9EABB9E56","EXPIRED &amp; LOCKED","07-FEB-06","18-JUN-24","SYSAUX","TEMP","07-FEB-06","DEFAULT","DEFAULT_CONSUMER_GROUP",""
"CTXSYS","25","D1D21CA56994CAB6","EXPIRED &amp; LOCKED","18-JUN-24","18-JUN-24","SYSAUX","TEMP","07-FEB-06","DEFAULT","DEFAULT_CONSUMER_GROUP",""
"DBSNMP","23","E066D214D5421CCC","EXPIRED &amp; LOCKED","07-FEB-06","","SYSAUX","TEMP","07-FEB-06","DEFAULT","DEFAULT_CONSUMER_GROUP",""
"FLOWS_020100","35","16E4C012E98710D0","EXPIRED &amp; LOCKED","07-FEB-06","18-JUN-24","SYSAUX","TEMP","07-FEB-06","DEFAULT","DEFAULT_CONSUMER_GROUP",""
"XDB","27","E76A6BD999EF9FF1","EXPIRED &amp; LOCKED","07-FEB-06","","SYSAUX","TEMP","07-FEB-06","DEFAULT","DEFAULT_CONSUMER_GROUP",""
"HR","33","4C6D73C3E8B0F0DA","EXPIRED &amp; LOCKED","18-JUN-24","18-JUN-24","USERS","TEMP","07-FEB-06","DEFAULT","DEFAULT_CONSUMER_GROUP",""

```

>I have separated the users that we need / created for viewing sake.

>[!info]
>The command above $\uparrow$ is run on the `SYS` / `SYSTEM` account

---

# Socials

- **Instagram**: https://www.instagram.com/s.sunhaloo
- **YouTube**: https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg
- **GitHub**: https://www.github.com/Sunhaloo

---

S.Sunhaloo
Thank You!