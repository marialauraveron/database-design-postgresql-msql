# Database Design and Implementation — PostgreSQL and MySQL

## Project Description

This project simulates a real-world Data Engineering scenario for a coffee shop chain based in New York that plans to expand nationwide by opening new franchise locations.

The company currently stores its information across different systems and formats, including spreadsheets, CSV files, Point of Sale (POS) systems, Customer Relationship Management (CRM) systems, and supplier databases.

The goal of the project is to design and implement a centralized relational database that enables the company to organize and manage its data efficiently and facilitates access to information to support business decision-making.

The project was developed using PostgreSQL and MySQL.

**Context:** Practical project developed as part of the IBM Data Engineering program, based on a simulated business scenario.

---

## Database Design

The database structure was designed using an Entity-Relationship Diagram (ERD) in pgAdmin.

### Entity-Relationship Diagram

![Database ERD](ERD/database_erd.jpg)

---

## Project Objectives

The main objectives of the project were:

* Identify the entities and attributes present in the data.
* Design a relational data model.
* Create an Entity-Relationship Diagram (ERD).
* Normalize the tables.
* Define primary and foreign keys.
* Establish relationships between the different entities.
* Create database objects using SQL.
* Implement the database using PostgreSQL.
* Create views and materialized views.
* Export data subsets.
* Import data into MySQL using phpMyAdmin.

---

## Data Sources

The information used in the project comes from different sources:

* Headquarters (HQ) spreadsheets: staff information.
* Headquarters (HQ) spreadsheets: sales outlet information.
* POS system: sales data in CSV format.
* CRM system: customer data in CSV format.
* Supplier database: product information.

The project involves centralizing these data sources into a relational database.

---

## Technologies and Tools

* PostgreSQL
* MySQL
* SQL
* pgAdmin
* phpMyAdmin
* CSV

---

## Repository Structure

The repository is organized as follows:

* **ERD/** — Contains the Entity-Relationship Diagram (ERD) of the database.
* **PostgreSQL/** — Contains the SQL scripts used to create the database structure and load the data.
* **exports/** — Contains the datasets exported from the PostgreSQL view and materialized view.

### PostgreSQL Files

* **`GeneratedScript.sql`** — Contains the SQL script generated from the ERD to create the database tables, primary keys, foreign keys, and relationships.
* **`CoffeeData.sql`** — Contains the data used to populate the PostgreSQL database.

### Exported Data

* **`staff_locations_view.csv`** — Contains the data exported from the PostgreSQL view created to provide staff and location information.
* **`product_info_m-view.csv`** — Contains the data exported from the PostgreSQL materialized view created to provide product information.

---

## Database Tables

The PostgreSQL database includes the following tables:

* `staff`
* `sales_outlet`
* `customer`
* `sales_transaction`
* `sales_detail`
* `product`
* `product_type`

### Table Description

| Table               | Description                                                 |
| ------------------- | ----------------------------------------------------------- |
| `staff`             | Stores information about the coffee shop employees.         |
| `sales_outlet`      | Stores information about the different sales locations.     |
| `customer`          | Stores customer information.                                |
| `sales_transaction` | Stores information about sales transactions.                |
| `sales_detail`      | Stores the details associated with each sales transaction.  |
| `product`           | Stores information about the products sold by the company.  |
| `product_type`      | Stores information used to classify the different products. |

---

## Keys and Relationships

Primary keys and foreign keys were defined to maintain data integrity and establish relationships between the tables.

### Primary Keys

| Table               | Primary Key       |
| ------------------- | ----------------- |
| `staff`             | `staff_id`        |
| `sales_outlet`      | `sales_outlet_id` |
| `customer`          | `customer_id`     |
| `sales_detail`      | `sales_detail_id` |
| `product`           | `product_id`      |
| `product_type`      | `product_type_id` |
| `sales_transaction` | `transaction_id`  |

### Foreign Key Relationships

* `sales_transaction.staff_id` → `staff.staff_id`
* `sales_transaction.sales_outlet_id` → `sales_outlet.sales_outlet_id`
* `sales_transaction.customer_id` → `customer.customer_id`
* `sales_detail.transaction_id` → `sales_transaction.transaction_id`
* `sales_detail.product_id` → `product.product_id`
* `product.product_type_id` → `product_type.product_type_id`

The relationships defined in the ERD were implemented as foreign key constraints in the SQL script generated by pgAdmin.

---

## Views and Materialized Views

As part of the project, a view and a materialized view were created in PostgreSQL to prepare specific subsets of data for business use.

* **`staff_locations_view`** — Combines staff and sales outlet information to provide a structured view of employees and their locations.
* **`product_info_m-view`** — Materialized view created to provide structured product information.

The resulting datasets were exported as CSV files and are available in the `exports/` folder.

---

## MySQL Implementation

As part of the project, the exported datasets were imported into a MySQL database using phpMyAdmin.

This step provided practical experience working with different relational database management systems and transferring data between PostgreSQL and MySQL environments.

---

## Key Learnings

Through this project, I gained practical experience in:

* Relational database design and data modeling.
* Identifying entities and attributes.
* Creating Entity-Relationship Diagrams (ERD).
* Database normalization.
* Defining primary and foreign keys.
* Establishing relationships between tables.
* Working with SQL and PostgreSQL.
* Creating views and materialized views.
* Exporting data to CSV files.
* Importing data into MySQL using phpMyAdmin.
* Working with data from multiple sources and formats.
