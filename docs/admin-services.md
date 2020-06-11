# Start or Stop the Services

These commands you must know when you using the PostgreSQL of Websoft9

## Linux

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

## Windows

For Windows Sever, please use the system's services management to start | stop | restart PostgreSQL  
![](https://libs.websoft9.com/Websoft9/DocsPicture/en/postgresql/postgresql-servicewin-websoft9.png)