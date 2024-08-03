# SQL on Linux Terminal Using MySQL 

### Note:
Once you enter the MySQL CLI, you will need to use “;” for it to interpret the command. Otherwise, it will just move to the next line, allowing you to enter more commands. The SQL language is not case-sensitive. However, the order of the commands matters (e.g., `SELECT` goes first, then `FROM`, followed by other parameters). Dates in SQL are represented as integers and must be wrapped between “ ” (e.g., “YYYY-MM-DD”). Also, Fields and columns are used interchangeably but mean the same thing for this content.

### Regex Summary:
- `^` means the beginning.
- `$` means the end.
- `|` is a logical OR.
- `[abcd]` specifies any character from a, b, c, d.
- `[a-c]` specifies the range from “a to c”.

To get a deeper understanding of regex expressions used in SQL, here's a handy reference table:


## Installation Steps

1. **Install MySQL:**
    ```bash
    sudo apt install mysql-server -y
    ```
    This command installs MySQL on your machine.

2. **Verify Installation:**
    ```bash
    sudo systemctl status mysql
    ```
    If it says ‘active (running)’, the installation was successful.

3. **Start MySQL:**
    ```bash
    sudo mysql
    ```
    This command starts MySQL in the terminal.

## Basic Commands

4. **Show Databases:**
    ```sql
    show databases;
    ```
    Displays all available databases.

5. **Create a Database:**
    ```sql
    create database {name};
    ```
    Creates a new database with the specified name.

6. **Use a Database:**
    ```sql
    use {name of the database};
    ```
    Switches to a specific database for further operations.

## Table Operations

7. **Create a Table:**
    ```sql
    create table {name of the table} (
        id int,
        name varchar(255),
        gender boolean
    );
    ```
    Creates a table with columns `id`, `name`, and `gender`.

8. **Show Tables:**
    ```sql
    show tables;
    ```
    Displays all tables in the current database.

9. **Describe a Table:**
    ```sql
    describe {name of the table};
    ```
    Displays the structure of the specified table.

## Data Operations

10. **Insert Values:**
    ```sql
    insert into {table name} values (1, “Purva”, True);
    ```
    Inserts values into the specified table.

11. **Select All:**
    ```sql
    select * from {name of the table};
    ```
    Displays all data from the specified table.

12. **Filter Data:**
    ```sql
    select * from {name of the table} where name = “Purva”;
    ```
    Filters data where the `name` field is “Purva”.

13. **Delete Data:**
    ```sql
    delete from {name of the table} where name = “Purva”;
    ```
    Deletes rows where the `name` field is “Purva”.

14. **Update Data:**
    ```sql
    update {name of the table} set name = “Patel” where id = 1;
    ```
    Updates the `name` field to “Patel” where `id` is 1.

## Advanced Commands

15. **Order Data:**
    ```sql
    select * from {name of the table} order by id asc;
    ```
    Orders data by `id` in ascending order.

16. **Add a Column:**
    ```sql
    alter table {name of the table} add LastName varchar(255);
    ```
    Adds a new column `LastName` to the table.

17. **Arithmetic Operations:**
    ```sql
    select age + 1 from {name of the table};
    ```
    Performs arithmetic operations on `age` column.

18. **Set Alias:**
    ```sql
    select age + 1 as NewAge from {name of the table};
    ```
    Sets an alias `NewAge` for the result of the arithmetic operation.

19. **Distinct Values:**
    ```sql
    select distinct FirstName from {name of the table};
    ```
    Displays unique values from the `FirstName` column.

20. **IN Operator:**
    ```sql
    select * from {name of the table} where name in (“Purva”, “Patel”);
    ```
    Filters data where the `name` field is either “Purva” or “Patel”.

21. **BETWEEN Operator:**
    ```sql
    select * from {name of the table} where age between 20 and 30;
    ```
    Displays data where `age` is between 20 and 30.

22. **LIKE Operator:**
    ```sql
    select * from {name of the table} where name like “P%”;
    ```
    Filters data where `name` starts with “P”.

23. **REGEXP Operator:**
    ```sql
    select * from {name of the table} where name regexp “^P”;
    ```
    Filters data where `name` starts with “P” using regular expressions.

24. **NULL Values:**
    ```sql
    select * from {name of the table} where name is null;
    ```
    Filters data where the `name` field is `null`.

25. **LIMIT Results:**
    ```sql
    select * from {name of the table} limit 5;
    ```
    Limits the number of results to 5.

26. **OFFSET Results:**
    ```sql
    select * from {name of the table} limit 5 offset 2;
    ```
    Skips the first 2 results and then limits the results to 5.

## Joining Tables

27. **Basic Join:**
    ```sql
    select * from table1 join table2 on table1.id = table2.id;
    ```
    Joins two tables on the `id` column.

28. **Join Across Databases:**
    ```sql
    use database1;
    select * from database2.table2 join table1 on table1.id = table2.id;
    ```
    Joins tables from two different databases.

29. **Self Join:**
    ```sql
    select * from table1 t1 join table1 t2 on t1.id = t2.id;
    ```
    Joins a table with itself using aliases.

30. **Compound Join:**
    ```sql
    select * from table1 join table2 on table1.id = table2.id and table1.name = table2.name;
    ```
    Joins tables on multiple columns.

31. **USING Clause:**
    ```sql
    select * from table1 join table2 using (id);
    ```
    Joins tables using a common column.

32. **Natural Join:**
    ```sql
    select * from table1 natural join table2;
    ```
    Automatically joins tables on columns with the same name.

33. **Cross Join:**
    ```sql
    select * from table1 cross join table2;
    ```
    Produces a Cartesian product of both tables.

34. **UNION:**
    ```sql
    select * from table1 union select * from table2;
    ```
    Combines the results of two queries.

35. **Create Table from Another Table:**
    ```sql
    create table new_table as select * from existing_table;
    ```
    Creates a new table by copying an existing table.

---

By following these commands, you can efficiently manage databases and tables using MySQL on a Linux terminal. Each command is designed to be intuitive, making it easier for you to navigate and manipulate your data.

---

Author: **Purva Patel**
