---
Alias: Database Design ( Assignment 1 - Requirements ) - Week 8
Tag: uni, db
Module: BCNS1103C / DBT1103C
Author: S.Sunhaloo
Date: 2024-06-23
Status: Completed
---

<p align="center">Database Design<br>Assignment 1<br>BCNS1103C / DBT1103C<br>SUNHALOO Shehzaad</p>

<p align="center">University of Technology, Mauritius</p>

<h1 align="center">Computer / Computer Spare Parts Shop</h1>

---

## List of Contents

- [[Computer - Computer Spare Parts Shop Requirements#Analysis Phase| Analysis Phase]]
	- [[Computer - Computer Spare Parts Shop Requirements#Introduction| Introduction]]
	- [[Computer - Computer Spare Parts Shop Requirements#Brief History of Company| Brief History of Company]]
	- [[Computer - Computer Spare Parts Shop Requirements#Limitations with Existing System and Background Information of Proposed System| Limitations with Existing System and Background Information of Proposed System]]
		- [[Computer - Computer Spare Parts Shop Requirements#Limitations with Existing System| Limitations with Existing System]]
		- [[Computer - Computer Spare Parts Shop Requirements#Background Information of Proposed System| Background Information of Proposed System]]
	- [[Computer - Computer Spare Parts Shop Requirements#Organigram| Organigram]]
	- [[Computer - Computer Spare Parts Shop Requirements#Description of their Main Activities| Description of their Main Activities]]
	- [[Computer - Computer Spare Parts Shop Requirements#Data Dictionary| Data Dictionary]]
	- [[Computer - Computer Spare Parts Shop Requirements#Business Rules| Business Rules]]
	- [[Computer - Computer Spare Parts Shop Requirements#Function and Non-Function Requirements| Function and Non-Function Requirements]]
		- [[Computer - Computer Spare Parts Shop Requirements#List of Functional Requirements| List of Functional Requirements]]
		- [[Computer - Computer Spare Parts Shop Requirements#List of Non-Functional Requirements| List of Non-Functional Requirements]]
	- [[Computer - Computer Spare Parts Shop Requirements#Queries| Queries]]
	- [[Computer - Computer Spare Parts Shop Requirements#Conclusion and Appraisal| Conclusion and Appraisal]]
		- [[Computer - Computer Spare Parts Shop Requirements#Conclusion| Conclusion]]
		- [[Computer - Computer Spare Parts Shop Requirements#Appraisal| Appraisal]]

---

### My Links

- [[Computer - Computer Spare Parts Shop Requirements ( Version 4 )#Socials| Link to Socials]]

---

# Analysis Phase

## Introduction

Established on June 15, 1995, by James May, Sun's Systems is a reliable and customer-focused company in the computer hardware industry. Located at Place D'Armes, the company attracts many customers and tourists with its extensive product range and exceptional service.
Sun's Systems has built a solid reputation for providing a variety of computer products and spare parts. The company offers an array of desktops and essential computer components like motherboards, processors, graphics cards, and storage devices, catering to diverse customer needs.
Additionally, Sun's Systems provides services such as building custom computers for professionals and gamers, as well as expert computer repair and convenient delivery services. These services have further cemented the company's position as a trusted provider in the industry.
As James May approaches retirement, he plans to pass the company on to his son, ensuring that Sun's Systems continues to serve its community with dedication and quality. This transition will allow the company to maintain its commitment to excellence and customer satisfaction.

## Brief History of Company

Since its establishment in the 1990s, Sun's Systems has operated with a largely manual system. The company relies on text-based documents and basic spreadsheet programs to track customer orders and inventory of parts. This traditional approach has served the company well in its early years.
With the emergence of the Internet, Sun's Systems has experienced increased customer traffic, driven by positive recommendations for its products and services. However, this surge in popularity has presented new challenges. Managing data and information manually has become increasingly difficult, leading to issues such as lost records, delays in order processing, and the need for frequent rewriting of information. These inefficiencies have become more pronounced as the business grows, highlighting the inadequacy of the current system for handling the increasing volume of transactions and customer interactions. Consequently, there is a pressing need to transition to a more efficient, automated system to keep pace with the company’s expansion and to maintain high standards of customer service.

## Limitations with Existing System and Background Information of Proposed System

### Limitations with Existing System

Since its inception, the company has relied on manual processes to manage operations, from tracking stock to handling customer computer parts and services like repairing computers, building new custom computers and making deliveries. This involved using paper-based records and spreadsheet software.

However, with increasing customer feedback, the original system (manual processes and spreadsheets) is becoming obsolete. As the company gains more clients, the shortcomings of Sun's Systems' management system are becoming apparent.

Challenges Faced:

- Inaccuracies in data
- Data loss
- Time-consuming processes
- Redundancy
- Delays
- Goals of the New System

### Background Information of Proposed System

The new system aims to improve the system by using:

1. Centralized Database:

	- Store and structure data in a single location (computer/server)
	- Reduce/eliminate the risk of data loss and inconsistencies
	- Include backup functionalities

2. Automated Entries:

	- Minimize time spent on data entry
	- Enhance accuracy

By transitioning to a modern, automated database system, Sun's Systems will be well-equipped to handle its growing customer base and operational demands. The new system will not only address current challenges but also pave the way for future success by enhancing data management, operational efficiency, and customer experience.

## Organigram

>[!info]
>Please Refer to Organigram on Separate Page!

## Description of their Main Activities

### IPO Concept

Sun's System engages in various daily activities to ensure smooth operations and excellent customer service. Here are their main daily activities:

| Management / Service | Staff | CREATE | READ | UPDATE | DELETE | Entities |
| -------------------- | ----- | ------ | ----- | ----- | ------ | -------- |
| Stock Management | Store Manager | New Product added to Inventory System | Store Manager check the current stock levels to prepare monthly restock | Store Manager checks the current stock levels to prepare monthly restock | Removal of discontinued product from Inventory Records | - Stock Parts <br> - Stock Prebuilt Computer <br> - Stock Computer Parts|
| Customer Service | Sales Representative | New customer is added into system after first purchase | Customer Representative checks the status for open service request by Customer | After resolving the service request asked by Customer, status is set to "resolved" | Customer requests deletion of their records from system | - Customer <br> - Computer Parts <br> - Prebuilt Computers |
| Repair and Maintenance | Repair & Diagnostic Team | Add new repair / maintenance tasks to system when Customer brings in computers / computer parts | View details and statuses of ongoing repair / maintenance | Modify details for existing repair / maintenance tasks; status becomes completed, Customer is called | Deleting repair / maintenance records that are no longer needed from years ago | - Service <br> - Computer Parts |
| Custom Computer Builds | Computer Build Team | Customer places new order for Custom PC build; build order is recorded | Technician checks the details and statuses of all ongoing PC builds | After build completion, technician will update status to "completed"; calls the Customer to pick up PC | Deleting computer build that are no longer needed from years ago | - Service <br> - Computer Parts |
| Administrative Tasks | Manager | New employee record is create when he / she joins | Manager / Administrator checks for attendance of the month | Employee contact information is updated in the system | Employee records who has left the company is deleted | Employee |
| Marketing and Customer Outreach | Sales Representative <br> Manager | Develop new promotional campaign for holiday seasons | Review performance metrics for recent social media posts / campaign | Adjust targeting criteria for ongoing Social Media Ads | Removal of outdated holiday promotions | - Employee |
| Deliveries | Delivery Team | Create new delivery order for Customer who has purchased computer parts | Check status for specific delivery order and retrieve delivery history for that particular Part / Customer | Update delivery address for Customer's order | Cancel delivery order and remove it from system; Deletion for old delivery logs | - Customer <br> - Employee <br> - Computer Parts |

## Data Dictionary

### Customer Table

| Field Name | Data Type | Field Size | Description | Validation Rule | Example |
| ---------- | --------- | ---------- | ----------- | --------------- | ------- |
| Customer ID | AutoNumber | 4 Bytes / 32 Bits | Unique Record Identifier for `tblCustomer` | - | 8 |
| First Name | Text | 30 Characters / Bytes | First Name of Customer | - | Carlos |
| Last Name | Text | 30 Characters / Bytes | Last Name of Customer | - | Sainz |
| Address | Text | 100 Characters / Bytes | Primary Place of Residence | - | Old Moka Road |
| Mobile Number | Number | 4 Bytes / 32 Bits | Mobile / Phone Number of Customer | Length of Mobile Number should be 8 | 52080842 |
| Gender | Text | 1 Character / Byte | Customer's Gender | Either 'M' or 'F' | M |

### Employee Table

| Field Name | Data Type | Field Size | Description | Validation Rule | Example |
| ---------- | --------- | ---------- | ----------- | --------------- | ------- |
| Employee ID | AutoNumber | 4 Bytes / 32 Bits | Unique Record Identifier for `tblEmployee` | - | 10 |
| First Name | Text | 30 Characters / Bytes | First Name of Employee | - | Lewis |
| Last Name | Text | 30 Characters / Bytes | Last Name of Employee | - | Hamilton |
| Department | Text | 50 Characters / Bytes | Department / Specialisation of Employee | - | Cashier |
| Date of Birth | Date/Time | 8 Bytes / 64 Bits | Date of Birth of Employee | Age ( Calculated Value ) Must not be **Below** 18 | 15/10/04 |
| Mobile Number | Number | 4 Bytes / 32 Bits | Mobile / Phone Number of Customer | Length of Mobile Number should be 8 | 53348245 |
| Salary | Number | 4 Bytes / 32 Bits | Employee's Salary | Salary should Not be **Below** 20000 | 25000 |

### Computer Parts Table

| Field Name | Data Type | Field Size | Description | Validation Rule | Example |
| ---------- | --------- | ---------- | ----------- | --------------- | ------- |
| Part ID | AutoNumber | 4 Bytes / 32 Bits | Unique Record Identifier for `tblComputerParts` | - | 5 |
| Part Make | Text | 30 Characters / Bytes | Make / Brand of Computer Part | - | Intel |
| Part Name | Text | 30 Characters / Bytes | Name of Part | - | Core i5-14400F |
| Category | Text | 15 Characters / Bytes | Indicates the Category of Part | Can either be 'CPU', 'GPU', 'RAM', 'Storage-HDD', 'Storage-SSD', 'Storage-NVMe', 'Fans', 'Motherboard', 'PSU', 'Case', 'Wiring' | CPU |
| Tested | Yes/No | 1 Byte / 8 Bits | Has the Part been Tested before Selling? | Yes Or No | Yes |
| Price | Number | 4 Bytes / 32 Bits | Price of Part | Price of Part Cannot be **Lower** than 250 | 3000 |
| Warranty | Number | 4 Bytes / 32 Bits | Number of Years of Warranty of Part | Warranty must be in the range of 0 to 10 ( not more or less ) | 10 |

### Service Table ( Without Foreign Key )

| Field Name | Data Type | Field Size | Description | Validation Rule | Example |
| ---------- | --------- | ---------- | ----------- | --------------- | ------- |
| Service ID | AutoNumber | 4 Bytes / 32 Bits | Unique Record Identifier for `tblService` | - | 6 |
| Service | Text | 15 Characters / Bytes | Service Type | Service can either be 'Consultation', 'Repair' Or 'Build' | Build |
| Price | Number | 4 Bytes / 32 Bits | Price of Service | Price must be in the range of 500 to 1000 ( Not More or Less) | 1000 |

### Service Table ( With Foreign Key )

| Field Name | Data Type | Field Size | Description | Validation Rule | Example |
| ---------- | --------- | ---------- | ----------- | --------------- | ------- |
| Service ID | AutoNumber | 4 Bytes / 32 Bits | Unique Record Identifier for `tblService` | - | 6 |
| Service | Text | 15 Characters / Bytes | Service Type | Service can either be 'Consultation', 'Repair' Or 'Build' | Build |
| Customer ID | Number | 4 Bytes / 32 Bits | Unique Record Identifier for `tblCustomer` | - | 8 |
| Service Date | Date/Time | 8 Bytes / 64 Bits | Store the date when Customer will receive Service | Date must be in the Future | 15/10/04 |
| Price | Number | 4 Bytes / 32 Bits | Price of Service | Price must be in the range of 500 to 1000 ( Not More or Less) | 1000 |

### Stock Table

#### Stock Parts Table ( Without Foreign Key )

| Field Name | Data Type | Field Size | Description | Validation Rule | Example |
| ---------- | --------- | ---------- | ----------- | --------------- | ------- |
| Stock ID | AutoNumber | 4 Bytes / 32 Bits | Unique Record Identifier for `tblStockParts` | - | 10 |
| Part Make | Text | 30 Characters / Bytes | Make / Brand of Computer Part | - | MSI |
| Part Name | Text | 30 Characters / Bytes | Name of Part | - | NVIDIA GTX 1660 Super |
| Category | Text | 15 Characters / Bytes | Indicates the Category of Part | Can either be 'CPU', 'GPU', 'RAM', 'Storage-HDD', 'Storage-SSD', 'Storage-NVMe', 'Fans', 'Motherboard', 'PSU', 'Case', 'Wiring' | GPU |
| Buying Price | Number | 4 Bytes / 32 Bits | Price from Supplier / Manufacturer | Cannot be Lower than *Selling Price* | 15000 |
| Selling Price | Number | 4 Bytes / 32 Bits | Price from Supplier / Manufacturer | Cannot be Higher than *Buying Price* | 16000 |

#### Stock Parts Table ( With Foreign Key )

| Field Name | Data Type | Field Size | Description | Validation Rule | Example |
| ---------- | --------- | ---------- | ----------- | --------------- | ------- |
| Stock ID | AutoNumber | 4 Bytes / 32 Bits | Unique Record Identifier for `tblStockParts` | - | 10 |
| Part ID | Number | 4 Bytes / 32 Bits | Unique Record Identifier for `tblComputerParts` | - | 1 |
| Part Make | Text | 30 Characters / Bytes | Make / Brand of Computer Part | - | MSI |
| Part Name | Text | 30 Characters / Bytes | Name of Part | - | NVIDIA GTX 1660 Super |
| Category | Text | 15 Characters / Bytes | Indicates the Category of Part | Can either be 'CPU', 'GPU', 'RAM', 'Storage-HDD', 'Storage-SSD', 'Storage-NVMe', 'Fans', 'Motherboard', 'PSU', 'Case', 'Wiring' | GPU |
| Buying Price | Number | 4 Bytes / 32 Bits | Price from Supplier / Manufacturer | Cannot be Lower than *Selling Price* | 15000 |
| Selling Price | Number | 4 Bytes / 32 Bits | Price from Supplier / Manufacturer | Cannot be Higher than *Buying Price* | 16000 |

### Order Table

#### Order Parts Table ( Without Foreign Key )

| Field Name | Data Type | Field Size | Description | Validation Rule | Example |
| ---------- | --------- | ---------- | ----------- | --------------- | ------- |
| OrderP ID | AutoNumber | 4 Bytes / 32 Bits | Unique Record Identifier for `tblStockComputer` | - | 6 |
| First Name | Text | 30 Characters / Bytes | First Name of Customer | - | Carlos |
| Last Name | Text | 30 Characters / Bytes | Last Name of Customer | - | Sainz |
| Order Date | Date/Time | 8 Bytes / 64 Bits | Store the date when Customer brought Product | Date must be Today or in the Future | 15/10/04 |
| Part Make | Text | 30 Characters / Bytes | Make / Brand of Computer Part | - | MSI |
| Part Name | Text | 30 Characters / Bytes | Name of Part | - | NVIDIA GTX 1660 Super |
| Price | Number | 4 Bytes / 32 Bits | Price of Part | Price of Part Cannot be **Lower** than 250 | 3000 |
| Payment Method | Text | 1 Characters / Bytes | How will the Customer Pay | Can either pay with Cash or Finance | C |

#### Order Parts Table ( With Foreign Key )

| Field Name | Data Type | Field Size | Description | Validation Rule | Example |
| ---------- | --------- | ---------- | ----------- | --------------- | ------- |
| OrderP ID | AutoNumber | 4 Bytes / 32 Bits | Unique Record Identifier for `tblStockComputer` | - | 6 |
| Customer ID | Number | 4 Bytes / 32 Bits | Unique Record Identifier for `tblCustomer` | - | 8 |
| First Name | Text | 30 Characters / Bytes | First Name of Customer | - | Carlos |
| Last Name | Text | 30 Characters / Bytes | Last Name of Customer | - | Sainz |
| Order Date | Date/Time | 8 Bytes / 64 Bits | Store the date when Customer brought Product | Date must be today | 15/10/04 |
| Part ID | Number | 4 Bytes / 32 Bits | Unique Record Identifier for `tblComputerParts` | - | 1 |
| Part Make | Text | 30 Characters / Bytes | Make / Brand of Computer Part | - | MSI |
| Part Name / Model | Text | 30 Characters / Bytes | Name of Part | - | NVIDIA GTX 1660 Super |
| Price | Number | 4 Bytes / 32 Bits | Price of Part | Price of Part Cannot be **Lower** than 250 | 3000 |
| Payment Method | Text | 1 Characters / Bytes | How will the Customer Pay | Can either pay with Cash or Finance | C |

### Delivery Table ( Without Foreign Key )

| Field Name | Data Type | Field Size | Description | Validation Rule | Example |
| ---------- | --------- | ---------- | ----------- | --------------- | ------- |
| Delivery ID | AutoNumber | 4 Bytes / 32 Bits | Unique Record Identifier for `tblDelivery` | - | 1 |
| First Name | Text | 30 Characters / Bytes | First Name of Customer | - | Carlos |
| Last Name | Text | 30 Characters / Bytes | Last Name of Customer | - | Sainz |
| Order Date | Date/Time | 8 Bytes / 64 Bits | Store the date when Customer brought Product | Date must be today | 15/10/04 |
| Address 1 | Text | 30 Characters / Bytes | Primary Place of Residence | - | Old Moka Road |
| Mobile Number | Number | 4 Bytes / 32 Bits | Mobile / Phone Number of Customer | Length of Mobile Number should be 8 | 52080842 |
| Part Make | Text | 30 Characters / Bytes | Make / Brand of Computer Part | - | MSI |
| Part Name | Text | 100 Characters / Bytes | Name of Part | - | NVIDIA GTX 1660 Super |
| Price | Number | 4 Bytes / 32 Bits | Price of Part | Price of Part Cannot be **Lower** than 250 | 3000 |

### Delivery Table ( With Foreign Key )

| Field Name | Data Type | Field Size | Description | Validation Rule | Example |
| ---------- | --------- | ---------- | ----------- | --------------- | ------- |
| Delivery ID | AutoNumber | 4 Bytes / 32 Bits | Unique Record Identifier for `tblDelivery` | - | 1 |
| Customer ID | Number | 4 Bytes / 32 Bits | Unique Record Identifier for `tblCustomer` | - | 8 |
| First Name | Text | 30 Characters / Bytes | First Name of Customer | - | Carlos |
| Last Name | Text | 30 Characters / Bytes | Last Name of Customer | - | Sainz |
| Address 1 | Text | 30 Characters / Bytes | Primary Place of Residence | - | Old Moka Road |
| Mobile Number | Number | 4 Bytes / 32 Bits | Mobile / Phone Number of Customer | Length of Mobile Number should be 8 | 52080842 |
| Order Date | Date/Time | 8 Bytes / 64 Bits | Store the date of Delivery | Date must be in the Future or Today | 15/10/04 |
| Part ID | Number | 4 Bytes / 32 Bits | Unique Record Identifier for `tblComputerParts` | - | 1 |
| Part Make | Text | 30 Characters / Bytes | Make / Brand of Computer Part | - | MSI |
| Part Name | Text | 100 Characters / Bytes | Name of Part | - | NVIDIA GTX 1660 Super |
| Price | Number | 4 Bytes / 32 Bits | Price of Part | Price of Part Cannot be **Lower** than 250 | 3000 |

## Business Rules

Customer Table - Order Table

- A `Customer` may have 0 or Many `Orders`
- Each `Order` must be purchased by 1 specific `Customer`

Customer Table - Services Table

- A `Customer` may have 0 or Many `Service`
- Each `Service` must be requested by 1 specific `Customer`

Customer Table - Delivery Table

- A `Customer` may have 0 or Many `Delivery`
- Each `Delivery` is delivered to 0 or Many `Customer`

Services Table - Computer Parts Table

- A `Service` must demand for 1 or More `Computer Part`
- Each `Computer Part` is given to 1 or More `Service`

Computer Parts Table - Stock Parts Table

- A `Computer Part` may be available or out of `Stock`
- Each `Stock` may contains 0 or Many `Computer Part`

## Function and Non-Function Requirements

### List of Functional Requirements

- Stock ( Inventory ) Management
	1. Track Stock Levels of all products and parts
	2. Automatic Update of Stock upon Sales and Restocking
	3. Alerts for Low Stock Levels and Re-order Points
	4. Maintain records of suppliers and purchase orders
- Customer Management
	1. Store and Manage customer information ( contact details, orders of customer )
	2. Track customer interactions and service requests
- Order Management
	1. Proceessing of customer Orders efficiently
	2. Track order Status from placement to delivery
	3. Generate Invoices and Receipts for customer orders
	4. Manage returns and exchanges
- Sales Management
	1. Record and Process sales transactions
	2. Generate sales reports and analytics
	3. Manage discounts, promotions and special offers
- Repair and Maintenance Services
	1. Track repair requests and service orders
	2. Assign technicians to specific repair tasks
	3. Maintain detailed logs of repairs and diagnostic
	4. Notify customers of repair status and completion
- Custom Computer Builds
	1. Capture detailed customer requirements for custom builds
	2. Manage component inventory for custom builds
	3. Track the progress of custom build projects
	4. Provide cost estimates and quotations for custom builds
- Employee Management
	1. Store employee information and job roles
	2. Track attendence and work hours
	3. Manage task assignment and performance evaluations
	4. Handle payroll processing and records
- Supplier Management
	1. Store and Manage supplier information
	2. Track supplier performance and delievery history
	3. Manage purchase orders and suppliers invoices
- Finacial Management
	1. Track company expenses and income
	2. Generate financial reports ( profits / loss statements, balance sheets )
	3. Manage payroll and employee compensation
	4. Handle taxes and compliance documentation
- Reporting and Analytics
	1. Generate various operational reports ( inventory, sales, customer activity )
	2. Export reports to different formats ( PDF, Excel )
- Backup and Recovery
	1. Regularly back up all critical data
	2. Provide data recovery options in case of data loss or corruption
	3. Ensure business continuity with minimal downtime
- User Interface and Experience
	1. Provide an intuitive and user-friendly interface
	2. Ensure responsive design for access on various devices ( desktop, mobiles )
	3. Allow customisation of the user interface as per user roles ( external views )

### List of Non-Functional Requirements

- Performance
	1. Should support many users simultaneously
	2. Low Latency for Queries
- Scalability
	1. System must be scalable to accomodate future growth in the number of users and data volume
	2. Should be easy to add new features and functionalities wihout major system overhauls
- Security
	1. System should ensure secure authentication and authorisation for all users
	2. User Views and Passwords
	3. Data Encryption should be used for sensitive information both in transit and at rest
- Effiency
	1. System should optimise resource utilisation, ensuring efficent use of memory, CPU, and storage.
	2. Batch Processing should be used where applicable to minise resource consumption during peak hours
- Auditability
	1. System should maintain detailed logs of all user activities and system changes
	2. Audit trails should be easily accessible for review and compliance purposes

## Queries

- Customer Information Queries:
    - Find customers who have made a purchase within a specific date range.
    - List customers who have pending orders.
    - Identify top customers based on the total amount spent.
- Order Management Queries:
    - Retrieve all orders placed within a certain period.
    - Find orders that include a specific part or product.
    - List all pending or unfulfilled orders.
    - Generate an order history for a particular customer.
- Inventory Management Queries:
    - Identify parts that are low in stock and need reordering.
    - Retrieve details of parts supplied by a specific vendor.
- Sales and Revenue Queries:
    - Determine the most popular products based on sales volume.
    - Generate sales reports by product category.
    - Analyse sales trends over different months or years.
- Supplier Management Queries:
    - Find the most reliable suppliers based on delivery times and quality.
    - Track purchase orders made to suppliers.
- Employee Management Queries:
    - List employees based on their roles (e.g., technicians, customer support).
    - Identify technicians who have completed the most repairs or builds.
- Service Management Queries:
    - Identify ongoing or pending repair tasks.
    - Generate reports on the most common types of repairs or services requested.
- Financial Queries:
    - Generate profit and loss statements for a specific period.

## Conclusion and Appraisal

### Conclusion

In conclusion, transitioning to an automated database system will resolve the current inefficiencies of Sun's Systems' manual processes. This upgrade will enhance data accuracy, streamline operations, and support the company's growth, ensuring continued high-quality service and customer satisfaction.

### Appraisal

This appraisal will involve the evaluation of the implementation about the new database system. Its purpose it to access its effectiveness in addressing the limitations and challenges of the manual processes.

The new system will significantly reduce the amount of data entry errors and improve processing time.
It should improve the Customer experience/satisfaction and overall efficiency

---

# Socials

- **Instagram**: https://www.instagram.com/s.sunhaloo/
- **YouTube**: https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg
- **GitHub**: https://www.github.com/Sunhaloo

---

S.Sunhaloo
Thank You!
