---
Alias: Tutorial 1 Week 1 - Intro to Databases
Tag: uni, db
Module: BCNS1103C / DBT1103C
Author: S.Sunhaloo
Date: 2024-05-08
Status: Completed
---

<p align="center">Introduction to Databases<br>Tutorial 1<br>BCNS1103C / DBT1103C<br>SUNHALOO Shehzaad</p>

<p align="center">University of Technology, Mauritius</p>

---

### My Links

- [[Database Questions - Tutorial 1#Socials | Link to Social]]

---

>[!tip] 1 What do you understand by 'Database Systems'?
>
>A database system is the collection or combination of both the Database Management Software / Package together with the data ( *"raw" data* ).

>[!tip] 2 What is meant by 'Database Management Systems'?
>
>It is the software ( software package ) that is used to **create** and **maintain** computerised databases.
>It also has functions such as *storage*, *sharing of data* and *backups + recovery*.

>[!tip] 3 What is the basic difference between a 'Database System' and 'Database Management System'?
>
>The Database Management System ( DBMS ) is only the software that is used to create and help maintain databases $\Rightarrow$ which are set of related data that is centralised and structured on a computer system; while the Database System consists of both the collection of the raw data ( *facts and figure* ) and the software package.

>[!tip] 4 What is a 'Database'?
>A database consists of related data items that is centralised and structured using computer systems.

>[!tip] 5 Differentiate between 'Centralised' and 'Distributed' databases.
>
>In a **centralised** database, the data is stored in a single location usually in on a desktop computer or mainframe computer. They are normally used in organisations such as *businesses* or *universities*. Nevertheless, they are vulnerable to failure
>
>Compared to **distributed** database, the data is store in multiple locations. It may be stored on multiple computers in the same physical space or over a dispersed interconnected network of computers ( *similar to something like an intranet* ).

>[!tip] 6 What are Homogenous and Heterogeneous databases?
>A *homogeneous* database system in one in which all the devices ( *i.e computers and servers* ) use the same Database Management System ( DBMS ). The data are unified and consistent across all of the devices. In addition, if 1 computer updates the database; it will be automatically updated in all other devices.
>They are used in places like:
>- Enterprise Applications
>- Financial Institutions
>- Healthcare Systems
>- Inventory Management
>
>A *heterogeneous* database system is one which places emphasis on flexibility and caters to diverse requirements. They use different Database Management System ( DBMS ) Softwares and use Schema Mappings ( *related to establishing relationships* ) to ensure that data are exchanged properly.
>They are used in places like:
>- Internet of Things ( IoT ) and Big Data

>[!tip] 7 List the main functions of a Database Management System ( DBMS ).
>- Create and Maintain Computerised Databases
>- Storage, Retrieval and Update Systems
>- Integrity Preservation
>- Security
>	- Authorisation + <ins>Access Control</ins> $\Rightarrow$ Related to *views*
>- Utility Services
>	- Metrics
>	- Garbage Collection system ( *similar to programming; where removes unnecessary data from memory* )
>	- Data Conversions
>- Sharing of Data

>[!tip] 8 What are the main disadvantages of Manual System?
>1. Duplication and Redundancy of Data
>2. Loss of data
>3. Time consuming
>4. Can take a lot of space ( *physical or "software"* )
>5. Cannot easily share data ( *if at all* )
>6. No utility like Data conversion, metrics and graphics

>[!tip] 9 What are the main disadvantages of File Processing Systems?
>1. Difficult to search and retrieve information
>2. Data are not stored in a structured way
>3. No / Limited Backups and Recovery
>4. Data Duplication, Inconsistency and Redundancy

>[!tip] 10 What are the benefits of Database Systems?
>1. No ( *little to no* ) Duplication and Redundancy of data
>	- Consistency
>	- Less storage space required
>1. Search / Query of Data
>2. Backups and Recovery
>3. Templates
>4. Utility Programs like Graphics and Metrics
>5. Sharing of Data

>[!tip] 11 How do you compare the 'Hierarchical' Model with the 'Network' Model? Illustrate your answer with appropriate diagrams.
>A **hierarchical** model instead of organising information in tuples and fields, it organises data in a **tree**-like structure ( *similar something like a subroutine* ). Each **record** has 1 parent record and many children records.
>![[Hierarchical Database Model.png | 400]]
>
>A **network** model is similar to a graph with many connections. Each record can have **multiple** parent and children records.
>![[Network Database Model.png | 400]]
>>NOTE to self: Learn this again!

>[!tip] 12 Describe the 'Three-Tier Architecture' as proposed by the ANSI / SPARC Model. Support your answer with appropriate diagrams.
>It's main objective is to **separate** and provide personalised user's views depending on the requirements
>It has 3 levels / layer of abstraction ( *abstraction $\Rightarrow$ generalising concepts* ) :
>1. External / View Level ( *first* level )
>	- Consists of tailored user views; how user perceive and interact with the data
>	- The irrelevant data are not showed
>2. Conceptual / Logical Level ( *second* level )
>	- Provides unified and abstract view of entire database
>	- Defines the main structure of the database
>	- Normally managed by a Database Administrator
>3. Internal / Physical Level ( *third* level )
>	- Actual physical storage devices like:
>		- Disks, Hard drives
>![[Three-Level Architecture diagram.png | 500]]

>[!tip] 13 Explain fully the term 'Mappings' as applied to the 'Three-Tier Architecture'.
>Refers to the relationships and connections made between the levels ( *i.e external, conceptual and internal* ).
>It defines how the data and functionality flows between these levels.

>[!tip] 14 Explain what is meant by the term 'Data Independence'. What are the 2 types of data independence you know? Briefly explain each of these, supporting your answer with appropriate examples.
>Data independence refers to the data transparency; users do not need to see the details of data and the physical storage system in their tailored ( *external* ) view or application.
>
>1. Logical Data Independence: Refers to ability to change the *logical* / *conceptual* schema or view without the need to rewrite the application.
>	- It ensure that the underlying database structure do not affect how user see and interact with the data
>	- Example: Banking System
>1. Physical Data Independence: Refers to the ability to change the *physical* / *internal* schema without the need to rewrite application
>	- Hide the details of storage configurations from the user
>	- Allow for changes in internal level without requiring the conceptual or external level
>	- Example: Hashing Algorithms, Compression Techniques


>[!tip] 15 Database Languages can be broadly grouped into six main categories. What are these? Briefly describe each of these.
>1. Structured Query Language ( SQL )
>	- Used to manage and manipulate relational database management system ( RDBMS / RDMS *like MS Access* )
>2. Data Definition Language ( DDL )
>	- Use to create and modify databases
>	- Some of its syntax are:
>		- `CREATE`
>		- `ALTER`
>		- `TRUNCATE`
>3. Data Manipulation Language ( DML )
>	- While DDL is used to create and manipulate the actual database
>	- DML will mostly be managing the values inside the database
>		- Updating values inside the database
>		- Deleting values
>		- Inserting values
>4. Data Control Language ( DCL )
>	- Related to security
>	- Gives and Revokes user's permission like:
>		- SELECT
>		- INSERT
>		- UPDATE
>	- Normal syntax / statements
>		- `GRANT`
>		- `REVOKE`
>5. Data Query Language ( DQL )
>	- Simply used to make searches and queries in a database
>	- Statements are like:
>		- `SELECT Name FROM TABLE Customers WHERE Paid = True;`
>			>This should have been on different lines!
>6. Transact-SQL ( T-SQL )
>	- Microsoft's proprietary version of SQL
>	- Includes:
>		- Procedural programming like `IF ... THEN ... ELSE`
>		- Local Variables
>		- String and Data Processing

---

# Socials

- [**Instagram**](https://www.instagram.com/s.sunhaloo/)
- [**YouTube**](https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg)
- [**GitHub**](https://www.github.com/Sunhaloo)

---

S.Sunhaloo
Thank You!
