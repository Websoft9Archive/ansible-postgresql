# 服务启停

使用由 Websoft9 提供的 PostgreSQL 部署方案，可能需要用到的服务如下：

### Linux系统

#### PostgreSQL
```shell
sudo systemctl start postgresql
sudo systemctl restart postgresql
sudo systemctl stop postgresql
sudo systemctl status postgresql
```

#### Docker

```shell
sudo systemctl start docker
sudo systemctl restart docker
sudo systemctl stop docker
sudo systemctl status docker
```

#### pgAdmin

```shell
sudo docker start pgadmin
sudo docker restart pgadmin
sudo docker stop pgadmin
sudo docker stats pgadmin
```


#### phpPgAdmin

```shell
sudo docker start pgadmin
sudo docker restart pgadmin
sudo docker stop pgadmin
sudo docker stats pgadmin
```

### Windows 系统

Windows下的镜像采用操作系统的服务管理功能，来实现 PostgreSQL 的启动、停止和重启操作