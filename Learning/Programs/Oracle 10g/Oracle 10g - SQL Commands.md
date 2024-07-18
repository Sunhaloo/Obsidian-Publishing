---
Alias: SQL Commands for Oracle 10g ( kinda a documentaion )
Tag: uni, db, oracle
Module: BCNS1103C / DBT1103C
Author: S.Sunhaloo
Date: 2024-07-16
Status: In-Progress
---

## List of Contents

- [[Oracle 10g - SQL Commands#List Users in Database System | List Users in Database System]]
- [[Oracle 10g - SQL Commands#Creating Users | Creating Users]]
	- [[Oracle 10g - SQL Commands#Verify Creation of User | Verify Creation of User]]
	- [[Oracle 10g - SQL Commands#Change Username of User | Change Username of User]]
	- [[Oracle 10g - SQL Commands#Change Password of User | Change Password of User]]
	- [[Oracle 10g - SQL Commands#Delete a User from Database System | Delete a User]]
- [[Oracle 10g - SQL Commands#Grant Permissions to User | Grant Permissions to User]]
	- [[Oracle 10g - SQL Commands#Types of Privileges in Oracle 10g | Types of Privileges]]
	- [[Oracle 10g - SQL Commands#Grant System Privileges | Grant System Privileges]]
	- [[Oracle 10g - SQL Commands#Grant Object Privileges | Grant Object Privileges]]
		- [[Oracle 10g - SQL Commands#Access Another Table From Another User | Access Another Table From Another User]]
	- [[Oracle 10g - SQL Commands#Granting Other Permissions | Granting Other Permissions]]
	- [[Oracle 10g - SQL Commands#Verify Granted Privileges of User | Verification of Granted Permissions]]
		- [[Oracle 10g - SQL Commands#Verify System Privileges | Verify System Privileges]]
		- [[Oracle 10g - SQL Commands#Verify Object Privileges | Verify Object Privileges]]
- [[Oracle 10g - SQL Commands#Tables | Tables]]
	- [[Oracle 10g - SQL Commands#Creating Tables | Creating Tables]]

---

### My Links

- [[Oracle 10g - SQL Commands#Socials | Link to Socials]]

---

>[!note]
>The Oracle 10g is **Web-Based** application.
>It runs on a local host ( something like https://127.0.0.1/... )
>>What I mean by that is that its **not** Command-Line ( CLI ) based


## List Users in Database System

```SQL
SELECT * FROM dba_users;
```

>[!note]
>This command will require [[Database Administrator]] privileges ( *i.e must be in `SYS` / `SYSTEM` to be able to use it* )
>The **scope** of this command is *Database-Wide*
>The table `dba_users` will contains information about **all** users in the database system.

```SQL
SELECT * FROM all_users;
```

>[!note]
>This command does **not** require any DBA privileges; thus, it can be used by any user.
>The **scope** of this command is *Schema-Wide*
>The table `all_users` contains information about **all** users that is visible to the <span style="color: orange;">current</span> user.

>When you are going to run the commands above $\uparrow$ and compare them; You will see that the **first** command ( *the one that needs DBA access* ) will provide **more** information.

# Creating Users

```SQL
CREATE USER username IDENTIFIED BY "passwd";
```

## Verify Creation of User

```SQL
SELECT * FROM dba_users WHERE username = 'USERNAME';
```

>[!warning]
>The commands above is can only be run the the `SYS` / `SYSTEM` Database Administrator account.
>In addition, we need to type `USERNAME` instead of `username` because Oracle 10g applies like a [[String Manipulation - Python#Upper Function | .upper()]] function to it.

```SQL
SELECT * FROM all_users WHERE username = 'USERNAME';
```

>[!info]
>If you are not the `SYS` / `SYSTEM` account; you can use this command to be able to check what users are *connected* to your current account
>
>>We are going to see how to link tables ( *and other stuff* ) from one account to another later on.

## Change Username of User

>[!warning]
>This cannot be done directly in Oracle 10g.
>The way we do that is **not** straight-forward.

### Steps to Change Username

1. Create a new user with the desired username

```SQL
CREATE USER new_username IDENTIFIED BY "passwd";
```

>[!note]-
>Again, don't change the password of the user as we are **only** changing the *username*.

2. Transfer all the data items to the newly created user.

This command below $\downarrow$ will show you how to **transfer** the contents of a table to another user.

>[!warning]
>When you use that command; you get the option to **change** the *name* of the table.
>As I have been saying; we are **only** changing the *username* of the user.
>Hence, everything still needs to be the same!
>>But I will still show you how you can use the **same** command to *create* that table with a different *table name*!

```SQL
CREATE TABLE new_username.table_name AS SELECT * FROM original_username.table_name;
```

>[!tip] Change the name of Table
>
>>I told you that I will be showing you!
>
>```SQL
>CREATE TABLE new_username.any_table_name AS SELECT * FROM original_username.table_name;
>```
>Hence, in this case we can see that the original table name was `table_name` and when transferring the contents; we transferred it to a table ( *which BTW has just been created when you run the command* ) called `any_table_name`

3. Delete the Original User

>[!warning]-
>This will *delete* **everything**!

```SQL
DROP USER original_username CASCADE;
```

>The `CASCADE` option makes it so that it delete everything and does **not** left anything behind.

---

General Steps:

1. Create a new user with the desired username
	>As we are only changing the username, let the password be the same!
2. Grant the user all the same permissions as our original user.
3. Transfer the "*schema*" ( *tables, permissions, everything* ) to the newly created user
4. Delete the original user.

>Now you can also <span style="color: green;">verify</span> that the users have been **created** and **deleted** correctly again by using the command [[Oracle 10g - SQL Commands#List Users in Database System | above]].

---

## Change Password of User

To change the password of a user; we can simply run the command $\swarrow$:

```SQL
ALTER USER username IDENTIFIED BY "new_passwd";
```

>In this case, our new password for the user `username` will become `new_passwd`

## Delete a User from Database System

We have already used this command when we were learning about how to [[Oracle 10g - SQL Commands#Change Username of User | change the username]] of a user.

>But here is the command again $\swarrow$

```SQL
DROP USER username CASCADE;
```

---

# Grant Permissions to User

## Types of Privileges in Oracle 10g

### System Privileges

These *system* privileges allow the user to perform specific actions within the database.

- They are *Database-Wide*
- They offer users permissions what allows them to performs actions at the **database** level

Some of these System Privileges ( *commands* ) includes:

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

### Object Privileges

These *privileges* will allow the user to perform actions on specific **objects**

- They are *Schema-Based*
- They offer users permissions that allow users to perform actions on specific **schema** objects

Some of the Object Privileges ( *commands* ) includes:

```SQL
SELECT
INSERT
UPDATE
DELETE
ALTER
INDEX
REFERENCES
```

## Grant System Privileges

Let's give a user some system privileges and then we explain what each of them do.

```SQL
GRANT CONNECT, RESOURCE, UNLIMITED TABLESPACE TO username;
```

### `CONNECT`

What is `CONNECT`?

This permission allows the user to establish a session with the database.
This privilege does **not** do anything except to **establish** a connection to the database.

>[!info]
>The `CONNECT` privilege is a very basic privilege that does **not** grant the user any additional privileges like `SELECT`, `INSERT` and so on.
>
>>[!note]
>>This does **not** mean that if you do not grant the user `CONNECT`; he will not be able to even login to the Oracle 10g
>>><span style="color: #91f00f;">He will still be able to login even if he does <strong>not</strong> have <code>CONNECT</code> privileges</span>

Remember that we used the command:

```SQL
SELECT * FROM all_users;
```

Hence, if you for example grant the user `user_1` the `CONNECT` privilege and then go to `user_2` and run the above $\uparrow$ command.
You will see that you will be able to see `user_1` in the table `all_users`.

### `RESOURCE`

>[!info]-
>Before we start, we have not asked ourselves this question; "*What is a Schema?*"
>Ahhh! A schema is **not** only the tables themselves... But the **overall** combination of database objects that are owned by specific users.
>
>You could say "*the database system as a whole*"!

What is the `RESOURCE` privilege?

The privilege allow the user with the ability to create and manage certain types of *schema* $\uparrow$ objects.

They allow the user to create things like *tables*, *indexes* and *clusters*

>[info] In Short!
>It is a system privilege that allows the user to **create** and **manage** schema objects, but <span style="color: orange;"><strong>within</strong> the user's own schema</span>

### `TABLESPACE`

#### What is a Tablespace?

>Why am I giving this one its own header?
>Because I did not understand a single thing when I was learning it... Now I know more about it.
>Hence, I am giving it my all!
>I used [Ollama](https://ollama.com/) with the [codellama](https://ollama.com/library/codellama) model to get these answer!

>[!tip] 10 Year old Explanation
>A *tablespace* is like a big **storage** where all of the data for the database is kept
>Think of it like a *folder* on your computer where all the database files are stored.

>[!tip] Computer Person Definition
>It is the *logical storage unit* within an Oracle Database.
>A tablespace is used to manage the storage of data for 1 or more tables / indexes.

Each *table* in a database can have its **own** *tablespace* which means that each table can have its own storage **location** and **size**!
This allows one to organise data into different groups or categories based on your needs.

There are many benefits to you using tablespaces; they are:

- Organisation
- Scalability
- Security
- Backup and Recovery

>I also made a *rough* note on Oracle 10g, you can find it here $\Rightarrow$ [[Oracle 10g Rough]]
>What is the point of the rough? It was a rough plan for me to learn Oracle and then be able to make this *documentation*
>Hence, long story short, they are also something that might peek your interest!

>[!info]
>Go up and check the command that I showed you...
>You can see that we granted the user `UNLIMITED TABLESPACE`.
>This means that the user `username` will have no limit to the *logical storage space*.
>But we can also give it a *set* storage space in **Megabytes**

## Grant Object Privileges

These are the ones that actually interest us the most and I will be also showing you how to get access to **another** user's *table*!

As I said; object privileges commands includes:

```SQL
SELECT
INSERT
UPDATE
DELETE
ALTER
INDEX
REFERENCES
```

>[!warning]
>I will **not** be showing you any of them right now!
>*You fucking bastard!* Yes, I know I lied... But we are going to learn more about them later on!
>When we are actually going to use them.
>>Besides you have already been using some of them!

### Access Another Table From Another User

>Let's get started!

We have 2 users, namely `user_a` and `user_b`.
`user_a` is a user that has been in the database system for a long time. Hence, he has all of the tables and clusters and whatever else he has.
Now, a new kid has just arrived on the block; `user_b`. `user_b` is a mastermind... Hence, he as been called to help `user_a` ( *similar to my case with me and my DB lecturer* ) out!

But how can he do that when we do **not** have any of those tables and we <span style="color: red;">don't</span> want to use the command:

```SQL
CREATE TABLE user_b.table_name AS SELECT * FROM user_a.table_name;
```

Here comes the other command!!!

>Check this out $\downarrow$

```SQL
GRANT SELECT ON user_a.table TO user_b;
```

>[!warning]
>The above $\uparrow$ is run the `SYS` / `SYSTEM` account!

This will grant the user to be able to use the `SELECT` command on the table `table` which is found in `user_a` "*tablespace*"

#### Verify if that is the case

Now, we have granted the permission to be able to `SELECT` value from `table`.
The *new kid on the block* can now run the following command $\downarrow$

```SQL
SELECT * FROM user_a.table;
```

>This should run perfectly find and then the values will be displayed on the **results** tab.

#### Granting Other Permissions

Now what if the user `user_b` wants to do things like:

- Insert values into that `table`
- Remove values
- Update values
- Alter the table 
	- create another column
	- change the primary key
	- create constraints ( *we will get to that later on!* )

The code block below will include most of these commands:

```SQL
GRANT SELECT ON user_a.table TO user_b;
GRANT INSERT ON user_a.table TO user_b;
GRANT UPDATE ON user_a.table TO user_b;
GRANT DELETE ON user_a.table TO user_b;
GRANT ALTER ON user_a.table TO user_b;
```

Hence, the `user_b` will be able to do stuff like this:

```SQL
SELECT col1, col2, col100 FROM user_a.table;

INSERT INTO (col1, col2, col3) VALUES (1, "test", TO_DATE('25-04-1993', 'DD-MM-YYYY')) user_a.table;

UPDATE table
SET col1 = 2
WHERE ID = 1;

ALTER TABLE table MODIFY (
	col2 VARCHAR(30) DEFAULT "test"
);

```

>I mean we can pretty much do anything once we have been granted the *right* permissions.
>Hence, I have showed you how to actually "*connect*" to another user's tables and thus, we move on!

## Verify Granted Privileges of User

### Verify System Privileges

As you know by now, the System Privileges are `CONNECT`, `RESOURCE` and `TABLSPACE`.
To check the user has been given privileges, we can use the following command:

```SQL
SELECT * FROM dba_role_privs WHERE grantee = 'USERNAME';
```

>[!warning]
>This command that I just showed you need to be run in the `SYS` / `SYSTEM` account as it requires DBA Privileges!

#### Verify Tablespace

Similar to things like `dba_users` and `all_users`; we have both, thus we can run both in `SYS` and also run `all_users` in just like a normal user.
For this one we also have this; where one command can only be run in the Database Administrator and the other can be run in the current / normal user.

>BTW, the `SYS` / `SYSTEM` account can run both DBA *privileged* commands and *normal* commands... *Obviously*.

1. `SYS` / `SYSTEM` / Database Administrator Privileges Required

```SQL
SELECT owner, segment_name, segment_type, tablespace_name, bytes FROM dba_segments
WHERE owner = 'USERNAME'
ORDER BY tablespace_name, segment_type, segment_name;
```

2. Non-Admin Users

```SQL
SELECT owner, segment_name, segment_type, tablespace_name, bytes FROM all_segments
WHERE owner = 'USERNAME'
ORDER BY tablespace_name, segment_type, segment_name;
```

3. Current User's own Tablespace Segment

```SQL
SELECT owner, segment_name, segment_type, tablespace_name, bytes FROM user_segments
WHERE owner = 'USERNAME'
ORDER BY tablespace_name, segment_type, segment_name;
```

>[!tip]-
>"<span style="color: green;"><em>Don't Worry!!!</em></span>" ( *that's what she said* ).
>You will **not** really be using these commands as a beginner. Because if you are like me, you might be saying to yourself "*what the hell is all of this?*"
>Again "*Don't Worry*", for the moment just know that you can run check these commands and then what you can do right now is run these commands an see of yourself!

### Verify Object Privileges

To verify our Object Privileges like `SELECT` , `INSERT` and the others... We can use the command found below $\downarrow$:

```SQL
SELECT * FROM dba_tab_privs WHERE grantee = 'USERNAME';
```

---

# Tables

>Let's get back to basics!

>[!tip] What is a Table?
>A table is a structured collection of data organised into records ( *rows* ) and tuples ( *columns* ).
>A table typically consists of the following components:
>1. Keys like:
>	- Primary Key
>	- Foreign Key
>2. Indexes
>3. Constraints
>4. Triggers
>5. Views
>6. Stored Procedures

## Creating Tables

To create a simple table ( *no primary key etc* ), study and use the command below $\downarrow$ as a *template*:

```SQL
CREATE TABLE table_name (
	col1 Datatype,
	col2 Datatype
);
```

The above command with create a table with the identifier name `table_name`; and in this table we are going to have 2 tuples / columns namely `col1` and `col2`.
Be careful with `Datatype`! As this was a *template*; I did not bother adding the actual datatypes.

### Datatype in Oracle 10g

The main datatypes that are found in Oracle10g are ( *in no particular order* ) as follows:

1. `NUMBER`
2. `VARCHAR` or `VARCHAR2`
3. `DATE`
4. `TIMESTAMP`
5. `INTERVAL`

>There are more datatypes like `CLOB` and stuff; but we are going to be mainly using the ones that I just mentioned above $\uparrow$

>[!note]
>Data Types such as `NUMBER` and `DATE` have default **size**!
>Meaning I do not need to do:
>```SQL
>NUMBER(100)
>```
>You are going to understand more about them later on

## Simple to Interesting Creation of Tables

>These are actual examples and not template!

### Name and Last Name Example

Create a simple and short table; where we can input a user's first and last name.

```SQL
CREATE TABLE User (
	Name VARCHAR(50),
	LastName VARCHAR(50)
);
```

Here $\uparrow$, we have a table with the identifier name `User`. This `User` table has 2 column, namely `Name` and `LastName`.
Here this simple table does not have any complicated things like **Primary Key**, **Foreign Key** also stuff like **Constraints**, **Default** values.

This should be the visual representation of the above `User` table:

| Name | LastName |
| ---- | -------- |

#### Create the same `User` Table with Primary Key

Okay, we are going to take the above table ( *SQL Command* ) and we are going to a **Primary Key** `UserID` to it.
Now, there are 2 ways we can approach this, lets's check them out, shall we?

##### Method 1: During Creation of Table

>This one is pretty simple!

```SQL
CREATE TABLE User (
	UserID NUMBER PRIMARY KEY NOT NULL,
	Name VARCHAR(50),
	LastName VARCHAR(50)
);
```

>Let me explain this to you before I show you the other method!

So again, we have our column `Name` and `LastName`. But now we also have another column ( *which is going to be at the start of our table* ) called `UserID`; which will be our unique record identifier $\Rightarrow$ **Primary Key** for our `User` table.
We have also added a simple *constraint* which is $\rightarrow$ `NOT NULL`. This *constraint* will specify that the user <span style="color: orange;"><strong>needs</strong></span> enter a value for that column.

This is what the table looks like currently:

| UserID | Name | LastName |
| ------ | ---- | -------- |

##### Method 2: Adding the Primary Key After Creation of Table

```SQL
CREATE TABLE User (
	UserID NUMBER PRIMARY KEY NOT NULL,
	Name VARCHAR(50),
	LastName VARCHAR(50)
);
```

So what if we have already run the above $\uparrow$ command? and we have already added many *records* in `User`.

>We can try `ALTER`ing the table `User`!

--

# Socials

- **Instagram**: https://www.instagram.com/s.sunhaloo
- **YouTube**: https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg
- **GitHub**: https://www.github.com/Sunhaloo

---

S.Sunhaloo
Thank You!