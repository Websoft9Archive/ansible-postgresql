# GUI: pgAdmin

[pgAdmin](https://www.pgadmin.org/) is rich Open Source administration and development platform for PostgreSQL 

pgAdmin is built using Python and Javascript/jQuery. A desktop runtime written in C++ with Qt allows it to run standalone for individual users, or the web application code may be deployed directly on a webserver for use by one or more users through their web browser. 

We will introduce the basic managements about pgAdmin

### Install and Connection

1. [Download](https://www.pgadmin.org/download/) and install pgAdmin for Windows

2. Installation completed, click the pgAdmin icon, you can see the pgAdmin running on your default browser

3. Set your pgAdmin master password first
  ![set pgAdmin password](https://libs.websoft9.com/Websoft9/DocsPicture/zh/postgresql/pgadmin-setmasterpw-websoft9.png)

4. Set your PostgreSQL database connection ([don't known password](/stack-accounts.md#postgresql))
  ![set pgAdmin connection](https://libs.websoft9.com/Websoft9/DocsPicture/zh/postgresql/pgadmin-setconnection-websoft9.png)

3. 成功连接
  ![phpPgadmin](https://libs.websoft9.com/Websoft9/DocsPicture/zh/postgresql/pgadmin-console-websoft9.png)

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