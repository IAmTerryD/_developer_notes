In SQL, a one-to-many relationship is a type of relationship between two tables where a record in one table can be related to multiple records in another table, but a record in the second table is related to only one record in the first table. This relationship is established using a foreign key in the "many" side table that references the primary key in the "one" side table.

Here's a simple example with two tables: "departments" and "employees."

Create the "departments" table:

sql
Copy code
CREATE TABLE departments (
    department_id INT PRIMARY KEY,
    department_name VARCHAR(50),
    -- Other department-related columns
);
Create the "employees" table:

sql
Copy code
CREATE TABLE employees (
    employee_id INT PRIMARY KEY,
    employee_name VARCHAR(100),
    department_id INT,
    -- Other employee-related columns
    FOREIGN KEY (department_id) REFERENCES departments(department_id)
);
In this example:

The "departments" table stores information about different departments, with the department_id as the primary key.

The "employees" table stores information about employees, including the employee_id as the primary key and the department_id as a foreign key that references the "departments" table.

This establishes a one-to-many relationship because:

Each department in the "departments" table can have multiple employees in the "employees" table.

Each employee in the "employees" table is associated with only one department in the "departments" table.

In summary, one department can have many employees, but each employee belongs to only one department.






