# ReadMore Library Database Design

## Overview
This project focuses on the end-to-end design and implementation of a relational database system for a multi-branch community library.

Starting from a set of business requirements, the project walks through the full database design lifecycle — from conceptual modelling to logical design, and finally to SQL schema implementation.

The goal was to design a structured, scalable system capable of managing library operations such as catalogue management, borrowing, reservations, and branch-level inventory tracking.

---

## Project Scope

The database was designed to support:

- Library branches operating across multiple LGAs
- Centralised catalogue with multiple book editions (ISBN-based)
- Physical book copy tracking across branches
- Borrower management with classification and borrowing rules
- Loan lifecycle tracking (borrow, return, overdue handling)
- Reservation system for unavailable book copies

---

## Project Structure

### 1. Conceptual Design
- `conceptual_model.pdf`
- `design_assumptions.pdf`

Initial entity-relationship model (ERD) built from business requirements.  
Defines key entities such as branches, catalogue entries, books, borrowers, and loans, along with their relationships and constraints.

---

### 2. Normalisation
- `normalisation.pdf`

Step-by-step transformation of unstructured data into Third Normal Form (3NF), including:

- UNF → 1NF → 2NF → 3NF
- Identification of partial and transitive dependencies
- Decomposition into well-structured relational tables

---

### 3. Logical Data Model
- `logical_model.pdf`
- `implementation_assumptions.pdf`

Refined relational model derived from the conceptual design and normalisation process.

Key features:
- Resolution of many-to-many relationships using bridge tables
- Separation of catalogue, book editions, and physical copies
- Introduction of reservation and loan tracking systems
- Use of surrogate keys where appropriate for performance and integrity

---

### 4. Database Implementation
- `schema.sql`
- `schema_output.txt`

Oracle SQL schema generated from the logical model.

Includes:
- Primary and foreign key constraints
- Check constraints enforcing business rules
- Unique constraints for data integrity
- Column-level documentation using SQL comments

The `schema_output.txt` file demonstrates successful execution of the schema.

---

## Key Design Decisions

- **Separation of Book vs Book Copy**  
  Logical distinction between ISBN-level data and physical inventory tracking.

- **Use of Bridge Tables**  
  Many-to-many relationships (e.g. authors, subjects, publishers) were resolved using linking tables.

- **Surrogate Key Implementation**  
  A surrogate key (`book_copy_sk`) was introduced to simplify relationships involving composite keys.

- **Business Rule Enforcement via Constraints**  
  Borrower classes, book status, and loan conditions were enforced directly at the database level.

---

## Tools & Technologies

- Oracle Data Modeler
- Oracle SQL
- Relational Database Design Principles (Normalization up to 3NF)

---

## What This Project Demonstrates

- Translating business requirements into structured data models
- Applying normalization techniques to real-world data
- Designing scalable relational schemas
- Implementing data integrity through constraints
- Understanding the full lifecycle of database development

---

## Notes

This project has been adapted from an academic assignment and restructured for portfolio presentation.
All identifying academic information has been removed, and the focus has been placed on technical design and implementation.