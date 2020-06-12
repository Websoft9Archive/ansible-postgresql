# Parameters

The PostgreSQL deployment package contains a sequence software (referred to as "components") required for PostgreSQL to run. The important information such as the component name, installation directory path, configuration file path, port, version, etc. are listed below.

## Path

You should know the components is different for different OS before using PostgreSQL

### Linux

#### PostgreSQL

PostgreSQL data directory: */data/postgresql/pgdata*  
PostgreSQL configuration directory: */data/postgresql/config*  
PostgreSQL logs directory: */data/postgresql/log*  

> The above list is the directory created by soft link, please query more file path information through commands like `locate pg_hba.conf`

#### phpPgAdmin on Docker

We used Docker to install phpPgAdmin

> Get more details about Docker from our documentation [Docker administrator guide](https://support.websoft9.com/docs/docker/stack-components.html)

### Windows Sever

Coming soon...

## Ports

You can control(open or shut down) ports by **[Security Group Setting](https://support.websoft9.com/docs/faq/tech-instance.html)** of your Cloud Server whether the port can be accessed from Internet.

Use the command `netstat -tunlp` to check ports, these ports should be opened for this application:

| Name | Number | Use |  Necessity |
| --- | --- | --- | --- |
| TCP | 9090 | HTTP to visit phpPgAdmin | Optional |
| TCP | 5432 | remote connect PostgreSQL | Optional |

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