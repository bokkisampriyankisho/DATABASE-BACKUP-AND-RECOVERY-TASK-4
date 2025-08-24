# DATABASE-BACKUP-AND-RECOVERY-TASK-4

STEP 1: CREATING DATABASE AND TABLE

--CREATE DATABASE
CREATE DATABASE company_db;

--USE THE DATABASE
USE company_db;

--CREATE TABLE
CREATE TABLE employees(
   Emp id INT PRIMARY KEY,
   Name VARCHAR(50),
   Dept VARCHAR(50),
   Salary DECIMAL(10,2)
);
--INSERT SAMPLE DATA
INSERT INTO employees VALUES
(1,'Rasi','HR',45000.00),
(2,'Charlie','IT',60000.00),
(3,'Udaya','Finance',55000.00);

--VIEW TABLE
SELECT * FROM employees;


OUTPUT:

|Emp id |Name   |Dept   |Salary   |
|-------|-------|-------|---------|
| 1     | Rasi  | HR    | 45000.00|
| 2     | Charlie| IT   | 60000.00|
| 3     | Udaya | Finance|55000.00|


STEP 2: TAKE A BACKUP OF DATABASE

Command(MySQL Dump method)

QUERY:

mysqldump -u root -p company_db > company_db_backup.sql

This creates a backup file(cpmpany_db_backup.sql) containong all structure and data.

STEP 3: SIMULATE DATABASE FAILURE(DROP DATABASE)

QUERY:

DROP DTABASE company_db;

Now the database is lost.

STEP 4: RESTORE DATABASE FROM BACKUP

QUERY :

mysql -u root -p company_db < company_db_backup.sql

STEP 5: VERIFY RESTORED DATABASE

QUERY :

USE company_db;
SELECT * FROM employees;

OUTPUT :

| EMp id| Name    | Dept    | Salary   |
|-------|---------|---------|----------|
| 1     | Rasi    | HR      | 45000.00 |
| 2     | Charlie | IT      | 60000.00 |
| 3     | Udaya   | Finance | 55000.00 |














































































