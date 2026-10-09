# Periodic Table Database

A command-line interface application built with **Bash** and **PostgreSQL** that queries and displays detailed chemical properties of periodic table elements. This project fulfills the final requirements for the **freeCodeCamp: Relational Database Certification**.

---

## Overview

The application accepts an element's atomic number, symbol, or full name as a command-line argument. It queries a normalized PostgreSQL database and outputs the element's atomic mass, melting point, boiling point, and chemical type in a standardized format.

---

## Features

- **Multi-Input Lookup:** Query elements flexibly using atomic number (e.g., `1`), chemical symbol (e.g., `H`), or full name (e.g., `Hydrogen`).
- **Normalized Schema:** Utilizes relational database architecture with primary and foreign key constraints linking `elements`, `properties`, and `types`.
- **Input Validation & Error Handling:** Outputs specific prompts when arguments are omitted or when queried elements do not exist in the database.
- **Git Version Controlled:** Built and tracked across structured Git commits following project specifications.

---

## Database Architecture

The PostgreSQL database (`periodic_table`) consists of three interconnected tables:

- **`types`**:
  - `type_id` (SERIAL, PRIMARY KEY)
  - `type` (VARCHAR)
- **`elements`**:
  - `atomic_number` (INT, PRIMARY KEY)
  - `symbol` (VARCHAR, UNIQUE)
  - `name` (VARCHAR, UNIQUE)
- **`properties`**:
  - `atomic_number` (INT, PRIMARY KEY, FOREIGN KEY -> `elements.atomic_number`)
  - `type_id` (INT, FOREIGN KEY -> `types.type_id`)
  - `atomic_mass` (DECIMAL)
  - `melting_point_celsius` (NUMERIC)
  - `boiling_point_celsius` (NUMERIC)

---

## Repository Files

- **`element.sh`**: The executable Bash script that queries PostgreSQL and formats terminal output.
- **`periodic_table.sql`**: Full database dump containing the complete schema, data fixes, and element properties.

---

## Getting Started

### Prerequisites

- **Bash Shell** (Linux/macOS or WSL on Windows)
- **PostgreSQL** (v12 or higher)

### Setup & Usage

1. **Clone the Repository:**
   ```bash
   git clone [https://github.com/](https://github.com/)<your-username>/periodic-table-database.git
   cd periodic-table-database
