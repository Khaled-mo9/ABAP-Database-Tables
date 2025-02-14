# ABAP-Database-Tables

Repository for managing and documenting SAP DDIC database tables. Includes table definitions, data elements, domain structures, and related ABAP code for data manipulation and integration.

## Introduction

This project is designed to streamline the management of employee and department data within SAP systems, ensuring data integrity and consistency.

## SAP DDIC Project: Employee and Department Tables

### Description

This project involves the creation and management of two SAP DDIC (Data Dictionary) tables: `ZEMPLOYEE_T` (Employee) and `ZDEPARTMENT_T` (Department). The SAP Data Dictionary is a central repository for metadata in SAP systems, providing a structured way to define and manage data objects.

### What is DDIC?

The SAP Data Dictionary (DDIC) is a crucial component of the SAP system, used to define and manage data structures. It ensures data consistency and integrity across the system by providing:

- **Centralized Data Definitions**: DDIC allows for the centralized definition of data elements, tables, views, and more, ensuring uniformity across applications.
- **Data Integrity**: DDIC helps maintain data integrity and consistency by defining relationships and constraints.
- **Performance Optimization**: Properly defined data structures can improve system performance and retrieval efficiency.

### Naming Conventions

- Every object, including tables and other data structures, should start with `Z` or `X` to indicate custom development.

### Relevant SAP Transaction Codes

- **SE11**: Data Dictionary - Use to create and manage data dictionary objects.
- **SE14**: Database Utility - Use for database table maintenance tasks like adjusting, deleting, or activating tables.
- **SE12**: Data Dictionary Display - Use to view table definitions.
- **SE16N**: General Table Display - Use to view and analyze table data.
- **SM30**: Table View Maintenance - Use to maintain table entries.

### Project Overview

#### `ZEMPLOYEE_T` Table

- **Purpose**: Stores employee information.
- **Key Fields**:
  - `MANDT`: Client
  - `EMP_ID`: Employee ID
  - `EMP_NAME`: Employee Name
  - `EMP_DOB`: Date of Birth
  - `EMP_GENDER`: Gender
  - `EMP_EMAIL`: Email Address
  - `EMP_PHONE`: Phone Number
  - `EMP_HIRE_DATE`: Hire Date
  - `DEPT_ID`: Department ID
  - `JOB_TITLE`: Job Title
  - `SALARY`: Salary
  - `MANAGER_ID`: Manager ID
  - `ADDRESS`: Address
  - `EMERGENCY_CONTACT`: Emergency Contact Name
  - `EMERGENCY_PHONE`: Emergency Contact Phone
  - `CREATED_BY`: Created By
  - `CREATED_DATE`: Created Date
  - `CHANGED_BY`: Changed By
  - `CHANGED_DATE`: Changed Date

#### `ZDEPARTMENT_T` Table

- **Purpose**: Stores department information.
- **Key Fields**:
  - `DEPT_ID`: Department ID
  - `DEPT_NAME`: Department Name
  - `LOCATION`: Location
  - `CREATED_BY`: Created By
  - `CREATED_DATE`: Created Date
  - `CHANGED_BY`: Changed By
  - `CHANGED_DATE`: Changed Date

#### `ZEMPLOYEE_STRUCT` Table

- **Purpose**: Used to track metadata for audit purposes in both `ZEMPLOYEE_T` and `ZDEPARTMENT_T` tables.

- **Key Fields**:
  - `CREATED_BY`: The user who created the entry
  - `CREATED_DATE`: Date of creation
  - `CHANGED_BY`: User who last modified the entry
  - `CHANGED_DATE`: Date of last modification

## Screens from Project:
  
*The initial screen for creating and managing **(DDIC)** database tables in the ABAP Dictionary.*

![Data Dictionary](Screens/ddic.png)

*Diagram showing the foreign key relationship between `ZDEPARTMENT_T` and `ZEMPLOYEE_T` tables.*

![ERP](Screens/erp.png)

*The ZEMPLOYEE_STRUCT structure is used in both the ZEMPLOYEE_T and ZDEPARTMENT_T tables to track metadata.
It includes fields like CREATED_BY, CREATED_DATE, CHANGED_BY, and CHANGED_DATE,
providing a consistent way to audit who created and modified records and when.*

![Structure Table](Screens/struct.png)

*Structure of the `ZEMPLOYEE_T` table, detailing fields and data types.*

<p align="center">
  <img src="Screens/emp-table.png" alt="Employee Table" width="600"/>
</p>

*Structure of the `ZDEPARTMENT_T` table, showing fields and data types.*

![Department Table](Screens/dept-table.png)

*Data element `ZEMP_ID` for Employee ID, showing its domain and data type.*

![Employee ID Data Element](Screens/de.png)

*Field label settings for the `ZEMP_ID` data element, detailing different label lengths.*

![Employee ID Field Label](Screens/de-fl.png)

*Display of the `ZEMP_GENDER` domain, showing the value range for gender options.*

![Gender Domain](Screens/d.png)

*Domain definition for `ZEMP_ID`, specifying data type and format.*

![Employee ID Domain](Screens/d-vr.png)

*Access the Utilities menu to generate table maintenance events.*

![Utilities](Screens/utilities.png)

*Settings for generating table maintenance dialogs for `ZEMPLOYEE_T`.*

![Table Maintenance Generator](Screens/tmg.png)

*Navigate the Environment menu to access events and other settings.*

![Environment](Screens/environment.png)

*View and manage form routines for table maintenance in `ZEMPLOYEE_T`.*

![Events](Screens/events.png)
