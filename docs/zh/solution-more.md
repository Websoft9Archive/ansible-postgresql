# 更多...

下面每一个方案，都经过实践证明行之有效，希望能够对你有帮助

## 设置远程访问

当你想通过本地的电脑的 PostgreSQL 客户端（例如：Navicat/pgAdmin）连接服务器上的 PostgreSQL 的时候，就需要设置 PostgreSQL 的远程访问。

数据库是高安全应用，设置远程访问，最少两个独立的步骤：

### 云控制台放通 5432 端口

一般来说，PostgreSQL使用的是 **5432** 端口。

首先，我们要登录到云控制台，打开云服务器所在的安全组中，保证3306端口是开启的。

### 修改 PostgreSQL 配置文件

安全组开启后，还没有完成 PostgreSQL 远程方案的设置。 接下来，还需要对 PostgreSQL 配置文件进行设置，以便其接受外部网络的访问

1. 修改 [postgresql.conf](/zh/components.md#postgresql) 文件
   ```
   #listen_addresses = 'localhost'

   修改为

   listen_addresses = '*'
   ```

2. 修改 [pg_hba.conf]((/zh/components.md#postgresql)) 文件，增加如下一行到文件末尾
   ```
   host    all             all             0.0.0.0/0            md5
   ```

3. 重启 PostgreSQL 后生效
   ```
   systemctl restart postgresql
   ```

## 密码管理

对于 PostgreSQL 来说，由于可以通过 Unix 套字节在无需验证的情况下登录数据库，因此修改密码和重置密码都是同样的操作：

```
# 切换到 postgres 用户
sudo -u postgres psql

# 修改密码
ALTER USER postgres WITH PASSWORD 'postgres';

#exit psql
\q
```

## 更换数据文件路径

1. 备份 */data/postgresql/pgdata* 目录下的所有数据
2. 根据不同的操作系统分别设置

   * RedHat/CentOS  修改 **postgreql.service** 文件中数据目录的环境变量
      ```
      # 查看postgresql.service位置
      systemctl cat postgreql.service 

      # 在 postgresql.servce 中找到下面这行，修改之
      Environment=PGDATA=/var/lib/pgsql/11/data/
      ```
   * Ubuntu  修改 **postgresql.conf** 文件中数据目录
     ```
     data_directory =
     ```
3. 恢复数据到新的目录
4. 重启 PostgreSQL 服务