# MySQL

---

## Installation

### **[MAC] Install MySQL**:

Step 1: Go to link [mysql-downloads](https://dev.mysql.com/downloads/mysql/) to download desired installation.  
Step 2: Install with every thing default and choose the password.  
Step 3: Open terminal and type:

```
open ~/.zshrc
```

add new line:

```
# MySQL
export PATH=${PATH}:/usr/local/mysql/bin
```

close terminal and open it again  
Step 4: open new terminal and enter this command for login to mysql as root with pass:

```
mysql -u root -p
```

type password and done.

### **[MAC] Install MySQL Workbench**:

Step 1: Go to link [mysql-workbench-downloads](https://dev.mysql.com/downloads/workbench/) to download desired installation and install it.  
Step 2: Open MySQL workbench and login as root.

### SQL Commands

- Create database:

```SQL
CREATE DATABASE database_name;
```

- Delete database (**NEVER** use if want lose job):

```SQL
DROP DATABASE database_name;
```

- Use database:

```SQL
USE database_company;
```

- Create table:

```SQL
CREATE TABLE table_name (
    name_column INT
);
```

- Alter table (edit table after create it):
  Example add new column:

```SQL
ALTER TABLE table_name
ADD column_name VARCHAR(255); // create string with 255 characters
```

- Delete table:

```SQL
DROP TABLE table_name;
```

- Create column that cannot null:

```SQL
CREATE TABLE table_name (
    column_name VARCHAR(255) NOT NULL
);
```

- Create id (primary key with auto increment) that cannot null:

```SQL
CREATE TABLE table_name (
    id INT NOT NULL AUTO_INCREMENT,
    column_name VARCHAR(255) NOT NULL,
    PRIMARY KEY (id)
);
```

- Create foreign key for multiple tables working:

```SQL
CREATE TABLE albums (
	id INT NOT NULL AUTO_INCREMENT,
    column_name VARCHAR(255) NOT NULL,
    foreign_id INT NOT NULL,
    PRIMARY KEY (id),
    FOREIGN KEY (foreign_id) REFERENCES table_name(column_name)
);
```

- Insert record to table:

```SQL
INSERT INTO table_name (column_name)
VALUES ('ABC');
```

- Insert multiple records to table:

```SQL
INSERT INTO table_name (column_name)
VALUES ('ABC'), ('ABC');
```

- Insert multiple records of multiple columns to table:

```SQL
INSERT INTO table_name (column_name, column_name, column_name)
VALUES  ('ABC', 123, 'ABC'),
        ('ABC', 123, 'ABC');
```

- Query all data of all columns:

```SQL
SELECT * FROM table_name;
```

- Query data of all columns in limit:

```SQL
SELECT * FROM table_name LIMIT 2;
```

- Query data of specific column:

```SQL
SELECT column_name FROM table_name;
```

- Query data of specific column and rename it:

```SQL
SELECT column_name AS 'alias_name', column_name AS 'alias_name' FROM table_name;
```

- Query data in asc order:

```SQL
SELECT * FROM table_name ORDER BY column_name;
```

- Query data in reverse order:

```SQL
SELECT * FROM table_name ORDER BY column_name DESC;
```

- Query data and remove duplicate:

```SQL
SELECT DISTINCT column_name FROM table_name;
```

- Query data based on string:

```SQL
SELECT * FROM table_name
WHERE column_name LIKE '%condition%;
```

- Query data with different condition (and):

```SQL
SELECT * FROM table_name
WHERE column_name LIKE '%condition%' AND id = 1;
```

- Query data with different condition (or):

```SQL
SELECT * FROM table_name
WHERE column_name LIKE '%condition%' OR id = 1;
```

- Query data between conditions:

```SQL
SELECT * FROM table_name
WHERE column_name BETWEEN number AND number;
```

- Query data based on type:

```SQL
SELECT * FROM table_name
WHERE column_name IS NULL;
```

- Update all data of column:

```SQL
UPDATE table_name SET column_name = new_value;
```

- Update specific data of column:

```SQL
UPDATE table_name
SET column_name = new_value
WHERE id = 1;
```

