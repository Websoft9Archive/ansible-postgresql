# 参数

PostgreSQL 预装包包含 PostgreSQL 运行所需一序列支撑软件（简称为“组件”），下面列出主要组件名称、安装路径、配置文件地址、端口、版本等重要的信息。

## 路径

PostgreSQL 安装到 Linux 还是 Windows 系统，对应的路径有很大的差异，请根据实际情况参考：

### Linux

#### PostgreSQL

PostgreSQL 配置文件: */data/postgresql/config*   
PostgreSQL 数据目录：*/data/postgresql/pgdata*   
PostgreSQL 日志目录: */data/postgresql/log*  

> 以上列出的是通过软连接创建的目录，请通过 `locate pg_hba.conf` 这样的命令查询更多文件路径信息

#### phpPgAdmin on Docker

phpPgAdmin 是采用 Docker 方式来安装的  

> Docker 相关路径请查看我们编写的 [Docker 管理员手册](https://support.websoft9.com/docs/docker/zh/stack-components.html)

### Windows

暂无

## 端口号

在云服务器中，通过 **[安全组设置](https://support.websoft9.com/docs/faq/zh/tech-instance.html)** 来控制（开启或关闭）端口是否可以被外部访问。 

通过命令 `netstat -tunlp` 看查看相关端口，下面列出可能要用到的端口：

| 名称 | 端口号 | 用途 |  必要性 |
| --- | --- | --- | --- |
| TCP | 9090 | 通过 HTTP 访问 phpPgAdmin | 可选 |
| TCP | 5432 | 远程连接PostgreSQL | 可选 |

## 版本号

组件版本号可以通过云市场商品页面查看。但部署到您的服务器之后，组件会自动进行更新导致版本号有一定的变化，故精准的版本号请通过在服务器上运行命令查看：

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