---
Alias: Database Systems ( Semester 1 Labsheet 1 ) - Week 2 
Tag: uni, db, lab
Module: ICDT 1202Y
Author: S.Sunhaloo
Date: 2024-08-07
Status: Completed
---

## List of Contents

- [[Database Systems - Labsheet 1#Create Database | Create the Database]]
- [[Database Systems - Labsheet 1#Create Tables | Create the Tables]]
- [[Database Systems - Labsheet 1#Add Another Column to Table Property for Rent | Add another Column to Table]]

---

### My Links

- [[Database Systems - Labsheet 1#Socials | Link to Socials]]

---

# Create Database

```SQL
-- create database 'Dreamhome'
CREATE DATABASE Dreamhome;
```

# Create Tables

## Branch Table

```SQL
-- create table 'Branch'
CREATE TABLE Branch (
	-- columns / fields
    branchNo CHAR(4),
    street VARCHAR(20),
    city VARCHAR(15),
    postcode VARCHAR(8),

    -- constraints

    -- primary key
    CONSTRAINT PK_tblBranch PRIMARY KEY ( branchNo ),
    -- primary key constraint
    CONSTRAINT start_with_PK_tblBranch CHECK ( branchNo LIKE 'B%' )
);
```

## Staff Table

```SQL
-- create table 'Staff'
CREATE TABLE Staff (
	-- columns / fields
    staffNo VARCHAR(4),
    fname VARCHAR(25),
    lname VARCHAR(20),
    position VARCHAR(15),
    sex CHAR(1),
    DOB DATE,
    salary INTEGER,
    branchNo CHAR(4),

	-- contraints

    -- primary key
    CONSTRAINT PK_tblStaff PRIMARY KEY ( staffNo ),
    -- primary key constraint
    CONSTRAINT start_with_PK_tblStaff CHECK ( staffNo LIKE 'S%' ),

	-- check constraints
    CONSTRAINT chk_position_tblStaff CHECK ( position IN ( 'Manager', 'Assistant', 'Supervisor' ) ),
    CONSTRAINT chk_sex_tblStaff CHECK ( sex IN ( 'M', 'F' ) ),
    CONSTRAINT chk_salary_tblStaff CHECK ( salary > 7000 ),

	-- foreign key
    CONSTRAINT FK_branchNo_tblStaff FOREIGN KEY ( branchNo ) REFERENCES Branch ( branchNo ),
	-- foreign key constraint
    CONSTRAINT start_with_FK_branchNo_tblStaff CHECK ( branchNo LIKE 'B%' )
);
```

## Client Table

```SQL
-- create table 'Client'
CREATE TABLE Client (
	-- columns / fields
    clientNo CHAR(4),
    fname VARCHAR(25),
    lname VARCHAR(20),
    phone VARCHAR(20),
    prefType VARCHAR(5),
    maxRent INTEGER,

	-- constraints

	-- primary key
    CONSTRAINT PK_tblClient PRIMARY KEY ( clientNo ),
	-- primary key constraint
    CONSTRAINT start_with_PK_tblClient CHECK ( clientNo LIKE 'CR%' ),

	-- check constraint
    CONSTRAINT chk_prefType_tblClient CHECK ( prefType IN ( 'House', 'Flat' ) )
);
```

## Property for Rent Table

```SQL
-- create table 'PropertyForRent'
CREATE TABLE PropertyForRent (
	-- columns / fields
    propertyNo VARCHAR(4),
    street VARCHAR(20),
    city VARCHAR(15),
    postcode VARCHAR(8),
    ptype VARCHAR(5),
    rooms SMALLINT,
    rent INTEGER,
    staffNo VARCHAR(4),
    branchNo CHAR(4),

	-- constraints

	-- primary key
    CONSTRAINT PK_tblPropertyForRent PRIMARY KEY ( propertyNo ),
	-- primary key constraint
    CONSTRAINT start_with_PK_tblPropertyForRent CHECK ( propertyNo LIKE 'P%' ),

	-- check constraints
    CONSTRAINT chk_ptype_tblPropertyForRent CHECK ( ptype IN ( 'House', 'Flat' ) ),
    CONSTRAINT chk_rooms_tblPropertyForRent CHECK ( rooms > 0 AND rooms < 10 ),
    CONSTRAINT chk_rent_tblPropertyForRent CHECK ( rent > 0 AND rent < 1000 ),

	-- foreign keys and foreign key constraints
    CONSTRAINT FK_branchNo_tblPropertyForRent FOREIGN KEY ( branchNo ) REFERENCES Branch ( branchNo ),
    CONSTRAINT start_with_FK_branchNo_tblPropertyForRent CHECK ( branchNo LIKE 'B%' ),
    CONSTRAINT FK_staffNo_tblPropertyForRent FOREIGN KEY ( staffNo ) REFERENCES Staff ( staffNo ),
    CONSTRAINT start_with_FK_staffNo_tblPropertyForRent CHECK ( staffNo LIKE 'S%' )
);
```

## Private Owner Table

```SQL
-- create table 'PrivateOwner'
CREATE TABLE PrivateOwner (
	-- columns / fields
    ownerNo CHAR(4),
    fname VARCHAR(25),
    lname VARCHAR(20),
    address VARCHAR(40),
    telNo VARCHAR(20),

	-- constraint

	-- primary key
    CONSTRAINT PK_tblPrivateOwner PRIMARY KEY ( ownerNo ),
	-- primary key constraint
    CONSTRAINT start_with_PK_tblPrivateOwner CHECK ( ownerNo LIKE 'CO%' )
);
```

## Viewing Table

```SQL
-- create table 'Viewing'
CREATE TABLE Viewing (
	-- columns / fields
    clientNo CHAR(4),
    propertyNo VARCHAR(4),
    viewDate DATE,
    comment VARCHAR(50),

	-- constraints

	-- composite primary key
    CONSTRAINT CPK_tblViewing PRIMARY KEY ( clientNo, propertyNo ),

	-- foreign keys and foreign key constraints
    CONSTRAINT FK_clientNo_tblViewing FOREIGN KEY ( clientNo ) REFERENCES Client ( clientNo ),
    CONSTRAINT start_with_FK_clientNo_tblViewing CHECK ( clientNo LIKE 'CR%' ),
    CONSTRAINT FK_propertyNo_tblViewing FOREIGN KEY ( propertyNo ) REFERENCES PropertyForRent ( propertyNo ),
    CONSTRAINT start_with_FK_propertyNo_tblViewing CHECK ( propertyNo LIKE 'P%' )
);
```

## Registration Table

```SQL
-- create table 'Registration'
CREATE TABLE Registration (
	-- columns / fields
    clientNo CHAR(4),
    dateJoined DATE,
    branchNo CHAR(4),
    staffNo VARCHAR(4),

	-- constraints

	-- primary key
    CONSTRAINT PK_tblRegistration PRIMARY KEY ( clientNo ),

	-- foreign keys and foreign key constraints
    CONSTRAINT FK_clientNo_tblRegistration FOREIGN KEY ( clientNo ) REFERENCES Client ( clientNo ),
    CONSTRAINT start_with_FK_clientNo_tblRegistration CHECK ( clientNo LIKE 'CR%' ),
    CONSTRAINT FK_branchNo_tblRegistration FOREIGN KEY ( branchNo ) REFERENCES Branch ( branchNo ),
    CONSTRAINT start_with_FK_branchNo_tblRegistration CHECK ( branchNo LIKE 'B%' ),
    CONSTRAINT FK_staffNo_tblRegistration FOREIGN KEY ( staffNo ) REFERENCES Staff ( staffNo ),
    CONSTRAINT start_with_FK_staffNo_tblRegistration CHECK ( staffNo LIKE 'S%' )
);
```

---

# Add Another Column to Table Property for Rent

## Create the New Column

```SQL
-- alter table 'PropertyForRent' to add new column 'ownerNo'
ALTER TABLE PropertyForRent
ADD ownerNo CHAR(4);
```

## Make that Column a Foreign Key Column

```SQL
-- make 'ownerNo' in table 'PropertyForRent' a foreign key
ALTER TABLE PropertyForRent
ADD CONSTRAINT FK_ownerNo_tblPropertyForRent FOREIGN KEY ( ownerNo ) REFERENCES PrivateOwner ( ownerNo );
```

## Add Check Constraint

```SQL
-- values of 'ownerNo' in table 'PropertyForRent' must start with characters 'CO'
ALTER TABLE PropertyForRent
ADD CONSTRAINT start_with_FK_ownerNo_tblPropertyForRent CHECK ( ownerNo LIKE 'CO%' );
```

---

# Socials

- **Instagram**: https://www.instagram.com/s.sunhaloo
- **YouTube**: https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg
- **GitHub**: https://www.github.com/Sunhaloo

---

S.Sunhaloo
Thank You!