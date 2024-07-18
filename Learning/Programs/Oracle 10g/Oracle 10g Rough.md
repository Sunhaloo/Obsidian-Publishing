---
Alias: Oracle 10g Plan ( Make good documentation later )
Tag: uni, db, oracle
Author: Date
Date: 2024-07-10
Status: Completed
---

# Comment in SQL

```SQL

-- This is a comment
-- You know what I am thinking...
-- The way you comment things in SQL is similar to LUA!!!

```

# Access other people's Table

Granting permission to other user

>[!warning]
>This command below $\downarrow$ is done in ADMIN / DBA / SYS

```SQL

GRANT SELECT ON user_a.table TO user_b;

```

Accessing

>[!note]
>This command is run on the User that needs access to the table.

```SQL

SELECT * FROM user_a.table

```

---

# Starting Plan of Attack

# Username and Password Related

- Creating users
- Granting permission
- Removing / Revoking permissions
- Listing users
- Deleting users

## Creating a User 

Create user `test1` and `test2`.

```SQL

CREATE USER test1 IDENTIFIED BY "1234";

```

```SQL

CREATE USER test2 IDENTIFIED BY "1234";

```

## Grant the user Permissions

### Types of `GRANT` Privileges

#### System Privileges

This will allow the user to perform specific **actions** within the **database**.

Some of these System Privileges includes:

```SQL

CREATE SESSION
CREATE TABLE
CREATE VIEW
ALTER TABLE
DROP TABLE
SELECT TABLE
INSERT INTO TABLE
UPDATE TABLE
DELETE TABLE

```

#### Object Privileges

Allow the user to perform specific **actions** on specific **objects**.

Some of these includes:

```SQL

SELECT
INSERT
UPDATE
DELETE
ALTER
INDEX
REFERENCES

```

>Then da fuck the difference!
>Need to ask someone about this!

>[!note]
>This is done at the DBA level / `SYS` level.

The command below will give permission to the user test1 to be able to view the table `table_name` **only**!

```SQL

GRANT CONNECT ON table_name TO test1;

```

The command below will give user `test1` the permission to `CREATE TABLE`. You could say that we have given `test1` system privileges.

```SQL

GRANT CREATE TABLE TO test1;

```

The command below will grant *all* permission to user `test1` and `test2`

```SQL

GRANT CONNECT, RESOURCE, UNLIMITED TABLESPACE TO test1;
GRANT CONNECT, RESOURCE, UNLIMITED TABLESPACE TO test2;

```

>[!info]
>So basically we can give a user *all* privileges even make a *simple* user become a DBA if we want to.
>You must know your requirements and with that requirements ask what people need what level of access / privileges.

You can user the command below to `GRANT DBA` to a user.

1. Connect to DBA ( *temporary session for DBA* ) in the *normal user account*

```SQL

CONNECT sys/admin_password AS SYSDBA;

```

>[!bug]
>This does **not** work!!!
>Need to logout and log back into `SYS` and run the other commands

2. The actual command to grant the DBA role

```SQL

GRANT DBA TO test1;

```

3. Verify that we have successfully given *that* user DBA level access / privileges

>[!tip]
>Use the command below to be able to check which people / user have which privileges!

```SQL

SELECT * FROM dba_role_privs WHERE grantee = 'user';

```

4. I do now know if this is required... But we might need to exit *that* **temporary** DBA session and to achieve this we use the command

```SQL

EXIT;

```

$\downarrow$ They are system privileges and roles in Oracle database that grant specific *capabilities* to users.

## Revoke Access from User / Remove access from User

So we know how to give partial or even full DBA privileges... But how can we remove those privileges... This is done using the `REVOKE` command

Now I do **not** want the user `test1` to be able to create tables and stuff. I can achieve this with the commmand:

```SQL

REVOKE RESOURCE FROM test1;

```

---

### What is `CONNECT`?

Allows the user to establish a session with the database.

Allow the user to perform task like **querying data**, but does **not** provide permissions to *create* / *modify* database objects.

Privileges Granted:

```SQL

CREATE SESSION

```

The command above will allow the user to connect to the database.

>[!note]
>After playing with `test1` with only the `RESOURCE` command given... I get no errors even if I run the command `SELECT * FROM table_name`
>>[!info]
>>Hence, I think that the `CONNECT` command is the thing that we were trying to achieve... Like *connect* to **another** table found in *another* user!!!

