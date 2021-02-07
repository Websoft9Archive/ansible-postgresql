# GUI: pgAdmin

[pgAdmin](https://www.pgadmin.org/) is rich Open Source administration and development platform for PostgreSQL 

pgAdmin is built using Python and Javascript/jQuery. A desktop runtime written in C++ with Qt allows it to run standalone for individual users, or the web application code may be deployed directly on a webserver for use by one or more users through their web browser. 

We will introduce the basic managements about pgAdmin

### Login pgAdmin

You can login to phpAdmin directly if you have deploy Websoft9 solution of PostgreSQL:

1. Local browser Chrome or Firefox access URL: *http://server's Internet IP:9090*, enter to pgAdmin
   ![login pgAdmin](https://libs.websoft9.com/Websoft9/DocsPicture/en/postgresql/pgadmin-loginui-websoft9.png)

2. Input pgAdmin administrator account([view username and password](/stack-accounts.md#postgresql)) and enter to console
   ![pgAdmin console](https://libs.websoft9.com/Websoft9/DocsPicture/en/postgresql/pgadmin-console-websoft9.png)

### Install pgAdmin Desktop

pgAdmin can also used in you local computer:

1. [Download](https://www.pgadmin.org/download/) and install pgAdmin for Windows

2. Click the pgAdmin icon, you can see the pgAdmin running on your default browser

3. Set your pgAdmin master password first
  ![set pgAdmin password](https://libs.websoft9.com/Websoft9/DocsPicture/en/postgresql/pgadmin-setmasterpw-websoft9.png)

### Connect pgAdmin

Once you have enter to pgAdmin console, you can connect PostgreSQL server now:

1. Click 【server】 to connect PostgreSQL server

2. Set your PostgreSQL database connection ([don't known password](/stack-accounts.md#postgresql))
  ![set pgAdmin connection](https://libs.websoft9.com/Websoft9/DocsPicture/en/postgresql/pgadmin-createserver-websoft9.png)

2. Login to console successfully
  ![phpPgadmin](https://libs.websoft9.com/Websoft9/DocsPicture/en/postgresql/pgadmin-console-websoft9.png)

### Create database

1. Right mouse click 【Servers】>【Create】>【Database】, create new database
  ![pgAdmin create database](https://libs.websoft9.com/Websoft9/DocsPicture/zh/postgresql/pgadmin-createdb-websoft9.png)

2. Set your database name, Encoding..., then create it


### Create user

PostgreSQL roles is similar with users

1. Right mouse click 【Servers】>【Create】>【Login/Group Role】, create new user
  ![pgAdmin create user](https://libs.websoft9.com/Websoft9/DocsPicture/zh/postgresql/pgadmin-createroles-websoft9.png)

2. Set your database username, password..., then create it


### Backup database

1. Select the database you want to export, click 【Backup】button
  ![pgAdmin 创建数据库](https://libs.websoft9.com/Websoft9/DocsPicture/zh/postgresql/pgadmin-backupdb-websoft9.png)

2. Start you backup