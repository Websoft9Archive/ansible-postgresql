# 更新升级

网站技术日新月异，**更新升级**是维护工作之一，长时间不升级的程序，就如长时间不维护的建筑物一样，会加速老化、功能逐渐缺失直至无法使用。  

这里注意更新与升级这两词的差异（[延伸阅读](https://support.websoft9.com/docs/faq/zh/tech-upgrade.html#更新-vs-升级)），例如：  

- 操作系统打个补丁常称之为**更新**，Ubuntu16.04 变更为 Ubuntu18.04，称之为**升级**
- PostgreSQL5.6.25-->PostgreSQL5.6.30 常称之为**更新**，PostgreSQL5.6->PostgreSQL5.7 称之为**升级**

PostgreSQL 完整的更新升级包括：系统级更新（操作系统和运行环境）和 PostgreSQL 程序升级两种类型

## 系统级更新

运行一条更新命令，即可完成系统级更新：

``` shell
#For Ubuntu&Debian
apt update && apt upgrade -y

#For Centos&Redhat
yum update -y
```
> 本部署包已预配置一个用于自动更新的计划任务。如果希望去掉自动更新，请删除对应的Cron

## PostgreSQL 更新升级

PostgreSQL 提供了大版本升级工具 pg_upgrade。升级总是比较复杂，这里只列出 pg_upgrade 常用参数

```
pg_upgrade --help

pg_upgrade upgrades a PostgreSQL cluster to a different major version.

Usage:
  pg_upgrade [OPTION]...

Options:
  -b, --old-bindir=BINDIR       old cluster executable directory
  -B, --new-bindir=BINDIR       new cluster executable directory
  -c, --check                   check clusters only, don't change any data
  -d, --old-datadir=DATADIR     old cluster data directory
  -D, --new-datadir=DATADIR     new cluster data directory
  -j, --jobs=NUM                number of simultaneous processes or threads to use
  -k, --link                    link instead of copying files to new cluster
  -o, --old-options=OPTIONS     old cluster options to pass to the server
  -O, --new-options=OPTIONS     new cluster options to pass to the server
  -p, --old-port=PORT           old cluster port number (default 50432)
  -P, --new-port=PORT           new cluster port number (default 50432)
  -r, --retain                  retain SQL and log files after success
  -U, --username=NAME           cluster superuser (default "root")
  -v, --verbose                 enable verbose internal logging
  -V, --version                 display version information, then exit
  -?, --help                    show this help, then exit

Before running pg_upgrade you must:
  create a new database cluster (using the new version of initdb)
  shutdown the postmaster servicing the old cluster
  shutdown the postmaster servicing the new cluster

When you run pg_upgrade, you must provide the following information:
  the data directory for the old cluster  (-d DATADIR)
  the data directory for the new cluster  (-D DATADIR)
  the "bin" directory for the old version (-b BINDIR)
  the "bin" directory for the new version (-B BINDIR)

For example:
  pg_upgrade -d oldCluster/data -D newCluster/data -b oldCluster/bin -B newCluster/bin
or
  $ export PGDATAOLD=oldCluster/data
  $ export PGDATANEW=newCluster/data
  $ export PGBINOLD=oldCluster/bin
  $ export PGBINNEW=newCluster/bin
  $ pg_upgrade

Report bugs to <pgsql-bugs@postgresql.org>.
```