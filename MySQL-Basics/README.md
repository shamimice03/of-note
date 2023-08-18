As a DevOps engineer, you'll likely need to interact with MySQL databases for various tasks. Here are some basic MySQL commands that can be useful for DevOps tasks:

1. **Logging into MySQL:**

   To log in to the MySQL server using the command line:

   ```bash
   mysql -u <username> -p
   ```

   Replace `<username>` with the appropriate username. You'll be prompted to enter the password.

2. **Show Databases:**

   List all available databases:

   ```sql
   SHOW DATABASES;
   ```

3. **Create Database:**

   Create a new database:

   ```sql
   CREATE DATABASE <database_name>;
   ```

4. **Use Database:**

   Switch to a specific database to work with:

   ```sql
   USE <database_name>;
   ```

5. **Show Tables:**

   List all tables in the current database:

   ```sql
   SHOW TABLES;
   ```

6. **Describe Table:**

   Get information about the columns and structure of a table:

   ```sql
   DESCRIBE <table_name>;
   ```

7. **Import SQL File:**

   Import an SQL file into a database:

   ```bash
   mysql -u <username> -p <database_name> < <path_to_sql_file.sql>
   ```

8. **Backup Database:**

   Create a backup of a database:

   ```bash
   mysqldump -u <username> -p <database_name> > <backup_file.sql>
   ```

9. **Restore Database:**

   Restore a database from a backup file:

   ```bash
   mysql -u <username> -p <database_name> < <backup_file.sql>
   ```

10. **Create User:**

    Create a new MySQL user:

    ```sql
    CREATE USER '<username>'@'localhost' IDENTIFIED BY '<password>';
    ```

11. **Grant Privileges:**

    Grant privileges to a user on a specific database:

    ```sql
    GRANT ALL PRIVILEGES ON <database_name>.* TO '<username>'@'localhost';
    FLUSH PRIVILEGES;
    ```

12. **Revoke Privileges:**

    Revoke privileges from a user:

    ```sql
    REVOKE ALL PRIVILEGES ON <database_name>.* FROM '<username>'@'localhost';
    FLUSH PRIVILEGES;
    ```

13. **Show User Privileges:**

    Show the privileges granted to a user:

    ```sql
    SHOW GRANTS FOR '<username>'@'localhost';
    ```

14. **Change User Password:**

    Change the password for a MySQL user:

    ```sql
    ALTER USER '<username>'@'localhost' IDENTIFIED BY '<new_password>';
    ```

15. **Restart MySQL Service:**

    Restart the MySQL service (useful after configuration changes):

    ```bash
    sudo systemctl restart mysql
    ```

16. **Exit MySQL:**

    Exit the MySQL command-line client:

    ```sql
    EXIT;
    ```


***

- [Creating MySQL pod with preloaded database](https://medium.com/@AbhijeetKasurde/creating-mysql-pod-with-preloaded-database-2c01c002fdc3)