### What is `RESOURCE`?

Allow the user with the ability to **create** and **manage** certain types of schema objects.

>[!note] What is Schema in Oracle 10g?
>It not only the tables itself... But the overall combination of database objects that are owned by specific users.

Privileges Granted:

```SQL

CREATE TABLE ---> The one that we are going to be using the most
CREATE INDEXTYPE
CREATE OPERATOR
CREATE PROCEDURE
CREATE SEQUENCE
CREATE TRIGGER
CREATE TYPE 

```

>Need to make sure that I find out more about things like `OPERATORS` and the other commands.

>People like developers, managers and stock get this type of access as they need to be able to manipulate the data.

### What is `UNLIMITED TABLSPACE`?

This is typically granted to administrative users or schemas that require the ability to create large amounts of data without being restricted by tablespace quotas.

>[!note] What is a Tablespace Quota?
>It refers to the amount of **disk** space that the user is allowed to user within a specific tablespace.
>>[!note] Then what is Tablespace?
>>It is the *logical storage unit* within an Oracle Database.
>>What is its purpose?
>>- Manage **physical** storage of data
>>- Organise **data** *logically* $\rightarrow$ Are we talking about the Conceptual / Logical ( ANSI-SPARC / Three Tier Architecture - External, Conceptual, Logical / Physical )?
>>- Control **Space** Allocation
>>- Management of different data types.

>Again this is considered to be a high-privilege access.
>Hence, I will only be giving this access to the actual Computer Spare Parts Shop Company "*user*". While the others like Cashier, Technicians and other people will only be able to see data...
>But maybe we need to give some access to Cashier... For example: He / She needs to write data into the Customer Table.
>So we are going to see who needs what by first using our user `test1` and `test2`

>[!tip] Managed By:
>Database Administrator... In our case `SYS` or `SYSTEM`

>[!info]
>If you do not give the user `UNLIMITED TABLESPACE` or whatever the amount in megabytes... it will default to using the *default* tablespace.

#### Components and Structure of Tablespace

1. Datafiles
	- They are physical files on disk that store the database data.
	- When tablespace is create, at least one datafile is create ( *more will be created if need be* )
2. Logical Segregation:
	- When you might have **separate** *tablespaces* for user data, index data and temporary data.
3. Types of Tablespaces:
	- System Tablespace: Contains data dictionary... includes metadata about the structure of database.
	>Its like we are using the `CREATE TABLE` and `DESCRIBE table_name` Commands.
	- Temporary Tablespace: Temporary data storage for **operations** such as *sorting operations* and *temporary tables*
	- Undo Tablespaces: Provide rollback features $\rightarrow$ could be considered as a security feature.

#### Commands to check Tablespace

1. Admin users

```SQL

SELECT owner, segment_name, segment_type, tablespace_name, bytes
FROM dba_segments
WHERE owner = 'TEST1'
ORDER BY tablespace_name, segment_type, segment_name;

```

2. Non-Admin users

```SQL

SELECT owner, segment_name, segment_type, tablespace_name, bytes
FROM all_segments
WHERE owner = 'TEST1'
ORDER BY tablespace_name, segment_type, segment_name;

```


3. Current user's own segment

```SQL

SELECT segment_name, segment_type, tablespace_name, bytes
FROM user_segments
ORDER BY tablespace_name, segment_type, segment_name;

```

>People like Database Administrators get this privilege

>I will need to find someone to actually explain me this... But what I can do right now is run it and analyse the output of it.

---

## Change the username of a user

>[!bug] Warning
>YOU CANNOT DO THAT ( *easily* )

As I said, we cannot just perform / use a command that you can easily **change** the username from `test1` to `james may`
What you need to do is:

1. Create a new user `james may` with its respective password
2. Send all the contents
3. Delete / `DROP` the table in 


To be able to change the username for example `test1` to `james may`... We need the following commands:

```SQL

CREATE USER james_may IDENTIFIED BY password;

```

```SQL

CREATE TABLE james_may.table_name AS SELECT * FROM test1.table_name;

```

>[!tip] Test this command out $\uparrow$

