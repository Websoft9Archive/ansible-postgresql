# 图形化工具：phpPgAdmin

phpPgAdmin是很受欢迎的PostgreSQL数据库管理工具，下面介绍常见的phpPgAdmin操作

### 登录

1. 本地浏览器 Chrome 或 Firefox 访问：*http://服务器公网IP:9090*，进入phpPgAdmin
  ![登录phpMyadmin](https://libs.websoft9.com/Websoft9/DocsPicture/zh/postgresql/pgadmin.png)
2. 输入数据库用户名和密码([不知道密码？](/zh/stack-accounts.md#postgresql))
3. 开始管理数据库
  ![phpPgadmin](https://libs.websoft9.com/Websoft9/DocsPicture/zh/postgresql/phppgadmin-gui-websoft9.png)

### 创建数据库

1. 在【数据库】标签下，点击【创建数据库】链接
  ![phpPgadmin 创建数据库](https://libs.websoft9.com/Websoft9/DocsPicture/zh/postgresql/phppgadmin-createdb-websoft9.png)

2. 设置数据库名称、编码等信息，创建数据库


### 创建用户

PostgreSQL 中创建用户就是创建 Role

1. 在【Roles】标签下，点击【Create role】链接
  ![phpPgadmin 创建用户](https://libs.websoft9.com/Websoft9/DocsPicture/zh/postgresql/phppgadmin-createroles-websoft9.png)

2. 设置用户名称、密码等信息，创建用户


### 备份数据库

1. 选择需要备份的数据库，点击【导出】标签，勾选【Download】后，点击【导出】
  ![phpPgadmin 创建数据库](https://libs.websoft9.com/Websoft9/DocsPicture/zh/postgresql/phppgadmin-dl-websoft9.png)

2. 系统提示下载导出文件

3. 备份成功
