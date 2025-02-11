# MySQL Database Management Guide

This guide provides instructions for basic MySQL database administration tasks including logging in, user management, and permissions.

## Logging into MySQL

### Using Command Line
1. Basic login (if MySQL is running on localhost):
```bash
mysql -u root -p
```
## Checking Number of Users

1. After logging in, to see all users:
```sql
SELECT User, Host FROM mysql.user;
```

2. To count total number of users:
```sql
SELECT COUNT(*) FROM mysql.user;
```

## Creating Users and Managing Permissions

### Creating a New User
```sql
CREATE USER 'username'@'hostname' IDENTIFIED BY 'password';
```
Replace:
- 'username' with desired username
- 'hostname' with '%' for access from any host, or 'localhost' for local access only
- 'password' with a strong password

### Granting All Permissions
1. Grant all privileges on specific database:
```sql
GRANT ALL PRIVILEGES ON database_name.* TO 'username'@'hostname';
```

2. Giving minimum permissions
```sql
GRANT SELECT, INSERT, UPDATE, DELETE ON database_name.* TO 'username'@'hostname';
```
3. Apply privileges:
```sql
   FLUSH PRIVILEGES;
```

### Common Permission Types Explained
- SELECT: Read data
- INSERT: Add new records
- UPDATE: Modify existing records
- DELETE: Remove records
- CREATE: Create new databases/tables
- DROP: Delete databases/tables
- RELOAD: Reload server settings
- PROCESS: View server processes
- REFERENCES: Create foreign keys
- INDEX: Create/remove indexes
- ALTER: Modify table structure
- SHOW DATABASES: View database list
- CREATE TEMPORARY TABLES: Create temp tables
- LOCK TABLES: Lock tables
- EXECUTE: Execute stored procedures
- REPLICATION SLAVE: Replicate from master
- REPLICATION CLIENT: Ask master/slave status
- CREATE VIEW: Create views
- SHOW VIEW: View existing views
- CREATE ROUTINE: Create stored procedures
- ALTER ROUTINE: Modify stored procedures
- CREATE USER: Create users
- EVENT: Create/alter/drop events
- TRIGGER: Create/alter/drop triggers

4. Now login with a new user:
```sql
   mysql -u username -p
   create database database_name;
   -- it will throw a error permission denied for the user to create a database
```
5. Now login with the root user:
```sql
   mysql -u root -p
   -- it will ask for a password
```

6. Now we are giving a full permission to the new user:
```sql
   GRANT ALL PRIVILEGES ON database_name.* TO 'username'@'hostname';
   FLUSH PRIVILEGES;
```

### Viewing User Permissions
```sql
SHOW GRANTS FOR 'username'@'hostname';
```

### Revoking Permissions
```sql
REVOKE ALL PRIVILEGES ON database_name.* FROM 'username'@'hostname';
FLUSH PRIVILEGES;
```
### Altering the user password 
```sql
ALTER USER 'username'@'hostname' IDENTIFIED BY 'new_password';
   -- Add new_password to the list of arguments 
   -- and execute
   FLUSH PRIVILEGES;
```

### Dropping a User
```sql
DROP USER 'username'@'hostname';
FLUSH PRIVILEGES;
```

