# SQL

### **Creating & Dropping a Database**

#### **CREATE DATABASE**
- Very simple. 
- Requires admin privileges.

```sql
CREATE DATABASE database_name;
```

- Can check if it has been created afterwards by running the SQL command: `SHOW DATABASES;`

<br />

#### **DROP DATABASE**
- Deletes a database, along with all tables and data inside it. 
- Requires admin privileges.
- **Be careful** with this command! It will result in complete loss of information inside the database.
```sql
DROP DATABASE database_name;
```

<br />

### **Creating, Altering, Dropping a Table**

#### **CREATE TABLE**
- The column parameters specify the names of the columns of the table.
- The datatype parameter specifies the type of data the column can hold (e.g. varchar, integer, date, etc.).
- [Link to SQL Data Types Overview](https://www.w3schools.com/Sql/sql_datatypes.asp).
```sql
CREATE TABLE table_name (
    column1 datatype,
    column2 datatype,
    column3 datatype,
   ....
); 
```
- Example with `students` table:
```sql
CREATE TABLE students (
  id INT PRIMARY KEY AUTO_INCREMENT,
  fname VARCHAR(255) NOT NULL,
  lname VARCHAR(255) NOT NULL,
  major VARCHAR(255) DEFAULT 'Undecided'
);

-- Alternate way to declare primary key
CREATE TABLE professors (
  id INT AUTO_INCREMENT,
  fname VARCHAR(255) NOT NULL,
  lname VARCHAR(255) NOT NULL,
  dept VARCHAR(255) NOT NULL,
  PRIMARY KEY (id)
)
```

<br />

#### **ALTER TABLE**
- Used to modify a table after it has been created.
- Can add, remove or modify columns.
- Can add or drop constraints.

Add / Drop Example
```sql
ALTER TABLE table_name
ADD column_name data_type

ALTER TABLE table_name
DROP COLUMN column_name

-- Students example
ALTER TABLE students
ADD gpa INT;

ALTER TABLE students
DROP COLUMN gpa;
```

Modification Example
```sql
-- Rename a column
ALTER TABLE table_name
RENAME COLUMN old_name TO new_name;

-- Change a column's datatype (MySQL)
ALTER TABLE table_name
MODIFY COLUMN column_name data_type;

-- Other RDBMSs may have different code for the above.
```

<br />

#### **DROP TABLE**
- Delete a table.
- **Important:** Deleteing a table will also delete all the entries contained within it, so be careful.

```sql
DROP TABLE table_name;
```

Bonus Tip: **TRUNCATE TABLE**
- Deletes all data within a table, but not the table itself.

```sql
TRUNCATE TABLE table_name;
```

<br />

### **Performing CRUD Operations on a Table**

#### **INSERT**
- Used to create new entries in a database table.
- Remember that the order of the values inside the parentheses of `VALUES` matters: it has to match the order of the columns `(col1, col2, col3)`.

```sql
INSERT INTO table_name (col1, col2, col3)
VALUES (
  val_col1,
  val_col2,
  val_col3
);
INSERT INTO table_name (col1, col2, col3)
VALUES 
(val1, val2, val3),
(val4, val5, val6),
(val7, val8, val9);
```
- Example with `students` table:
```sql
INSERT INTO students (fname, lname, major)
VALUES ('Ronson', 'Jeremiah', 'English Literature');
```
- Note that we didn't add a value for the `id` column. This is because it is an `AUTO_INCREMENT` field, and the RDBMS automatically generates a valid unique value for the id for each new row. 

<br />

#### **SELECT**
- Used to read entries from a database table.
- You specify which columns you want to read. An asterisk (`*`) means all columns.
- The `DISTINCT` keyword elimintes duplicate results. So for example, in the `students` table, you can use it to get all the unique majors that exist in the table. 

```sql
SELECT * FROM table_name;
SELECT DISTINCT * FROM table_name;

-- Student example
SELECT id, fname, lname, major FROM students;
SELECT DISTINCT major FROM students;
```

<br />

#### **UPDATE**
- Used to update existing entries in a database table.
- Used in conjunction with the `SET` keyword.
- **Important:** If the `WHERE` condition is not specified, the query will update all the rows in the table, so be careful.

```sql
UPDATE table_name SET col1 = new_val1, col2 = new_val2
WHERE some_condition;

-- Student example
UPDATE students SET major = 'Computer Science'
WHERE fname = 'Angad' AND lname = 'Virk';
```

<br />

#### **DELETE**
- Used to delete entries in a database table. 
- Similar to `UPDATE`, but you don't have to specify columns as the query is supposed to delete entire rows.
- **Important:** Be careful here as well, if you don't specify a `WHERE` condition, this query will **delete** all the rows in the table! Dangerous stuff.

```sql
DELETE FROM table_name
WHERE some_condition;

-- Student example
DELETE FROM students
WHERE major = 'Gender Studies';
```

<br />

<!-- ### **Additional Things** 

#### **Joins**
- Allows you to combine rows in different tables, based on a common column. 
- There are different types of joins in SQL. 

**INNER JOIN**
- The default join type is an inner join.
- Result includes rows which have matching values for the common column -->

<!-- `GROUP BY`, `HAVING`, `LIKE`) -->