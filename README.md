

# Ocean Odyssey Database Project

This repository contains my **FIT2094 Databases** project at Monash University.  
The task was to design and implement a relational database for **Ocean Odyssey**, a cruise travel company, covering the full process from conceptual modelling to schema implementation in Oracle.

---

## Overview
Ocean Odyssey manages cruise bookings, ships, passengers, cabins, and ports.  
The project demonstrates my ability to:
- Design a conceptual ERD from a real-world case study.
- Apply normalisation (UNF → 1NF → 2NF → 3NF).
- Convert the conceptual design into a logical model using Oracle SQL Data Modeler.
- Generate and run a physical Oracle schema with constraints and business rules.
- Document assumptions and justify design decisions.

---

## Features
- 10 fully normalised tables in 3NF.  
- 25 constraints (primary keys, foreign keys, unique, and check clauses).  
- Attribute-level comments for clarity.  
- Surrogate keys introduced where composite keys were complex (e.g., Address, Manifest).  
- Enforced business rules such as guardian–passenger relationships and cabin class validation.  
- Successfully executed schema with zero errors/warnings in Oracle.

---

## Project Deliverables
This repository includes:
- `oo_conceptual.pdf` → Conceptual ERD.  
- `oo_normalisation.pdf` → Step-by-step normalisation to 3NF.  
- `oo_logical.pdf` → Logical model in Oracle Data Modeler.  
- `oo_schema.sql` → Generated Oracle schema.  
- `oo_schema_output.txt` → Output showing successful table creation in Oracle.  
- `oo_assumptions.pdf` → Documented assumptions and design choices.  

---

## Results
- A complete, working Oracle relational database ready to manage cruise bookings.  
- Normalised design ensures data integrity, consistency, and reduced redundancy.  
- Applied industry-standard database modelling practices and Oracle SQL implementation.  

---

## Author
**Nashmia Shakeel** 
