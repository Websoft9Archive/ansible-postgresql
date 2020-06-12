# 图形化工具：pgAdmin

[pgAdmin](https://www.pgadmin.org/) 是一款功能丰富、开源免费的 PostgreSQL 图形化客户端工具。它支持 Linux, Unix, Mac, Windows 等多种桌面操作系统。  

pgAdmin4 使用 Python 和 Javascript / jQuery 构建。可以在桌面上调用浏览器运行，也支持基于 Web 直接在浏览器运行。

本节介绍 pgAdmin 连接和管理数据库等常见操作

### 安装与连接

1. [下载](https://www.pgadmin.org/download/) pgAdmin Windows 版

2. 安装完成后，双击 pgAdmin 图标，会启动默认浏览器中打开 pgAdmin

3. 根据提示，先设置一个 pgAdmin 管理密码
  ![设置pgAdmin管理密码](https://libs.websoft9.com/Websoft9/DocsPicture/zh/postgresql/pgadmin-setmasterpw-websoft9.png)

4. 设置所需管理的 PostgreSQL 数据库连接信息([不知道密码？](/zh/stack-accounts.md#postgresql))
  ![设置pgAdmin连接信息](https://libs.websoft9.com/Websoft9/DocsPicture/zh/postgresql/pgadmin-setconnection-websoft9.png)

3. 成功连接
  ![phpPgadmin](https://libs.websoft9.com/Websoft9/DocsPicture/zh/postgresql/pgadmin-console-websoft9.png)

### 创建数据库

1. 鼠标右键一次点击：【Servers】>【Create】>【Database】，创建数据库
  ![pgAdmin 创建数据库](https://libs.websoft9.com/Websoft9/DocsPicture/zh/postgresql/pgadmin-createdb-websoft9.png)

2. 设置数据库名称、编码等信息，创建数据库


### 创建用户

PostgreSQL 中创建用户就是创建 Role

1. 鼠标右键一次点击：【Servers】>【Create】>【Login/Group Role】，创建用户
  ![pgAdmin 创建用户](https://libs.websoft9.com/Websoft9/DocsPicture/zh/postgresql/pgadmin-createroles-websoft9.png)

2. 设置用户名称、密码等信息，创建用户


### 备份数据库

1. 选择需要备份的数据库，点击【Backup】操作
  ![pgAdmin 创建数据库](https://libs.websoft9.com/Websoft9/DocsPicture/zh/postgresql/pgadmin-backupdb-websoft9.png)

2. 备份并下载到本地