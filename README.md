# Ocean Odyssey Database Project

A FIT2094 Databases project at Monash University: designing and implementing a relational database for Ocean Odyssey, a cruise travel company, covering the full process from conceptual modelling through normalisation to physical schema implementation in Oracle.

---

## Overview

Ocean Odyssey manages cruise bookings, ships, passengers, cabins, and ports. This project demonstrates:

- Designing a conceptual ERD from a real-world case study
- Applying formal normalisation (UNF → 1NF → 2NF → 3NF)
- Converting the conceptual design into a logical model using Oracle SQL Data Modeler
- Generating and executing a physical Oracle schema with constraints and business rules
- Documenting assumptions and justifying design decisions

---

## Normalisation (UNF → 3NF)

Formally normalised the CRUISE/ITINERARY relation from an unnormalised form containing repeating port and country attributes:

- **1NF:** Split into `CRUISE(cruise_id, cruise_name, cruise_cost_per_person)` and `ITINERARY(cruise_id, date_time, port_code, port_name, port_latitude, port_longitude, country_code, country_name, dep_arr)`, with no partial dependencies present
- **2NF:** Identified transitive dependencies — `port_code → port_name, port_latitude, port_longitude, country_code, country_name` and `country_code → country_name`
- **3NF:** Resolved transitive dependencies by extracting `PORT(port_code, port_name, port_latitude, port_longitude, country_code)` and `COUNTRY(country_code, country_name)` into separate relations, leaving `ITINERARY` with only `cruise_id, date_time, port_code, dep_arr`

---

## Design Decisions & Assumptions

- **PASSENGER → ADDRESS:** Modelled as many-to-one, since multiple passengers can share the same address (e.g. family members travelling together)
- **SHIP → CRUISE:** Modelled as many-to-one, assuming every ship operates at least one cruise
- **CRUISE → ITINERARY:** Modelled as one-to-many, assuming every cruise has at least one itinerary stop
- **Surrogate keys:** Added to `ADDRESS` (composite key of 5 attributes: street, street number, town, postcode, country) and `MANIFEST` (composite key of 3 attributes: cruise_id, pass_id, board_date_time), following the convention of introducing a surrogate key when a natural composite key exceeds two attributes — simplifying foreign key references throughout the schema

---

## Features

- **10 fully normalised tables in 3NF:** ADDRESS, CABIN, COUNTRY, CRUISE, ITINERARY, MANIFEST, OPERATOR, PASSENGER, PORT, SHIP
- **25 constraints** — primary keys, foreign keys, unique constraints, and check clauses (e.g. cabin class restricted to Balcony/Interior/Ocean View/Suite; itinerary dep/arr restricted to Depart/Arrive)
- Attribute-level comments on every column for clarity
- Enforced business rules including guardian–passenger self-referencing relationships and cabin class validation
- Schema executed successfully in Oracle with **zero errors and zero warnings**

---

## Project Deliverables

| File | Purpose |
|---|---|
| `oo_conceptual.pdf` | Conceptual ERD |
| `oo_normalisation.pdf` | Step-by-step normalisation to 3NF |
| `oo_logical.pdf` | Logical model (Oracle SQL Data Modeler) |
| `oo_schema.sql` | Generated Oracle schema (DDL) |
| `oo_schema_output.txt` | Execution output confirming successful table creation |
| `oo_assumptions.pdf` | Documented assumptions and design justifications |

---

## Results

- A complete, working Oracle relational database ready to manage cruise bookings
- Normalised design (3NF) ensures data integrity, consistency, and reduced redundancy
- Applied industry-standard database modelling practices from conceptual design through physical implementation

---

## Author

Nashmia Shakeel
