# PostgreSQL速学

### 连接 PostgreSQL Server

~~~
postgresql -u root –p
Enter password:

#exit postgresql if you want
postgresql> exit  
~~~

## 常见命令

```

PostgreSQL [(none)]> create database 数据库名称;     #特别注意有分号

PostgreSQL [(none)]>  show  databases;                      #查看数据库

PostgreSQL [(none)]>  exit;                                 #退出数据库控制台，特别注意有分号

PostgreSQL [(none)]> drop database 数据库名称;     #删除数据库

PostgreSQL [(none)]> exit;                                     #退出数据库控制台，特别注意有分号

PostgreSQL [(none)]> show databases;           #查看数据库: 如下图中3个数据库是默认数据库，不可删除

```
![websoft9-postgresql](http://libs.websoft9.com/Websoft9/DocsPicture/zh/postgresql/postgresql_databases_default.png)
