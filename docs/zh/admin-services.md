# 服务启停

使用由 Websoft9 提供的 PostgreSQL 部署方案，可能需要用到的服务如下：

## Linux系统

### PostgreSQL
```shell
#For CentOS&Redhat
sudo systemctl start postgresqld
sudo systemctl restart postgresqld
sudo systemctl stop postgresqld
sudo systemctl status postgresqld

#For Ubuntu&Debian
sudo systemctl start postgresql
sudo systemctl restart postgresql
sudo systemctl stop postgresql
sudo systemctl status postgresql
```

### MariaDB
```shell
systemctl start mariadb
systemctl stop mariadb
systemctl restart mariadb
```

### Docker

```shell
sudo systemctl start docker
sudo systemctl restart docker
sudo systemctl stop docker
sudo systemctl status docker
```

## Windows 系统

Windows下的镜像采用操作系统的服务管理功能，来实现 PostgreSQL 的启动、停止和重启操作
![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/postgresql/postgresql-servicewin-websoft9.png)