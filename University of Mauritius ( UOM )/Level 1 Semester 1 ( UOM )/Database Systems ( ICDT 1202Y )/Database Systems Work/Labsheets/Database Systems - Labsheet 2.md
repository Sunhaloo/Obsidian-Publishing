---
Alias: Database Systems ( Semester 1 Labsheet 1 )
tags: uni, db, lab
Module: ICDT 1202Y
Author: S.Sunhaloo
Date: 2024-08-07
Status: HOLD
---

>[!note]
>You need to follow [[Database Systems - Labsheet 1 | Labsheet 1]] first to be able to do this labsheet.

## List of Contents

- [[Database Systems - Labsheet 2#Insert Data into Tables | Insert Data into Tables]]

---

### My Links

- [[Database Systems - Labsheet 2#Socials | Link to Socials]]

---

# Insert Data into Tables

## Insert Values into Branch Table

```SQL
-- Inserting Data / Values into table 'Branch'
INSERT INTO Branch ( branchNo, street, city, postcode ) VALUES ( 'B005', '22 Deer Rd', 'London', 'SW1 4EH' );
INSERT INTO Branch ( branchNo, street, city, postcode ) VALUES ( 'B007', '16 Argyll St', 'Aberdeen', 'AB2 3SU' );
INSERT INTO Branch ( branchNo, street, city, postcode ) VALUES ( 'B003', '162 Main St', 'Glasgow', 'G11 9QX' );
INSERT INTO Branch ( branchNo, street, city, postcode ) VALUES ( 'B004', '32 Manse Rd', 'Bristol', 'BS99 1NZ' );
INSERT INTO Branch ( branchNo, street, city, postcode ) VALUES ( 'B002', '56 Clover Dr', 'London', 'NW10 6EU' );
```

## Insert Values into Staff Table

```SQL
-- Insert Data / Values into table 'Staff'
INSERT INTO Staff ( staffNo, fname, lname, position, sex, DOB, salary, branchNo ) VALUES ( 'SL21', 'John', 'White', 'Manager', 'M', '1-Oct-45', 30000, 'B005' )
INSERT INTO Staff ( staffNo, fname, lname, position, sex, DOB, salary, branchNo ) VALUES ( 'SG37', 'Ann', 'Beech', 'Assistant', 'F', '10-Nov-60', 12000, 'B003' )
INSERT INTO Staff ( staffNo, fname, lname, position, sex, DOB, salary, branchNo ) VALUES ( 'SG14', 'David', 'Ford', 'Supervisor', 'M', '24-Mar-58', 18000, 'B003' )
INSERT INTO Staff ( staffNo, fname, lname, position, sex, DOB, salary, branchNo ) VALUES ( 'SA9', 'Mary', 'Howe', 'Assistant', 'F', '19-Feb-70', 9000, 'B007' )
INSERT INTO Staff ( staffNo, fname, lname, position, sex, DOB, salary, branchNo ) VALUES ( 'SG5', 'Susan', 'Brand', 'Manager', 'F', '3-Jun-40', 24000, 'B003' )
INSERT INTO Staff ( staffNo, fname, lname, position, sex, DOB, salary, branchNo ) VALUES ( 'SL45', 'Julie', 'Lee', 'Assistant', 'F', '13-Jun-65', 9000, 'B003' )
```

## Insert Values into Private Owner Table

```SQL
-- Insert Data / Values into table 'PrivateOwner'
INSERT INTO PrivateOwner ( ownerNo, fname, lname, address, telNo ) VALUES ( 'CO46', 'Joe', 'Keogh', '2 Fergus Dr, Aberdeen AB2 7SX', '01224-861212' );
INSERT INTO PrivateOwner ( ownerNo, fname, lname, address, telNo ) VALUES ( 'CO87', 'Carol', 'Farrel', '6 Achray St, Glasgow G32 9DX', '0141-357-7419' );
INSERT INTO PrivateOwner ( ownerNo, fname, lname, address, telNo ) VALUES ( 'CO40', 'Tina', 'Murphy', '63 Well St, Glasgow G42', '0141-943-1728' );
INSERT INTO PrivateOwner ( ownerNo, fname, lname, address, telNo ) VALUES ( 'CO93', 'Tony', 'Shaw', '12 Park Pl, Glasgow G4 0QR', '0141-225-7025' );
```

## Insert Values into Property for Rent Table

```SQL
-- Insert Data / Values into table 'PropertyForRent'
INSERT INTO PropertyForRent ( propertyNo, street, city, postcode, ptype, rooms, rent, ownerNo, staffNo, branchNo ) VALUES ( 'PA14', '16 Holhead', 'Aberdeen', 'AB7 5SU', 'House', 6, 650, 'CO46', 'SA9', 'B007' );
-- problem here v
INSERT INTO PropertyForRent ( propertyNo, street, city, postcode, ptype, rooms, rent, ownerNo, staffNo, branchNo ) VALUES ( 'PA94', '6 Argyll St', 'London', 'NW2', 'Flat', 4, 400, 'CO87', 'SL41', 'B005' );
INSERT INTO PropertyForRent ( propertyNo, street, city, postcode, ptype, rooms, rent, ownerNo, staffNo, branchNo ) VALUES ( 'PG4', '6 Lawrence St', 'Glasgow', 'G11 9QX', 'Flat', 3, 350, 'CO40', NULL, 'B003' );
INSERT INTO PropertyForRent ( propertyNo, street, city, postcode, ptype, rooms, rent, ownerNo, staffNo, branchNo ) VALUES ( 'PG36', '2 Manor Rd', 'Glasgow', 'G32 4QX', 'Flat', 3, 375, 'CO93', 'SG37', 'B003' );
INSERT INTO PropertyForRent ( propertyNo, street, city, postcode, ptype, rooms, rent, ownerNo, staffNo, branchNo ) VALUES ( 'PG21', '18 Dale Rd', 'Glasgow', 'G12', 'House', 5, 600, 'CO87', 'SG37', 'B003' );
INSERT INTO PropertyForRent ( propertyNo, street, city, postcode, ptype, rooms, rent, ownerNo, staffNo, branchNo ) VALUES ( 'PG16', '5 Novar Dr', 'Glasgow', 'G12 9AX', 'Flat', 4, 450, 'CO93', 'SG14', 'B003' );
```

## Insert Values into Client Table

```SQL
-- Insert Data / Values into table 'Client'
INSERT INTO Client ( clientNo, fname, lname, phone, prefType, maxRent ) VALUES ( 'CR76', 'John', 'Kay', '0207-774-5632', 'Flat', 425 )
INSERT INTO Client ( clientNo, fname, lname, phone, prefType, maxRent ) VALUES ( 'CR56', 'Aline', 'Stewart', '0141-848-1825', 'Flat', 350 )
INSERT INTO Client ( clientNo, fname, lname, phone, prefType, maxRent ) VALUES ( 'CR74', 'Mike', 'Ritchie', '01475-392178', 'House', 750 )
INSERT INTO Client ( clientNo, fname, lname, phone, prefType, maxRent ) VALUES ( 'CR62', 'Mary', 'Tregear', '01224-196720', 'Flat', 600 )
```

## Insert Values into Registration Table

```SQL
-- Insert Data / Values into table 'Registration'
-- problem here v
INSERT INTO Registration ( clientNo, branchNo, staffNo, dateJoined ) VALUES ( 'CR76', 'B005', 'SL41', '2-Jan-04' )
INSERT INTO Registration ( clientNo, branchNo, staffNo, dateJoined ) VALUES ( 'CR56', 'B003', 'SG37', '11-Apr-03' )
INSERT INTO Registration ( clientNo, branchNo, staffNo, dateJoined ) VALUES ( 'CR74', 'B003', 'SG37', '16-Nov-02' )
INSERT INTO Registration ( clientNo, branchNo, staffNo, dateJoined ) VALUES ( 'CR62', 'B007', 'SA9', '7-Mar-03' )
```

## Insert Values into Viewing Table

```SQL
-- Insert Data / Values into table 'Viewing'
INSERT INTO Viewing ( clientNo, propertyNo, viewDate, comment ) VALUES ( 'CR56', 'PA14', '24-May-04', 'too small' )
INSERT INTO Viewing ( clientNo, propertyNo, viewDate, comment ) VALUES ( 'CR76', 'PG4', '20-Apr-04', 'too remote' )
INSERT INTO Viewing ( clientNo, propertyNo, viewDate, comment ) VALUES ( 'CR56', 'PG4', '26-May-04', 'null' )
INSERT INTO Viewing ( clientNo, propertyNo, viewDate, comment ) VALUES ( 'CR62', 'PA14', '14-May-04', 'no dining room' )
INSERT INTO Viewing ( clientNo, propertyNo, viewDate, comment ) VALUES ( 'CR56', 'PG36', '28-Apr-04', 'null' )
```

---

# Socials

- **Instagram**: https://www.instagram.com/s.sunhaloo
- **YouTube**: https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg
- **GitHub**: https://www.github.com/Sunhaloo

---

S.Sunhaloo
Thank You!