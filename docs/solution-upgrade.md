# Update & Upgrade

Updates and upgrades are one of the maintenance tasks for system. Programs that are not upgraded for a long time, like buildings that are not maintained for a long time, will accelerate aging and gradually lose functionality until they are unavailable.

You should know the differences between the terms **Update** and **Upgrade**([Extended reading](https://support.websoft9.com/docs/faq/tech-upgrade.html#update-vs-upgrade))
- Operating system patching is **Update**, Ubuntu16.04 to Ubuntu18.04 is **Upgrade**
- PostgreSQL5.6.25 to PostgreSQL5.6.30 is **Update**, PostgreSQL5.6 to PostgreSQL5.7 is **Upgrade**

For PostgreSQL maintenance, focus on the following two Update & Upgrade jobs

- System update(Operating System and Running Environment) 
- PostgreSQL upgrade 

## System Update

Run an update command to complete the system update:

``` shell
#For Ubuntu&Debian
apt update && apt upgrade -y

#For Centos&Redhat
yum update -y
```
> This deployment package is pre-configured with a scheduled task for automatic updates. If you want to remove the automatic update, please delete the corresponding Cron

## PostgreSQL Upgrade

PostgreSQL provides a major version upgrade tool **pg_upgrade**. Upgrading is always more complicated, only the common parameters of **pg_upgrade** are listed here

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