![Image](./logo.png)
# SQL

## What is a database?
A database is a structured collection of data that allows efficient storage, retrieval, and management of information.

## Why do we need it?
- To keep data organized.
- To allow data re-use in the future by applications or services.

## What is the link between an application and a database?
The connection between an application and a database is **data**. Applications use databases to store and retrieve data for processing.

## Examples of databases
- File systems (files and folders)
- Relational databases like MySQL, PostgreSQL
- NoSQL databases like MongoDB, Firebase

## Why do we need a Database Application Server?
A database application server provides:
- Speedy data access.
- Data security and integrity.
- Advanced functionalities such as indexing, transaction management, and querying.

## How to install a database?

### 1. Install MySQL using XAMPP
1. Visit [Apache Friends](https://www.apachefriends.org/).
2. Download the XAMPP application.
3. Install it on your system.
4. Start the MySQL service via the XAMPP control panel.

---

## Connecting to MySQL
- Use a MySQL client or command-line interface to connect to your database.
- Test your connection with basic commands like `SHOW DATABASES;`.

---

## Introduction to Database Structure
- **Database**: A collection of related data.
- **Table**: A structured format to store data in rows and columns.
- **Rows**: Individual records in a table.
- **Other structures**: Procedures, views, triggers.

---

## SQL Basics - CRUD Operations
### Read Data (SELECT)
#### Read table names in a database
```sql
SHOW TABLES;
```
#### Describe table structure
```sql
DESCRIBE etudiants;
```
#### Basic SELECT query
```sql
SELECT * FROM etudiants;
```
#### SELECT with aliases
```sql
SELECT nom AS name, telephone AS subscribers FROM etudiants;
```
#### SELECT with WHERE clause
```sql
SELECT * FROM etudiants WHERE date_inscription = '2024-12-01';
```
#### SELECT with LIKE operator
```sql
SELECT * FROM etudiants WHERE nom LIKE '%a%';
```
#### SELECT with IN clause
```sql
SELECT * FROM etudiants WHERE nom IN ('Moreau', 'Adam');
```
#### SELECT with ORDER BY
```sql
SELECT * FROM etudiants ORDER BY date_naissance ASC;
```
#### SELECT with AND condition
```sql
SELECT * FROM etudiants WHERE date_naissance <= '2002-12-03' AND nom LIKE '%a%';
```
#### SELECT with OR condition
```sql
SELECT * FROM etudiants WHERE date_naissance <= '2002-12-03' OR nom LIKE '%a%';
```
#### SELECT with NOT operator
```sql
SELECT * FROM etudiants WHERE date_naissance <= '2002-12-03' AND nom NOT LIKE '%a%';
```
#### COUNT function
```sql
SELECT COUNT(*) AS with_a_in_lastname FROM etudiants WHERE nom LIKE '%a%';
```
#### SUM function
```sql
SELECT SUM(price) AS total_price FROM clients WHERE date_achat BETWEEN '2022' AND '2023';
```
#### JOIN examples
```sql
SELECT enseignement_id, cours.nom_cours, CONCAT(professeurs.nom, ' ', professeurs.prenom) AS professeur
FROM enseignements
JOIN cours ON cours.cours_id = enseignements.cours_id
JOIN professeurs ON professeurs.professeur_id = enseignements.professeur_id;
```

---

### Create Data (INSERT)
#### Insert a row into a table
```sql
INSERT INTO etudiants (nom, prenom, date_naissance, email, telephone, date_inscription)
VALUES ('Berto', 'Ro', '1998-01-30', 'ariel@webschool.co.il', '0567890989', '2024-12-03');
```

### Update Data (UPDATE)
#### Update a row in a table
```sql
UPDATE etudiants
SET nom = 'Sarkozy', prenom = 'Nicola'
WHERE etudiant_id = 3;
```

### Delete Data (DELETE)
#### Delete a row from a table
```sql
DELETE FROM etudiants WHERE etudiant_id = 2;
```

---

### Database Management
#### Create a new database
```sql
CREATE DATABASE website;
```
#### Drop a database
```sql
DROP DATABASE website;
```
#### Select a database
```sql
USE website;
```
#### Create a table
```sql
CREATE TABLE menu (
    id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(50),
    href VARCHAR(200)
);
```
#### Drop a table
```sql
DROP TABLE menu;
```
#### Modify a table structure
```sql
ALTER TABLE menu DROP COLUMN href;
```

---

## Advanced Topics
### Introduction to Postman
Postman is a tool for testing APIs, which can interact with databases through REST APIs.

### Introduction to REST APIs
REST APIs enable communication between a client and server using HTTP methods like GET, POST, PUT, DELETE.

### Introduction to Flask and SQL in Python
Use Python's Flask framework to build web applications and connect to MySQL using a MySQL driver.

---

Ready to dive deeper? 🚀

