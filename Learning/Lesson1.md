## Basic Definitions
**What is a Database?**  
A database is a collection of data and holds the data in the form of table. provide us the capability of accessing and manipualating the data.

**What is a table?**  
It is a way of storing data in the form of rows and columns. It is similar to Excel spreadsheet which we have encountered numerous times.

**If we can store data in excel spreadsheets, then why do we need databases?**  
Suppose you have more than 1000 spreadsheets with a lot of data. In such scenarios it become cumbersome to manage such amount of data. That is why is recommended to use a database which will not only solve this problem but also provide n-number of other functionalities.
The database provide us the capability to access and manipulate the data.

**Two type of databases**  
- Relational databases  
In this the data is stored in the form of rows & columns. The tables have relationship between them.  
Examples: MySQL, MS SQL Server, Maria DB, SQLite, PostgreSQL
- Non-relational databases (NO SQL database)  
In this it could be in the form of key-value pairs, graph, document, XML etc. No two form of entities have relationship between them.  
Example: Hbase, Cassandra, MongoDB etc.

_In this course we will focus on only relational databases and in particular MySQL database since its very popular._

**MySQL vs SQL**
MySQL is a database to store the data whereas SQL is a language which stands for Structured Query language and it is used to communicate with stuctured databases.  

For practice use _goormide.io_. Signup using an email and practise SQL on it.

Creds used: nexet26003@ktasy.com, Nexet@26003, https://ide.goorm.io/my/dashboard#/containers

## Commands Used
|Command    |Purpose     |
|-----------|------------|
|mysql-ctl cli ; |Used to start CLI interface of MySQL on in goormIDE|
|SHOW databases ; |list all existing databases|
|CREATE DATABASE <name>;| to create a new database|
|DROP DATABASE <name>; |to delete/drop a database|
|USE <name-of-database>; |to select the database you want to work in|
|SELECT database(); |to check the database you are working in|  
|CREATE TABLE employee(name varchar(50), age int, salary int);  | Create a new table |
|SHOW TABLES; |To check the list of tables in the current database|
|DESCRIBE <name-of-table>; |To see the schema of the table|
|DROP TABLE <name-of-table>; |To drop exisiting table  |

## Type of datatypes in MySQL database
In MySQL there are three main data types: string, numeric, and date and time.

**String Data Types**
|Data type	| Description|
|-----------|------------|
|CHAR(size)	|A FIXED length string (can contain letters, numbers, and special characters). The size parameter specifies the column length in characters - can be from 0 to 255. Default is 1|
|VARCHAR(size)	|A VARIABLE length string (can contain letters, numbers, and special characters). The size parameter specifies the maximum string length in characters - can be from 0 to 65535|
|BINARY(size)	|Equal to CHAR(), but stores binary byte strings. The size parameter specifies the column length in bytes. Default is 1|
|VARBINARY(size)	|Equal to VARCHAR(), but stores binary byte strings. The size parameter specifies the maximum column length in bytes.|
|TEXT(size)	|Holds a string with a maximum length of 65,535 bytes|
|BLOB(size)	|For BLOBs (Binary Large Objects). Holds up to 65,535 bytes of data|
|LONGTEXT	|Holds a string with a maximum length of 4,294,967,295 characters|
|ENUM(val1, val2, val3, ...)	|A string object that can have only one value, chosen from a list of possible values. You can list up to 65535 values in an ENUM list. If a value is inserted that is not in the list, a blank value will be inserted. The values are sorted in the order you enter them|
|SET(val1, val2, val3, ...)	|A string object that can have 0 or more values, chosen from a list of possible values. You can list up to 64 values in a SET list|  

**Numeric Data Types**
|Data type	|Description|
|-----------|------------|
|BOOL	|Zero is considered as false, nonzero values are considered as true.|
|BOOLEAN	|Equal to BOOL|
|SMALLINT(size)	|A small integer. Signed range is from -32768 to 32767. Unsigned range is from 0 to 65535. The size parameter specifies the maximum display width (which is 255)|
|INT(size)	|A medium integer. Signed range is from -2147483648 to 2147483647. Unsigned range is from 0 to 4294967295. The size parameter specifies the maximum display width (which is 255)|
|BIGINT(size)	|A large integer. Signed range is from -9223372036854775808 to 9223372036854775807. Unsigned range is from 0 to 18446744073709551615. The size parameter specifies the maximum display width (which is 255)|
|FLOAT(p)	|A floating point number. MySQL uses the p value to determine whether to use FLOAT or DOUBLE for the resulting data type. If p is from 0 to 24, the data type becomes FLOAT(). If p is from 25 to 53, the data type becomes DOUBLE()|
|DOUBLE(size, d)	|A normal-size floating point number. The total number of digits is specified in size. The number of digits after the decimal point is specified in the d parameter|
|DECIMAL(size, d)	|An exact fixed-point number. The total number of digits is specified in size. The number of digits after the decimal point is specified in the d parameter. The maximum number for size is 65. The maximum number for d is 30. The default value for size is 10. The default value for d is 0.|

**Date and Time Data Types**
|Data type	|Description|
|-----------|------------|
|DATE	|A date. Format: YYYY-MM-DD. The supported range is from '1000-01-01' to '9999-12-31'|
|DATETIME(fsp)	|A date and time combination. Format: YYYY-MM-DD hh:mm:ss. The supported range is from '1000-01-01 00:00:00' to '9999-12-31 23:59:59'. Adding DEFAULT and ON UPDATE in the column definition to get automatic initialization and updating to the current date and time|
|TIMESTAMP(fsp)	|A timestamp. TIMESTAMP values are stored as the number of seconds since the Unix epoch ('1970-01-01 00:00:00' UTC). Format: YYYY-MM-DD hh:mm:ss. The supported range is from '1970-01-01 00:00:01' UTC to '2038-01-09 03:14:07' UTC. Automatic initialization and updating to the current date and time can be specified using DEFAULT CURRENT_TIMESTAMP and ON UPDATE CURRENT_TIMESTAMP in the column definition|
|TIME(fsp)	|A time. Format: hh:mm:ss. The supported range is from '-838:59:59' to '838:59:59'|
|YEAR	|A year in four-digit format. Values allowed in four-digit format: 1901 to 2155, and 0000. MySQL 8.0 does not support year in two-digit format.|  
