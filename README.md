# SQL Challenge - Employee Data Analysis

## Project Overview

This project, part of your role as a Data Engineer at Pewlett Hackard (a fictional company), focuses on analyzing employee data from the 1980s and 1990s. Your primary tasks include designing a SQL database, importing historical employee data from six CSV files, and performing a variety of queries to answer specific business questions. The project is divided into three major components: Data Modeling, Data Engineering, and Data Analysis.

## Table of Contents

1. [Background](#background)
2. [Files](#files)
3. [Technologies Used](#technologies-used)
4. [Project Structure](#project-structure)
5. [Data Modeling](#data-modeling)
6. [Data Engineering](#data-engineering)
7. [Data Analysis](#data-analysis)
8. [How to Use](#how-to-use)
9. [Submission](#submission)
10. [Contact](#contact)

## Background

Pewlett Hackard retained employee data from the 1980s and 1990s in six CSV files, which contain information such as employee details, salary, department, and manager information. The aim is to build a relational database to store this data and then run queries to extract valuable insights.

### Key Tasks:

1. **Data Modeling**: Create an Entity Relationship Diagram (ERD) to define relationships between the data.
2. **Data Engineering**: Design table schemas, create tables, and import CSV data into the tables.
3. **Data Analysis**: Perform SQL queries to answer specific business questions related to employee data.

## Files

The following files are used in this project:

1. **CSV Files**: The data for this project is spread across six CSV files (employees, departments, etc.).
2. **ERD Image**: An image of the Entity Relationship Diagram showing the relationships between the tables.
3. **SQL Files**:
    - `schema.sql`: Contains SQL statements for creating tables.
    - `queries.sql`: SQL queries to extract data for analysis.

## Technologies Used

- **SQL**: For database management and data analysis.
- **PostgreSQL/MySQL/SQLite**: Any of these relational databases can be used.
- **Entity Relationship Diagram Tool**: Tools like QuickDBD or dbdiagram.io can be used for ERD creation.
- **Python (optional)**: If scripting is needed for data transformation.

## Project Structure

```bash
sql-challenge/
│
├── EmployeeSQL/                   # Project directory
│   ├── data/                      # CSV files directory
│   │   ├── employees.csv
│   │   ├── departments.csv
│   │   └── ...
│   ├── schema.sql                 # SQL file for creating database schema
│   ├── queries.sql                # SQL file for running data analysis queries
│   └── erd.png                    # Image file of the ERD
│
├── README.md                      # This README file
└── .gitignore                     # Git ignore file
```

## Data Modeling

In this part of the project, you will:

1. **Inspect CSV Files**: Review the structure and contents of the provided CSV files.
2. **Create an Entity Relationship Diagram (ERD)**: Use a tool like QuickDBD to visualize the relationships between the tables.
3. **Define Relationships**: Identify primary keys, foreign keys, and relationships between entities (tables).

### ERD Overview:

- **Employees Table**: Stores employee data with a unique `employee_id` as the primary key.
- **Departments Table**: Stores department data with a unique `department_id` as the primary key.
- **Salaries Table**: Stores salary data linked to employees via `employee_id`.
- **Department_Managers Table**: Associates department managers with departments and employees.
- **Department_Employees Table**: Links employees with departments.

## Data Engineering

1. **Define Table Schemas**: For each CSV file, create a corresponding SQL table schema. This will involve setting appropriate data types, primary keys, foreign keys, and constraints (like `NOT NULL`).
   
2. **Create Tables**: Write SQL commands to create each table in the correct order to handle foreign key relationships.

3. **Import Data**: Use SQL commands to load data from the CSV files into the respective tables.

### Example Table Schema for `employees`:

```sql
CREATE TABLE employees (
    emp_no INT PRIMARY KEY,
    birth_date DATE NOT NULL,
    first_name VARCHAR(50) NOT NULL,
    last_name VARCHAR(50) NOT NULL,
    gender CHAR(1),
    hire_date DATE NOT NULL
);
```

## Data Analysis

After setting up the database, perform the following analysis:

1. **List employee details**: Employee number, last name, first name, gender, and salary of each employee.
2. **Employees hired in 1986**: First name, last name, and hire date for employees hired in that year.
3. **List managers**: Manager details including department number, department name, and employee details.
4. **List employees and their departments**: Department number, employee number, last name, and department name.
5. **Find employees with specific names**: Employees named Hercules with last names starting with 'B'.
6. **List Sales department employees**: Employee number, last name, and first name.
7. **List Sales and Development employees**: Employees from both departments.
8. **Frequency count of last names**: Count of employees with the same last name.

### Example Query:

```sql
SELECT emp_no, last_name, first_name, gender, salary
FROM employees
JOIN salaries ON employees.emp_no = salaries.emp_no;
```

## How to Use

1. **Clone the Repository**:

   ```bash
   git clone https://github.com/yourusername/sql-challenge.git
   cd sql-challenge
   ```

2. **Database Setup**:
    - Load `schema.sql` to create the database and tables.
    - Import the CSV data into the tables.

3. **Run Queries**:
    - Execute the queries in `queries.sql` to extract the required data.

## Submission

Make sure to submit the following:

1. **ERD Image**: An image file showing your Entity Relationship Diagram.
2. **Schema File**: A `.sql` file containing the SQL commands used to create your tables.
3. **Query File**: A `.sql` file with the queries used to analyze the data.
4. **Regular Commits**: Ensure your GitHub repository shows regular progress.

## Contact

For any queries or issues related to this project, feel free to contact:

- **Name**: [Your Name]
- **Email**: [Your Email]
- **GitHub**: [Your GitHub Username]

---

Happy coding!
