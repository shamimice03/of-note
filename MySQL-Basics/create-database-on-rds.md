
```sql
CREATE DATABASE <database_name>;
CREATE USER '<user>'@'localhost' IDENTIFIED BY '<password>';
GRANT ALL ON <database_name>.* TO '<user>'@'localhost';
FLUSH PRIVILEGES;
```
