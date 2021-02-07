# Start or Stop the Services

These commands you must know when you using the PostgreSQL of Websoft9

### Linux

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

### Windows

For Windows Sever, please use the system's services management to start | stop | restart PostgreSQL  