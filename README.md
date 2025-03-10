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

<p align="center">
  <em>The initial screen for creating and managing (DDIC) database tables in the ABAP Dictionary.</em><br><br>
  <img src="Screens/ddic.png" alt="Data Dictionary" width="600"/>
</p>

<p align="center">
  <em>Diagram showing the foreign key relationship between ZDEPARTMENT_T and ZEMPLOYEE_T tables.</em><br><br>
  <img src="Screens/erp.png" alt="ERP" width="600"/>
</p>

<p align="center">
  <em>The ZEMPLOYEE_STRUCT structure is used in both the ZEMPLOYEE_T and ZDEPARTMENT_T tables to track metadata. It includes fields like CREATED_BY, CREATED_DATE, CHANGED_BY, and CHANGED_DATE, providing a consistent way to audit who created and modified records and when.</em><br><br>
  <img src="Screens/struct.png" alt="Structure Table" width="600"/>
</p>

<p align="center">
  <em>Structure of the ZEMPLOYEE_T table, detailing fields and data types.</em><br><br>
  <img src="Screens/emp-table.png" alt="Employee Table" width="600"/>
</p>

<p align="center">
  <em>Structure of the ZDEPARTMENT_T table, showing fields and data types.</em><br><br>
  <img src="Screens/dept-table.png" alt="Department Table" width="600"/>
</p>

<p align="center">
  <em>Data element ZEMP_ID for Employee ID, showing its domain and data type.</em><br><br>
  <img src="Screens/de.png" alt="Employee ID Data Element" width="600"/>
</p>

<p align="center">
  <em>Field label settings for the ZEMP_ID data element, detailing different label lengths.</em><br><br>
  <img src="Screens/de-fl.png" alt="Employee ID Field Label" width="600"/>
</p>

<p align="center">
  <em>Display of the ZEMP_GENDER domain, showing the value range for gender options.</em><br><br>
  <img src="Screens/d.png" alt="Gender Domain" width="600"/>
</p>

<p align="center">
  <em>Domain definition for ZEMP_ID, specifying data type and format.</em><br><br>
  <img src="Screens/d-vr.png" alt="Employee ID Domain" width="600"/>
</p>

<p align="center">
  <em>Access the Utilities menu to generate table maintenance events.</em><br><br>
  <img src="Screens/utilities.png" alt="Utilities" width="600"/>
</p>

<p align="center">
  <em>Settings for generating table maintenance dialogs for ZEMPLOYEE_T.</em><br><br>
  <img src="Screens/tmg.png" alt="Table Maintenance Generator" width="600"/>
</p>

<p align="center">
  <em>Navigate the Environment menu to access events and other settings.</em><br><br>
  <img src="Screens/environment.png" alt="Environment" width="600"/>
</p>

<p align="center">
  <em>View and manage form routines for table maintenance in ZEMPLOYEE_T.</em><br><br>
  <img src="Screens/events.png" alt="Events" width="600"/>
</p>

<p align="center">
*********************************************************************************************************<br>
*********************************************************************************************************<br>
*******************************                  VIEWS                    *******************************<br>
*********************************************************************************************************<br>
*********************************************************************************************************<br>
</p>

<h2 align="center">Database View (ZEMPLOYEE_T_DV)</h2>
<p align="center">
  A database view that combines data from employee and department tables, providing a comprehensive view of employee information along with their department details. This view is useful for reporting and data analysis purposes.
</p>

[Database View Screenshots]

<p align="center">
  <em>Database View Configuration showing the join between ZEMPLOYEE_T and ZDEPARTMENT_T tables using DEPT_ID.</em><br><br>
  <img src="Screens/dv-01.png" alt="Database View Join Configuration" width="600"/>
</p>

<p align="center">
  <em>View Fields configuration displaying all fields from both tables with their respective data types and lengths.</em><br><br>
  <img src="Screens/dv-02.png" alt="View Fields Configuration" width="600"/>
</p>

<p align="center">
  <em>Sample data showing the combined employee and department information from the database view.</em><br><br>
  <img src="Screens/dv-03.png" alt="View Sample Data" width="600"/>
</p>

<hr>

<h2 align="center">Projection View (ZEMPLOYEE_T_PV)</h2>
<p align="center">
  A projection view that selects specific fields from the employee table, offering a focused view of employee information. This view is particularly useful when only specific employee attributes are needed.
</p>

[Projection View Screenshots]

