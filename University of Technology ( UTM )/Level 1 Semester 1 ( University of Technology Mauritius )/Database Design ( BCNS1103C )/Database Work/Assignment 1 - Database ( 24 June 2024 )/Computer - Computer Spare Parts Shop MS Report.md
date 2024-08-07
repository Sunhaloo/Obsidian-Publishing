---
Alias: Database Design ( Assignment 1 - MS Access Report ) - Week 8
Tag: uni, db, access
Module: BCNS1103C / DBT1103C
Author: S.Sunhaloo
Date: 2024-06-26
Status: Completed
---

## List of Contents

- [[Computer - Computer Spare Parts Shop Microsoft Access Report#Creation of Tables | Creation of Tables]]
- [[Computer - Computer Spare Parts Shop Microsoft Access Report#Creation of Forms| Creation of Forms]]
- [[Computer - Computer Spare Parts Shop Microsoft Access Report#Queries | Queries]]

---

### My Links

- [[Computer - Computer Spare Parts Shop Microsoft Access Report#Socials | Link to Socials]]

---

# Creation of Tables

>[!note]
>For the **Validation** I have only added the *fields* that has a **Validation** Rule and Text!

## Customer Table

- Name: `tblCustomer`
- Number of Fields: 6

### Customer Table `Design View`

![[Design View - Customer Table.png]]

### Customer Tables Validations

| Field | Validation Rule | Validation Text |
| ----- | --------------- | --------------- |
| Mobile Number | `Len([Mobile Number]) = 8` | Length of Mobile Number should be Equal to 8 |
| Gender | `"M" Or "F"` | Gender must be Male ( M ) or Female ( F ) |

## Employee Table

- Name: `tblEmployee`
- Number of Fields: 7

### Employee Table `Design View`

![[Design View - Employee Table.png]]

### Employee Table Validations

| Field | Validation Rule | Validation Text |
| ----- | --------------- | --------------- |
| Department | `"Manager" Or "Cashier" Or "Sales Representative" Or "Technician"` | Department can only be 'Manager' or 'Sales Representative' or 'Technician' or 'Cashier' |
| Date of Birth | `<=DateAdd("yyyy",-18,Date())` | Age of Employee cannot be Lower than 18 |
| Mobile Number | `Len([Mobile Number]) = 8` | Length of Mobile Number should be Equal to 8 |
| Salary | `>=20000` | Salary of Employee cannot be Lower than 20000 |

## Computer Parts Table

- Name: `tblComputerParts`
- Number of Fields: 7

### Computer Parts Table `Design View`

![[Design View - Computer Parts Table.png]]

### Computer Parts Table Validations

| Field | Validation Rule | Validation Text |
| ----- | --------------- | --------------- |
| Category | `'CPU' Or 'GPU' Or 'RAM' Or 'Storage-HDD' Or 'Storage-SSD' Or 'Storage-NVMe' Or 'Fans' Or 'Motherboard' Or 'PSU' Or 'Case' Or 'Wiring'` | Category of Part can either be 'CPU' Or 'GPU' Or 'RAM' Or 'Storage-HDD' Or 'Storage-SSD' Or 'Storage-NVMe' Or 'Fans' Or 'Motherboard' Or 'PSU' Or 'Case' Or 'Wiring' |
| Tested | `True Or False` | Computer Part can either be Tested ( True ) or NOT Tested ( False ) |
| Price | `>=250` | Price of Computer Part cannot be Lower than 250 Rupees |
| Warranty | `>= 0 Or <= 10` | Warranty should be in the range of 0 to 10 Years |

## Service Table

- Name: `tblService`
- Number of Fields: 5

### Service Table `Design View`

![[Design View - Service Table.png]]

### Service Table Validations

| Field | Validation Rule | Validation Text |
| ----- | --------------- | --------------- |
| Service | `"Consulation" Or "Repair" Or "Build"` | Service can only be 'Consultation' or 'Repair' or 'Build' |
| Price | `>=500 And <= 1500` | Price of Computer Part cannot be Lower than 250 Rupees |
| Service Date | `Date()` | Service Date must be in the Future |

## Stock Parts Table

- Name: `tblStockParts`
- Number of Fields: 4

### Stock Parts Table `Design View`

![[Design View - Stock Parts Table.png]]

### Stock Parts Table Validations

| Field | Validation Rule | Validation Text |
| ----- | --------------- | --------------- |
| Buying Price | `[Buying Price]<[Selling Price]` | Buying Price of Computer Part should be Less than Selling Price |
| Selling Price | `[Buying Price]<[Selling Price]` | Buying Price of Computer Part should be Less than Selling Price |

>[!warning]
>The **Validation** rules and text for 'Buying Price' and 'Selling Price' are added using the `Properties` Menu!

## Order Table

- Name: `tblOrder`
- Number of Fields: 6

### Order Table `Design View`

![[Design View - Order Table.png]]

### Order Table Validations

| Field | Validation Rule | Validation Text |
| ----- | --------------- | --------------- |
| Order Date | `>=Date()` | Order Date must be Today or in the Future |
| Price | `>=250` | Price of Computer Part cannot be Less than 250 |
| Payment Method | `"C" Or "F"` | Pay with either Cash ( C ) or Finance ( F ) |

## Delivery Table

- Name: `tblCustomer`
- Number of Fields: 7

### Delivery Table `Design View`

![[Design View - Delivery Table.png]]

### Delivery Table Validations

| Field | Validation Rule | Validation Text |
| ----- | --------------- | --------------- |
| Mobile Number | `Len([Mobile Number]) = 8` | Length of Mobile Number should be Equal to 8 |
| Order Date | `>=Date()` | Order Date must be Today or in the Future |
| Price | `>=250` | Price of Computer Part cannot be Less than 250 |

---

# Creation of Forms

## Customer Form

![[Form - Customer Table.png]]

## Customer View Form

![[Form View - Customer Table.png]]

## Employee Form

![[Form - Employee Table.png]]

## Employee View Form

![[Form View - Employee Table.png]]

## Computer Parts Form

![[Form - Computer Parts Table.png]]

## Computer Parts View Form

![[Form View - Computer Parts Table.png]]

## Service Form

![[Form - Service Table.png]]

## Service View Form

![[Form View -  Service Table.png]]

## Stock Form

![[Form - Stock Part.png]]

## Stock View Form

![[Form View - Stock Part.png]]

## Order Form

![[Form - Order Table.png]]

## Order View Form

![[Form View - Order Table.png]]

## Delivery Form

![[Form - Delivery Table.png]]

## Delivery View Form

![[Form View - Delivery Table.png]]

---

# Queries

## Profit Margin Query

![[Query - Profit Margin 1.png]]

### Profit Calculated Field

![[Query - Profit Margin ( Calculated Field ).png]]

---

# Socials

- **Instagram**: https://www.instagram.com/s.sunhaloo/
- **YouTube**: https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg
- **GitHub**: https://www.github.com/Sunhaloo

---

S.Sunhaloo
Thank You!