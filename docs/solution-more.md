# More

Each of the following solutions has been proven to be effective and we hope to be helpful to you.

## Set remote connection

If you want to use customer tool (e.g Navicat/pgAdmin) on your local computer to connect PostgreSQL Server, you should set your remote connection first.  

The database is a high-security application, set up remote access, at least two independent steps:

#### Enable **TCP:5432** port on your Cloud Platform

PostgreSQL is used **5432** port by default, you should login Cloud Platform to enabled this port

#### Modify the PostgreSQL configuration files

Then, you should set your PostgreSQL configuration files so that PostgreSQL can be accessed by external networks

1. Modify the configuration file [postgresql.conf](/zh/components.md#postgresql) 
   ```
   #listen_addresses = 'localhost'

   is set to

   listen_addresses = '*'
   ```

2. Modify the configuration file [pg_hba.conf]((/zh/components.md#postgresql)) , add the following line at the end of it
   ```
   host    all             all             0.0.0.0/0            md5
   ```

3. Restart PostgreSQL
   ```
   systemctl restart postgresql
   ```

## Password Management

PostgreSQL customer tool can connect PostgreSQL server by **Unix socket** directly, so you can modify your password without authentication

```
# change to user postgres
sudo -u postgres psql

# modify your password
ALTER USER postgres WITH PASSWORD 'postgres';

#exit psql
\q
```

## Change PGDATA directory

1. Backup all files on you PGDATA */data/postgresql/pgdata* 
2. Change the PGDATA directory by different Linux distribution

   * RedHat/CentOS: modify the file **postgreql.service** 
      ```
      # cat postgresql.service directory
      systemctl cat postgreql.service 

      # modify the  Environment=PGDATA in the file postgresql.servce
      Environment=PGDATA=/var/lib/pgsql/11/data/
      ```
   * Ubuntu: modify the file **postgresql.conf** 
     ```
     data_directory =
     ```
3. Restore all data from your backup
4. Restart your PostgreSQL service