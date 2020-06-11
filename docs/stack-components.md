# Parameters

The PostgreSQL deployment package contains a sequence software (referred to as "components") required for PostgreSQL to run. The important information such as the component name, installation directory path, configuration file path, port, version, etc. are listed below.

## Path

You should know the components is different for different OS before using PostgreSQL

### Linux

#### PostgreSQL

PostgreSQL data directory: */data/postgresql/pgdata*  
PostgreSQL configuration directory: */data/postgresql/config*  
PostgreSQL logs directory: */data/postgresql/log*  

> 以上列出的是通过软连接创建的目录，请通过 `locate pg_hba.conf` 这样的命令查询更多文件路径信息

#### phpPgAdmin on Docker

We used Docker to install phpPgAdmin

> Docker 相关路径请查看我们编写的 [Docker 管理员手册](https://support.websoft9.com/docs/docker/zh/stack-components.html)

### Windows Sever

Coming soon...

## Ports

You can control(open or shut down) ports by **[Security Group Setting](https://support.websoft9.com/docs/faq/tech-instance.html)** of your Cloud Server whether the port can be accessed from Internet.

通过命令 `netstat -tunlp` 看查看相关端口, These ports should be opened for this application:

| Name | Number | Use |  Necessity |
| --- | --- | --- | --- |
| phpPgAdmin on Docker | 9090 | HTTP to visit phpPgAdmin | Optional |
| PostgreSQL | 3306 | remote connect PostgreSQL | Optional |
| TCP | 9090 | 通过 HTTP 访问 phpPgAdmin | 可选 |
| TCP | 5432 | 远程连接PostgreSQL | 可选 |

## Version

You can see the version from product page of Marketplace. However, after being deployed to your server, the components will be automatically updated, resulting in a certain change in the version number. Therefore, the exact version number should be viewed by running the command on the server:

```shell
# Check all components version
sudo cat /data/logs/install_version.txt

# Linux Version
lsb_release -a

# PostgreSQL version
psql -V

# PostgreSQL Version
docker -v
```