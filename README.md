# Clinic Database Management System (CDMS)

This repository contains the database design and implementation details for the Clinic Database Management System (CDMS), developed for HealthyLife Clinic. The system aims to efficiently manage various medical tasks and provide robust data management functions for clinic staff and patients.

## Table of Contents

- [About](#about)
- [Project Objectives](#project-objectives)
- [Target Users](#target-users)
- [Database Design](#database-design)
  - [Entities and Attributes](#entities-and-attributes)
  - [Entity-Relationship Diagram (ERD)](#entity-relationship-diagram-erd)
  - [Business Rules](#business-rules)
- [Database Development](#database-development)
  - [Tables and Records](#tables-and-records)
  - [Switchboard](#switchboard)
- [Database Objects](#database-objects)
  - [Queries](#queries)
  - [Forms](#forms)
  - [Reports](#reports)
- [Future Improvements](#future-improvements)
- [Contributors](#contributors)
- [License](#license)

## About

The Clinic Database Management System (CDMS) is a comprehensive solution designed to streamline the operations of HealthyLife Clinic, a medium-sized clinic experiencing a significant influx of patients. The system is built to efficiently handle patient and doctor information, appointments, medical records, billing, payments, and clinic inventory. It simplifies data retrieval, storage, and management, aiming to increase efficiency for clinic staff and improve the patient experience. 

The system enforces business rules and regulations of HealthyLife Clinic to ensure all clinical tasks are managed appropriately.  It includes forms for data entry, queries for data searching and categorization, and reports for summarizing overall operations to aid management in decision-making. 

## Project Objectives

The primary objectives of this CDMS are:

1.  **Efficient Patient and Doctor Information Management:** To create a user-friendly system for effective data input and retrieval of patient and doctor information, ensuring secure storage and easy access for staff. 
2.  **Improved Diagnosis and Treatment:** To enhance doctors' ability to diagnose and treat patients by providing easily accessible medical history records, facilitating accurate diagnoses, optimal treatment courses, and informed drug prescription decisions. 
3.  **Streamlined Appointment Monitoring:** To offer a simplified way to monitor patient appointment statuses, which will improve clinic operations, enhance staff productivity, reduce wait times, and optimize clinic resources. The system also maintains and secures medical data, guaranteeing prompt and appropriate patient care. 

## Target Users

The CDMS is designed for use by HealthyLife Clinic staff members, including clinic administrators, doctors, and nurses, who are responsible for the administrative and business operations of the clinic. 

## Database Design

The database is constructed using an Entity-Relationship Diagram (ERD) to define relationships and cardinalities between entities, and business rules are established based on HealthyLife Clinic's terms and conditions. 

### Entities and Attributes

The CDMS comprises 15 main tables, each with predefined data types and domain constraints. 

Key entities and some of their attributes include: 

* **Patient:** `Patient_ID` (PK), `Patient_FirstName`, `Patient_LastName`, `Patient_DateOfBirth`, `Patient_Email`, `Patient_PhoneNumber` 
* **Patient_Condition:** `Patient_ID` (PK, FK), `Condition_ID` (PK, FK) 
* **Health_Condition:** `Condition_ID` (PK), `Condition_Description` 
* **Doctor:** `Doctor_ID` (PK), `Doctor_FirstName`, `Doctor_LastName`, `Doctor_DateOfBirth`, `Doctor_Email`, `Doctor_PhoneNumber` 
* **Doctor_Specialty:** `Doctor_ID` (PK, FK), `Specialty_ID` (PK, FK) 
* **Specialty:** `Specialty_ID` (PK), `Specialty_Name` 
* **Availability:** `Availability_ID` (PK), `Doctor_ID` (FK), `Availability_Date`, `Availability_StartTime`, `Availability_EndTime`, `Availability_Status` 
* **Shift:** `Shift_ID` (PK), `Shift_StartTime`, `Shift_EndTime` 
* **Doctor_Shift:** `Shift_ID` (PK, FK), `Doctor_ID` (PK, FK) 
* **Appointment:** `Appointment_ID` (PK), `Doctor_ID` (FK), `Patient_ID` (FK), `Availability_ID` (FK), `Appointment_Purpose`, `Appointment_Status` 
* **Medical_History_Record:** `Record_ID` (PK), `Patient_ID` (FK), `Appointment_ID` (FK), `Record_Diagnosis`, `Record_Test_Result`, `Record_Treatment`, `Record_Prescription` 
* **Expended_Resources:** `Record_ID` (PK, FK), `Inventory_ID` (PK, FK), `Expended_Amount` 
* **Billing_Payment:** `Payment_ID` (PK), `Appointment_ID` (FK), `Patient_ID` (FK), `Payment_Consulation`, `Payment_Treatment`, `Payment_Medication`, `Payment_Total`, `Payment_Method`, `Payment_Status` 
* **Invoice:** `Invoice_ID` (PK), `Payment_ID` (FK), `Invoice_Amount`, `Invoice_Date` 
* **Inventory:** `Inventory_ID` (PK), `Inventory_Name`, `Inventory_Type`, `Inventory_InitialAmount`, `Inventory_CurrentAmount` 

### Entity-Relationship Diagram (ERD)

The ERD is a foundational tool for designing a user-friendly system, ensuring structure coherence and facilitating the conversion of conceptual design into a logical and physical database. It clearly illustrates the relationships and connections between entities using notations like crow's foot, helping to identify potential errors such as many-to-many relationships. 

### Business Rules

The system incorporates various business rules to ensure data integrity and operational efficiency, based on assumptions about how the clinic operates. Examples include:

* Each patient must have a unique `Patient_ID` and can have multiple health conditions recorded. 
* Each appointment must have a unique `Appointment_ID` and be linked to a patient and a doctor’s availability. 
* Each payment must have a unique `Payment_ID`, linked to an appointment, and generates an invoice. 
* Doctors have unique `Doctor_ID`s and their availability, specializations, and shifts are meticulously tracked. 
* Inventory items have unique `Inventory_ID`s, and their usage is tracked and linked to medical history records. 

## Database Development

The database is implemented using Microsoft Access.

### Tables and Records

All relations identified in the ERD are created, with at least 10 records inserted per table (except lookup/composite tables).  Data dictionaries and sample records for each table (e.g., Patient, Patient_Condition, Doctor, Appointment, Inventory, etc.) are included in the project documentation. 

### Switchboard

A switchboard is created to provide a centralized navigation interface, including all tables, forms, queries, and reports. It is configured to start automatically when the database is opened and includes an exit button. 

## Database Objects

The CDMS includes various database objects to facilitate clinic operations:

### Queries

Three relevant queries with corresponding SQL commands are created to extract and analyze data from the database. The purpose of each query is explained. 

### Forms

Three useful forms are developed, which may include subforms. These forms are designed with colors and images to enhance user experience. The purpose of each form is explained. Examples include: 

* Patient Registration Form 
* Appointment Booking Form 
* Billing Payment Form 

### Reports

Three useful reports are generated to summarize clinic data. These reports are designed to be proper and easy to understand. Examples include: 

* Condition of Patient Report 
* Unpaid Report 
* Complete Appointment Report 

## Future Improvements

Potential future improvements for the CDMS include:

* **Comprehensive Training Program:** Develop a comprehensive training program for clinic staff on system usage and management, with periodic training and a communication platform for troubleshooting. 
* **Backup and Recovery Procedures:** Establish routine backup procedures with multiple storage locations (e.g., external hard drives, cloud) and regularly test backup/recovery processes. 
* **Accessibility Features and Accommodations:** Implement and continuously improve accessibility features based on user feedback collected through periodic surveys, eliminating barriers and enhancing usability. 

## Contributors

* **Stanley Chew Jun Xian** (Student ID: 23ABC04421, Programme: CS, Practical Group: 9) 
* **Tee Chi Sheng** (Student ID: 23ACB05145, Programme: CS, Practical Group: 10) 
* **Wong Carman** (Student ID: 23ACB05293, Programme: CT, Practical Group: 18) 
* **Kuik Kim Hong** (Student ID: 22ACB04878, Programme: CS, Practical Group: 9) 

## License

This project was developed as part of the UCCD1203 Database Development and Applications course at Universiti Tunku Abdul Rahman for the Academic Year 2023/2024, June Trimester.