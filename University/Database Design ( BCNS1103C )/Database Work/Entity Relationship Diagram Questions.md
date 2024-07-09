---
Alias: Database Design ( Entity Relationship Diagram ) - Week 3
Tag: uni, db
Module: BSNC1103C / DBT1103C
Author: S.Sunhaloo
Date: 2024-06-01
Status: In-Progress
---

>[!note]
>This markdown file is related to [[Entity Relationship Diagram ( ERD ) and Relationships]]

## List of Contents

- [[Entity Relationship Diagram Questions#Question 1 | Question 1]]
- [[Entity Relationship Diagram Questions#Question 2 | Question 2]]
- [[Entity Relationship Diagram Questions#Question 3 | Question 3]]
- [[Entity Relationship Diagram Questions#Question 4 | Question 4]]
- [[Entity Relationship Diagram Questions#Question 5 | Question 5]]

---

### My Links

- [[Entity Relationship Diagram Questions#Socials | Link to Social]]

---

# Question 1

A company has a **number** of *employees*. The **attributes** of `EMPLOYEE` includes *Employee_ID*, *Name*, *Address*, and *Birthdate*. The company also has **several** `PROJECTS`; which has **attributes** *Project_ID*, *Project_Name*, *Start_Date*. Each employee **may** be assigned to 1 or more projects, or may not be assigned to any projects. A project **must** have at least 1 employee, and may have any number of employees assigned. An employee billing rate may vary by project, and the company wishes to record the applicable billing rate ( *Billing_Rate* ) for each employee when assigned to a particular object.

![[Database Questions ERD - Week 3 - Question 1.png]]

# Question 2

A university has a large number of *courses* in its catalog. **Attributes** of `COURSE` include *Course_Number*, *Course_Name*, *Units*. Each course **may** have 1 or more different courses as [prerequisites](https://www.google.com/search?q=what+is+the+meaning+of+prerequisite&oq=what+is+the+meaning+of+prerequisite&gs_lcrp=EgZjaHJvbWUqCQgAEAAYDRiABDIJCAAQABgNGIAEMgkIARAAGA0YgAQyCQgCEAAYDRiABDIJCAMQABgNGIAEMgkIBBAAGA0YgAQyCQgFEAAYDRiABDIICAYQABgWGB4yCAgHEAAYFhgeMggICBAAGBYYHjIKCAkQABgPGBYYHtIBCDc0ODhqMGo3qAIAsAIA&sourceid=chrome&ie=UTF-8), or may have no prerequisites. Similarly, a particular course may be a prerequisite for any number of courses or may not be prerequisite for any other courses.

![[Database Questions ERD - Week 3 - Question 2.png]]

>[!warning]
>*Course_Number* and *Prerequsite_ID* should have been **<u>Underlined</u>**!!!

# Question 3

 A college course **may** have 1 or more scheduled sections, or may not have a scheduled section. **Attributes** of `COURSE` includes *Course_ID*, *Course_Name*, *Units*. Attributes of `SECTION` includes *Section_Number*, *Semester_ID*; the *Semester_ID* is composed of 2 parts: *Semester_Year* and *Semester_Number* which are integers that distinguishes 1 section from another for the same course but does not uniquely identify a section.

![[Database Questions ERD - Week 3 - Question 3.png]]

# Question 4

A hospital has a large number of registered physicians. **Attributes** of `PHYSICIAN` includes *Physician_ID* and *Specialty*. Patients are admitted to the hospital by physicians. **Attributes** of `PATIENTS` includes *Patient_ID* and *Patient_Name*. Any patient who is admitted **must** have exactly 1 admitting physician. A physician **may** optionally admit a number of patients. Once admitted, a given patient must be treated by at least one physician. A particular physician **may** treat any number, or may **not** treat any patients. Whenever a patient is treated by a physician, the hospital wishes to record the details of the treatment ( *Treatment_Detail* ). Components of *Treatment_Details* includes *Date*, *Time* and *Results*.



# Question 5

A laboratory has several chemist who work on 1 or more projects. Chemists may also use certain kinds of equipment on each project. **Attributes** of `CHEMIST` includes *Employee_ID*, *Name*, and *Phone_No*. **Attributes** of `PROJECT` includes *Project_ID* and *Start_Date*. Attributes of `EQUIPMENT` include *Serial_No*, *Cost*. The organisation wishes to record *Assign_Date* i.e the date when a given equipment item was assigned to a particular chemist working on a specified project. A chemist must be assigned to **at least** 1 project and 1 equipment item. A given equipment item need not be assigned, and a given project need not be assigned either a chemist or an equipment item.



---

# Socials

- [**Instagram**](https://www.instagram.com/s.sunhaloo/)
- [**YouTube**](https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg)
- [**GitHub**](https://www.github.com/Sunhaloo)

---

S.Sunhaloo
Thank You!