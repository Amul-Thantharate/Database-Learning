# Database Commands Guide

This guide provides common SQL commands for database operations.

## Database Management Commands

### Drop Database
```sql
DROP DATABASE database_name;
```

### Create Database
```sql
CREATE DATABASE database_name;
```

### Show databases
```sql
    SHOW DATABASES;
```

### Use database
```sql
USE database_name;
```

### Describe Table Structure
```sql
DESCRIBE table_name;
-- OR
DESC table_name;
```

### Create Table
```sql
CREATE TABLE employees (
    id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(100) NOT NULL,
    email VARCHAR(100) UNIQUE,
    department VARCHAR(50),
    salary DECIMAL(10,2),
    hire_date DATE
);
```

## Data Manipulation Commands

### Insert Data
```sql
-- Single row insert
INSERT INTO employees (name, email, department, salary, hire_date)
VALUES ('John Doe', 'john@example.com', 'IT', 75000.00, '2024-01-15');

-- Multiple row insert
INSERT INTO employees (name, email, department, salary, hire_date)
VALUES 
    ('Jane Smith', 'jane@example.com', 'HR', 65000.00, '2024-01-20'),
    ('Bob Wilson', 'bob@example.com', 'Sales', 70000.00, '2024-01-25'),
    ('Alice Johnson', 'alice@example.com', 'IT', 80000.00, '2024-01-30');
```

### Update Data
```sql
-- Update single record
UPDATE employees 
SET salary = 80000.00 
WHERE id = 1;

-- Update multiple records
UPDATE employees 
SET department = 'Technology' 
WHERE department = 'IT';
```

### Delete Data
```sql
-- Delete specific record
DELETE FROM employees 
WHERE id = 1;

-- Delete multiple records
DELETE FROM employees 
WHERE department = 'Sales';

-- Delete all records
DELETE FROM employees;
```



## Tips
- Always be careful with DELETE and DROP commands as they permanently remove data
- Use WHERE clauses with UPDATE and DELETE to avoid affecting unintended records
- Back up your database before performing major operations
- Use DESCRIBE to verify table structure before inserting data