<p align="center">
  <em>Projection View Configuration (ZEMPLOYEE_T_PV) shows selected employee table fields with their data elements and properties.</em><br><br>
  <img src="Screens/pv-01.png" alt="Projection View Configuration" width="600"/>
</p>

<p align="center">
  <em>Sample data displaying employee information through the projection view, including personal details and department assignments.</em><br><br>
  <img src="Screens/pv-02.png" alt="Projection View Data" width="600"/>
</p>

<hr>

<h2 align="center">Maintenance View (ZEMPLOYEE_T_MV)</h2>
<p align="center">
  A maintenance view that enables data maintenance while preserving the relationship between employee and department information. This view is designed for data updates and modifications with referential integrity.
</p>

[Maintenance View Screenshots]

<p align="center">
  <em>Maintenance View configuration showing the relationship between Employee and Department tables using DEPT_ID as the join condition.</em><br><br>
  <img src="Screens/mv-01.png" alt="Maintenance View Join Configuration" width="600"/>
</p>

<p align="center">
  <em>View Fields configuration displaying all fields from both tables with their technical specifications including data elements, types, and lengths.</em><br><br>
  <img src="Screens/mv-02.png" alt="Maintenance View Fields" width="600"/>
</p>

<p align="center">
  <em>Sample data display from the Maintenance View (ZEMPLOYEE_T_MV) showing basic employee information and allowing CRUD operations.</em><br><br>
  <img src="Screens/mv-03.png" alt="Maintenance View Data" width="600"/>
</p>

<hr>

<h2 align="center">Help View (ZEMPLOYEE_T_HV)</h2>
<p align="center">
  A help view that provides quick access to essential employee and department information. This simplified view is designed for reference purposes, showing only key fields needed for basic lookups.
  It is used in search help.
</p>

[Help View Screenshots]

<p align="center">
  <em>Help View join configuration displaying the relationship between Employee and Department tables using DEPT_ID field.</em><br><br>
  <img src="Screens/hv-01.png" alt="Help View Join Configuration" width="600"/>
</p>

<p align="center">
  <em>Help View (ZEMPLOYEE_T_HV) field configuration showing selected fields (EMP_ID, EMP_NAME, DEPT_NAME) with their technical details.</em><br><br>
  <img src="Screens/hv-02.png" alt="Help View Fields Configuration" width="600"/>
</p>

<p align="center">
*********************************************************************************************************<br>
*********************************************************************************************************<br>
*********************************** SEARCH HELPS *******************************************************<br>
*********************************************************************************************************<br>
*********************************************************************************************************<br>
</p>

<h2 align="center">Search Help Types Overview</h2>

<h3>Elementary Search Help (ZEMPLOYEE_T_SH)</h3>
<p>
An elementary search help provides basic search functionality for employee data. It allows users to search using key employee fields:
- EMP_ID: Employee identification number
- EMP_NAME: Employee full name
- DEPT_NAME: Department name
Key features:
- Hot key: 'E' for quick access
- Immediate value display
- Supports proposal search for input fields
</p>

<p align="center">
  <em>Elementary Search Help configuration for Employee data showing search parameters and dialog behavior.</em><br><br>
  <img src="Screens/emp-sh.png" alt="Employee Search Help Configuration" width="600"/>
</p>

<h3>Elementary Search Help (ZDEPT_T_SH)</h3>
<p>
Department search help provides focused search capabilities for department information:
- DEPT_ID: Department identification number
- DEPT_NAME: Department name
Key features:
- Hot key: 'D' for quick access
- Direct value display
- Optimized for department lookups
</p>

<p align="center">
  <em>Elementary Search Help configuration for Department data showing search parameters and dialog behavior.</em><br><br>
  <img src="Screens/dept-sh.png" alt="Department Search Help Configuration" width="600"/>
</p>

<h3>Collective Search Help (ZEMP_CSH)</h3>
<p>
A collective search help that combines both employee and department search capabilities:
- Integrates employee search help (ZEMPLOYEE_T_SH)
- Includes department search help (ZDEPT_T_SH)
Benefits:
- Unified search interface
- Flexible search across multiple entities
- Enhanced user experience with combined search options
</p>

<p align="center">
  <em>Collective Search Help configuration showing the integration of both Employee and Department search helps.</em><br><br>
  <img src="Screens/c-sh.png" alt="Collective Search Help Configuration" width="600"/>
</p>





















