# Crowdfunding ETL Project

## Project Overview

This project focuses on building an Extract, Transform, and Load (ETL) pipeline to process crowdfunding campaign data. The data originates from an Excel file (`crowdfunding.xlsx`) and is transformed into structured CSV files, which are then loaded into a PostgreSQL database.

## Project Structure
* **`README.md`**: This file, providing an overview of the project.
* **`crowdfunding.xlsx`**: The original Excel data source for campaign, category, and subcategory information.
* **`contacts.xlsx`**: The original Excel data source for contact information.
* **`Category.csv`**: CSV file containing category data.
* **`Subcategory.csv`**: CSV file containing subcategory data.
* **`contacts.csv`**: CSV file containing transformed contact data.
* **`Campaign.csv`**: CSV file containing cleaned campaign data.
* **`crowdfunding_db_schema.sql`**: SQL file containing the database schema.
* **`crowdfunding_db.sql`**: SQL file containing crouwdfunding database.  

## ETL Process

1.  **Extraction:**
    * Data was extracted from `crowdfunding.xlsx` using Pandas for campaign, category, and subcategory information.
    * Contact data was extracted from `contacts.xlsx` using Pandas.
2.  **Transformation:**
    * Data cleaning and transformation were performed using Pandas.
    * Categories and subcategories were extracted and organized.
    * Campaign data was cleaned, transformed, and merged with category and subcategory data.
    * Contacts data was transformed using Python dictionaries, including splitting names into first and last names.
    * Unwanted columns were dropped.
    * Data types were converted as needed.
    * Date and time formats were standardized.
3.  **Loading:**
    * Transformed data was exported to CSV files.
    * A PostgreSQL database (`crowdfunding_db`) was created.
    * Tables were created based on the ERD and schema defined in `crowdfunding_db_schema.sql`.
    * CSV data was loaded into the PostgreSQL tables.

## Database Schema (ERD)

An Entity-Relationship Diagram (ERD) was created using QuickDBD to visualize the relationships between the tables.

* **Category:** `category_id` (PK), `category`
* **Subcategory** `subcategory_id` (PK), `subcategory`
* **Contacts:** `contact_id` (PK), `first_name`, `last_name`, `email`
* **Campaign:** `cf_id` (PK), `contact_id` (FK), `company_name`, `description`, `goal`, `pledged`, `outcome`, `backers_count`, `country`, `currency`, `launch_date`, `end_date`, `category_id` (FK), `subcategory_id` (FK)
