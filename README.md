## 1. Environment

* WSL(Ubuntu 20.04.1 LTS (GNU/Linux 4.19.128-microsoft-standard x86_64))
* Docker version 20.10.2 |build 2291f61
* mysql/mysql-server:8.0

## 2. Reference

[MySQL Tutorial](https://www.w3schools.com/mysql/default.asp)

### 3. Docker

### 3-1. Setup MySQL and Login

```bash
$ echo 'export MYSQL_PASSWORD="password"' >> ~/.bash_profile
$ docker-compose up -d
$ docker-compose exec db mysql -u root -p
Enter password: password
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 248
Server version: 8.0.24 MySQL Community Server - GPL

Copyright (c) 2000, 2021, Oracle and/or its affiliates.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql>
```

### 3-2. Create DB

```sql
CREATE TABLE {DB_NAME};
SHOW DATABASES;
USE {DB_NAME};
```

### 3-3. Create Tables and Insert Records

Please refer to [SQL files](https://github.com/oasis-forever/mysql_tutorial/tree/master/sqls).

## 4. Tables

### 4-1. Categories

|CategoryID |CategoryName |Description |
|:-|:-|:-|
|PRIMARY KEY |varchar(255) |varchar(255) |

### 4-2. Customers

|CustomerID |CustomerName |ContactName |Address |City |PostalCode |Country |
|:-|:-|:-|:-|:-|:-|:-|
|PRIMARY KEY |varchar(255) |varchar(255) |varchar(255) |varchar(255) |varchar(255) |varchar(255) |

### 4-3. Employees

|EmployeeID |LastName |FirstName |BirthDate |Photo |Notes |
|:-|:-|:-|:-|:-|:-|
|PRIMARY KEY |varchar(255) |varchar(255) |date |varchar(255) |varchar(255) |

### 4-4. Shippers

|ShipperID |ShipperName |Phone |
|:-|:-|:-|
|PRIMARY KEY |varchar(255) |varchar(255) |

### 4-5. Suppliers

|SupplierID |SupplierName |ContactName |Address |City |PostalCode |Country |Phone |
|:-|:-|:-|:-|:-|:-|:-|:-|
|PRIMARY KEY |varchar(255) |varchar(255) |varchar(255) |varchar(255) |varchar(255) |varchar(255) |varchar(255) |

### 4-6. Products

|ProductID |ProductName |SupplierID |CategoryID |Unit |Price |
|:-|:-|:-|:-|:-|:-|
|PRIMARY KEY |varchar(255) |FOREIGN KEY |FOREIGN KEY |varchar(255) |float(5) |

### 4-7. OrderDetails

|OrderDetailID |OrderID |ProductID |Quantity |
|:-|:-|:-|:-|
|PRIMARY KEY |FOREIGN KEY |FOREIGN KEY |int |

### 4-8. Orders

|OrderID |CustomerID |EmployeeID |OrderDate |ShipperID |
|:-|:-|:-|:-|:-|
|PRIMARY KEY |FOREIGN KEY |FOREIGN KEY |date |FOREIGN KEY |