>[!warning]
>The above command will only send 1 table ( *i.e table_name* ) to user `james may`.
>If you have *multiple* tables... You will need to repeat this command multiple times
>>I know this is possible. But right now, we are a beginner and we only kind-of need to know the basics for now... Because we are not going to be actually using this command in Computer Spare Parts Shop Assignment. I will leave you to it to use [ChatGPT](https://chat.openai.com) to find about how you can send multiple / all tables to another user.

```SQL

DROP USER test1 CASCADE; -- CASCADE option drops all objects owned by the user

```

Delete the **entire** *schema* from the database / Oracle10g.

## Change the password of a user

Below $\downarrow$ you will find the command to change the password of a user

>[!warning]
>This command will require DBA *access*... What I mean by that is you cannot directly change the password when logged in as the user `test1`.
>You need to log in as user `SYS` or `system` / `SYSTEM`

```SQL

ALTER USER test1 INDENTIFIED BY new_password;

```

>User the `ALTER` command instead of the `CREATE` command.

### Connect to System Administrator in *normal* user

You can actually *connect* to the DBA while in *normal* user.

```SQL

CONNECT sys/admin_password AS SYSDBA;

```

>[!bug]
>This does **not** work!!!
>You actually need to log-out and log-in into the DBA / `SYS` and then run the command

Then we can directly run the command from the *normal* user:

```SQL

ALTER USER test1 IDENTIFIED BY new_secret_password;

```

>[!warning]
>After using the DBA privileges / commands we need to `EXIT` from the temporary session that we got access to:
>```SQL
>EXIT;
>```

>[!bug]
>Again this is an **invalid** SQL statement

## List All Users

- NO DBA access

If you do **not** have DBA level access / privileges; you can still run this command to be able to *view information about all the users that the current has access to*.

```SQL

SELECT username FROM all_users;

```

This will select usernames from `all_users`

- DBA Access

```SQL

SELECT username FROM dba_users;

```

This I think will select all the usernames from `dba_users` $\Rightarrow$ the list of Database Adminstrators

>NOTE: I ran this $\uparrow$ command and it gave me the same output as `SELECT username FROM all_users;`
>I mean, am I doing something wrong?

>[!warning]
>I need to run this command and find out more!
>>[!note]
>>We call also do things like `ORDER BY` username and stuff. Because from what I can understand; its basically stored as a *table*.

>[!note] Yes Another NOTE
>In the above $\uparrow$, we used commands like `SELECT username FROM all_users`;
>I ran by myself `SELECT * FROM dba_users` or `SELECT * FROM all_users`. There you will be able to see a lot more information like `USER_ID`, `ACCOUNT_STATUS` `TABLESPACE` and more.
>I will be exporting the CSV file $\Rightarrow$ I am currently doing the **testing**!

>[!tip] Difference between `dba_users` and `all_users`
>Technically both of them are the same!
>But its the "*level of access / privilege*" that differs.
>For example if you are **not** a database administrator / `SYS` then you will not be able to use it with `dba_users`
>>Yep! I just ran the command `SELEC * FROM dba_users;` and it gave me `ORA-00942: table or view does not exists`! So I was right all along!

## Delete a user / entire schema

```SQL

-- Drop the user test1
DROP USER test1 CASCADE;

```

This will "*delete*" all the tables, values and the actual user `test1` from database / Oracle10g.

>[!note]
>If you do not add the `CASCADE` options, it will drop the user only if they do not own any objects.

---

# Creating Tables and Table Related Commands

## List All Tables by a User / Account

### User Tables

```SQL

SELECT table_name FROM user_tables;

```

This command $\uparrow$ will list all the tables owned by the current user.

### All Table

```SQL

SELECT owner, table_name FROM all_tables;

```

Now this command will be able to how the tables accessible by the current user, including those *owned* by **another** user.

### DBA Table

List all the table created in the database / Oracle 10g ( *by any user* )

>[!info]
>Require Admin / DBA / `SYS` level access.

```SQL

SELECT owner, table_name FROM dba_tables;

```

>For `all_tables` and `dba_tables` we have added `owner` field because we are going to see *everything*
>When you will run the code you will understand what I am trying to say!

## Creating a Simple Table

What I mean by "*simple*" table is that we do not have things like **primary key**, **default values** and `NOT NULL`.
Now you might be saying that what the actual fuck! How can you create a table without a primary key... Yes! yes you can create a table without adding those features!

The command below $\downarrow$ will allow you to create a simple table called `Persons`

```SQL

-- No primary key, No defaults, No constraints / checks and No NOT NULLs
CREATE TABLE Persons (
	Name VARCHAR(30),
	LastName VARCHAR(30)
);

```

## Change a Column / Attribute / Field in a Table

```SQL

-- No primary key, No defaults, No constraints / checks and No NOT NULLs
CREATE TABLE Persons (
	Name VARCHAR(30),
	LastName VARCHAR(30)
);

```

So we have already created our table right; we have `Name` and `LastName`. But now I want to change the field `Name` to `Names`. How can we do that?

This is the command `ALTER` template to be able to rename a field / column ... I think you get the FUCKING POINT.

```SQL

ALTER TABLE table_name RENAME COLUMN old_column_name TO new_column_name;

```

Hence in our case `Name` $\rightarrow$ `Names`

```SQL

ALTER TABLE Persons RENAME COLUMN Name TO Names;

```

>[!tip] NOTE
>During the testing phase I did like:
>- Create the Table
>- Run the command `ALTER TABLE ... RENAME ...`
>
>I actually did:
>- Create Table
>- Run the command `INSERT INTO Persons (Name, LastName) VALUES ('Fucking', 'Dick')`
>- Then I ran the command `ALTER TABLE WHATEVER!...`
>
>This is so that I can check if something happens to the values.
>>[!success] Result
>>I did work and did not mess up with the values *Obviously... It would have been a fucking shitty problem if it would change*!

## Add another Column to an Existing Table

>My guess is we are going to be using the `ALTER` Command.

```SQL

ALTER TABLE table_name ADD (column_name data_type);

```

>What the fuck did I say! Huh, huh; I am a fucking shitty GOAT! The GOAT they say... *The GOAT!*

In our case I want to add the column / ( *I think you get the point* ) `age` to our table `Person`.

>Wait a second, lemme go ahead and git push this note

Yes, its going to be:

```SQL

ALTER TABLE Persons ADD (age NUMBER(2));

```

In this case, we are adding the column `age` with the datatype `NUMBER(3)` where `(2)` is the maximum characters we can add into that field ( *I must this is really basic... I am sure you get what I am trying to say... Because I can't fucking say / explain is properly* ).

>[!warning]
>If you do not add a "*Length*" to the `NUMBER` DataType; it would be unrestricted **precision** and **scale** and you would be able to do shit like this:
>```SQL
>
>-- Inserting values
>INSERT INTO Persons (Name, LastName, age) VALUES ('John', 'Doe', 30);
INSERT INTO Persons (Name, LastName, age) VALUES ('Jane', 'Smith', 25.5); -- Age normally is not 25.5
>
>```

### Updating the Existing Row of Values

Now, we have created that field `age`; but our row `Fucking Dick` does not have a value, how can we add an `age` for `Fucking Dick`

>I you do not know where `Fucking Dick` came from refer to `SQL_Testing ( Tables ).txt` ( *or .md* ) if I change it later. So that I can add a folder in this vault.

Do do that we need to use the `UPDATE` command; run the following command below

```SQL

UPDATE Persons
SET age = 20
WHERE Names = 'Fucking' AND LastName = 'Dick';

```

Hence the boilerplate / template becomes:

```SQL
UPDATE table_name
-- Our new columns
SET column1 = value1,
    column2 = value2,
    ...
-- Our old columns
WHERE condition;

```

>[!note]
>I did not actually ran the command:
>```SQL
>
>UPDATE Persons
>SET age = 20
>WHERE Names = 'Fucking' AND LastName = 'Dick';
>
>```
>I ran:
>```SQL
>
>UPDATE Persons
>SET age = 20
>WHERE LastName = 'Dick';
>
>```
>>[!warning]
>>This is **possible** but that does not mean its *good*
>>Because here we need to run the command that I did **not** run because we do **not** have a *primary key*!
>>Hence, the way that I did work but **not good** ( *I know there is a better word for that* ).

## Change the `LENGTH` of Column / Attribute / Field

Now we have created our table `Persons` change the field `Name` $\rightarrow$ `Names`. We have even added another column / field `age`. In addition, we did update the row `Fucking Dick` and provided him with an age.

Now I want to change the **length** of the column `Names` from `30` to `50`. This can be done by using the command below $\downarrow$:

```SQL

ALTER TABLE table_name
MODIFY column1 data_type(new_length);

```

Hence, in our case... the command will be like so:

```SQL

ALTER TABLE Persons
MODIFY Names VARCHAR(50);

```

>[!info]
>BTW if you want to change length of many columns... You cannot do that... you need to run each of the commands individually.
>What I mean by that is that you need to run the above $\uparrow$ command **separately** for each of the columns / fields you want to update ( *more like `ALTER`* ) 

## Removing a Column / Field / Attribute from a Table

```SQL

ALTER TABLE table_name
DROP COLUMN col_name;

```

Using this exact command, you can thus remove a field / column from the table `table_name`.

>I am going to remove the column `age` from the table `Persons`

## Create Another Table with Primary Key

>[!warning]
>I need to start moving quicker now!
>Because else I am going to get fucked while doing the programming assignment and I will have to cram

Let's now go ahead an create a table called `Cars` what will have the following column / attribute / fields

- Car_ID $\leftarrow$ our Primary Key ( *which is `NOT NULL`* )
- Person_ID ( $\Rightarrow$ which will be added to our table `Persons` | need to know *how to do that* )
- LastName ( again from our table `Persons` )
- Make
- Model

>Again, need to go check `SQL_Testing ( Tables ).txt` in the private repo `University/SQL_Assignment2`
>>[!warning]
>>At this point in time ( 12/07/2024 @ 15:56:48 ) The folder structure might be like this.
>>But as I am very fucking ADHD type person... I might be changing it in the future.
>Writing this $\uparrow$ because this is not my main vault and I do not care if things are not going to be updated.

### Add the Primary Key to table `Persons`

>[!warning]
>This is so fucking difficult...

```SQL

-- Add the column without NOT NULL constraint
ALTER TABLE table_name
ADD (column_name NUMBER);

-- Create a sequence to generate unique values
CREATE SEQUENCE sequence_name START WITH 1 INCREMENT BY 1;

-- Update existing rows with unique values
UPDATE table_name
SET column_name = sequence_name.NEXTVAL;

-- Set the column to NOT NULL
ALTER TABLE table_name
MODIFY (column_name NUMBER NOT NULL);

-- Add the primary key constraint
ALTER TABLE table_name
ADD CONSTRAINT pk_table_name PRIMARY KEY (column_name);

```

#### Explanation

```SQL

-- Create a sequence to generate unique values
CREATE SEQUENCE sequence_name START WITH 1 INCREMENT BY 1;

```

So currently our table has a record. When we are going to create the attribute / column `PersonID`, its going to be **empty**. Hence, we cannot simply add `1` to it.

We need to create a **_sequence_** that will do if for us and the *sequence* will be incrementing by 1 each time we add a value to the table `Persons`

```SQL

-- Update existing rows with unique values
UPDATE table_name
SET column_name = sequence_name.NEXTVAL;

```

For each row, we need to used the value created by our *sequence* and update the field `column_name` with it... *I think this is the command that will actually populate the values into the field which is our primary key*.

Hence in our case we need to do all of this:

```SQL

-- Add the column without NOT NULL constraint
ALTER TABLE Persons
ADD (PersonID NUMBER);

-- Create a sequence to generate unique values
CREATE SEQUENCE SEQ_PERSONID START WITH 1 INCREMENT BY 1;

-- Update existing rows with unique values
UPDATE Persons
SET PersonID = SEQ_PERSONID.NEXTVAL;

-- Set the column to NOT NULL
ALTER TABLE Persons
MODIFY (PersonID NUMBER NOT NULL);

-- Add the primary key constraint
ALTER TABLE Persons
ADD CONSTRAINT pk_person PRIMARY KEY (PersonID);

```

>All of these commands work $\uparrow$ I checked!

>[!tip] Just don't forget to add your primary key!

---

>Actually Creating the table `Cars`

- Create the table `Cars`

```SQL

-- Create the Cars table with NOT NULL constraint for Car_ID
CREATE TABLE Cars (
    CarID NUMBER NOT NULL PRIMARY KEY,
    Person_ID NUMBER,
    LastName VARCHAR2(30),
    Make VARCHAR2(30),
    Model VARCHAR2(30)
);

```

### Add Foreign Key

We are now going to take the **Primary Key** of table `Persons` and place it into table `Cars`.
Hence, `PersonID` will become a **Foreign Key** in the table `Cars`

>This is the boilerplate to add a **Foreign Key** to a table

```SQL

ALTER TABLE table_name
ADD CONSTRAINT foreign_key_name
FOREIGN KEY (foreign_key_column)
REFERENCES referenced_table(referenced_column);

```

>An actual example for example sake ( *I know my English is fucked up*! )

```SQL

-- Add the foreign key constraint
ALTER TABLE Cars
ADD CONSTRAINT fk_person
FOREIGN KEY (Person_ID)
REFERENCES Persons(PersonID);

```

>[!info]
>What I am trying to say is that we have a separate code for adding foreign keys!

Now I have another question... We have:

- Created the `Persons` Table
	- Inserted data into table `Persons`
	- Added a Primary Key / Column in table `Persons`
- Created the `Cars` Table
	- Linked the Primary Key from table `Person` to become / be a Foreign Key in `Cars` table.

But what about auto-population? Like for example in MS Access when you populate / insert values for example in `Customers` table and then you say that `CustomerID` becomes a foreign key in `Orders` table.
When you use combo boxes and other methods, you can see the data that has been added to the `Customers` table to `Orders` table.
I know it currently does not make any-sense, but in my head it does.

What I am trying to say that:

When we created the foreign key `PersonID`, we also have the column `LastName` in our table `Cars`. But do I need to actually each and every time check the `Persons` table and then input the data... Like there is not automation. I want the `LastName` attribute to be auto-populate...
Or is this not *good practice* in this case? Because we actually need to create each new `CarsID`?

![[Pasted image 20240712214440.png]]

So you are telling me that this is *not* really possible in a *non-relational* based database?

But it gave me way to do... But I am not going to cover them right now... because as I said I need to move fast

>Its currently 21:45:53 in the night and because I am stressed out; I am going to work till maybe 00:30

Here are some ways we can try to emulate that:

1. Database Triggers
2. Join Queries for Reporting
3. Views

![[Pasted image 20240712214728.png]]

Wait a fucking second... I think this is what I wanted...

>見てください $\leftarrow$ say that like Mr Tominaga said this in Midnight Wangan.

```SQL

-- Insert a value into Person's table
INSERT INTO Persons (PersonID, Name, LastName) VALUES (1, 'James', 'Bond');

-- Inserting into Cars (LastName will be auto-populated by the trigger) <-- I have my doubts about this... I do not think that this line of code will work!
INSERT INTO Cars (CarID, PersonID, Make, Model) VALUES (1, 1, 'Aston Martin', 'DB5');

-- Verify everthing
SELECT * FROM CarsView;

```

>Let me run these commands and report about it!
>>[!warning]
>>I does work... **BUT** you need the trigger for it to "*auto-populate*" the `LastName` column / field.
>>Because, when I ran the command... I did not insert any value at `LastName`.

>But how am I suppose to do the assignment "*correctly*"!
>There is going to be a lot of data redundancy and inconsistencies if you are not going to use these method ( *like trigger, views* ) above $\uparrow$

## Delete a Specific Value from A Row

To remove a value, use the template below $\downarrow$:

```SQL

UPDATE table_name
SET col_name1 = NULL
WHERE col_name1 = 'value at col_name1';

```

If you prefer to use *empty string* instead of `NULL`

```SQL

UPDATE table_name
SET col_name1 = ''
WHERE col_name1 = 'value at col_name1';

```

### Example: Delete Specific Value

```SQL

UPDATE Cars
SET Make = NULL
WHERE Make = 'Aston Martin';

```

>I am going to be using `NULL` as I am *entirely* **remove** the value `Aston Martin`

## Delete ENTIRE Record

Here is a simple template:

```SQL

DELETE FROM example_table
WHERE column1 = 'value1' AND column2 = 'value2';

```

### Example: Delete ENTIRE Record

```SQL

DELETE FROM Cars
WHERE CarID = 1;

```

As you can see, I did not used something like:

```SQL

DELETE FROM Cars
WHERE Make = 'Aston Martin' AND Model = 'DB5';

```

This is because:

1. I do not have the value `Aston Martin`
2. I already have a key identifier `CarID`

>If you have been following the `SQL_Testing ( Tables ).txt`; then you know what I am talking about!
>I think I will be placing this note in a folder called Oracle10g learning something like that and I will be converting the `.txt` file into `.md` file so that Obsidian can read it.

>[!info]
>I am going to start the actual assignment I think... current 22:51:13 on 12/07/2024