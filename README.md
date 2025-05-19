# Exploration of Gun Violence Incidents (2013–2018)

This repository contains the project developed for the *Laboratory of Data Science* module, within the *Decision Support Systems* course.

The full documentation of the project is available in **`report.pdf`**.

---

## Project Overview

The goal of the project is to explore and analyze incidents of gun violence in North America between 2013 and 2018. The pipeline follows a classical **ETL (Extract, Transform, Load)** structure:

- **Extract** raw data from heterogeneous sources (CSV, XML, JSON).
- **Transform** it using Python and SSIS workflows.
- **Load** it into a relational database and a multidimensional cube for OLAP analysis.

The project is divided into three parts, each with specific deliverables and technologies.

---

## Part 1 – Data Preparation and Database Population

**Objective**: Design a normalized database schema and populate it starting from multiple data formats.

Key steps:
- Creation of the database schema in SQL Server.
- Python scripts for:
  - Parsing and cleaning `.csv`, `.xml`, `.json` files.
  - Generating intermediate tables: `geography`, `date`, `participant`, `gun`, `incident`, and `custody`.
  - Computing attributes like `crime_gravity`.
- Efficient data loading into SQL Server using `pyodbc` and `fast_executemany`.

---

## Part 2 – ETL with SSIS

**Objective**: Solve data analysis problems through client-side computation using **SQL Server Integration Services (SSIS)**.

ETL workflows include:
- **Assignment 0**: Count custodies of young participants by gun type.
- **Assignment 1**: Identify cities with crime gravity above the average of their country.
- **Assignment 2**: Determine the gun type with the highest crime gravity for each state.

> All transformations are handled visually in SSIS using control and data flow components — **no SQL queries are used** in this part.

---

## Part 3 – OLAP Analysis and Dashboards

**Objective**: Create a data cube and answer business questions using **MDX queries** in **SQL Server Analysis Services (SSAS)**.

Key steps:
- Cube creation with appropriate hierarchies (e.g., date, geography).
- Automatic and custom measures: `crime_gravity`, `custody_count`.
- MDX queries implemented:
  1. City with highest crime gravity per country.
  2. Incident with highest crime-to-average ratio.
  3. Quarter-over-quarter crime gravity changes per city.
- Power BI dashboards visualizing:
  - Geographic distribution of crime gravity by age group.
  - Weekly and quarterly trends, gender and weapon-based analysis.

---
