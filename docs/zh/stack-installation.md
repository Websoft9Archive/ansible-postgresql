# 初始化验证

在云服务器上部署 PostgreSQL 预装包之后，请参考下面的步骤快速入门。

## 准备

1. 在云控制台获取您的 **服务器公网IP地址** 
2. 如果想从本地客户端远程连接 PostgreSQL，登录云控制台安全组中，检查 **Inbound（入）规则** 下的 **TCP:5432** 端口是否开启
3. 如果想使用可视化管理工具 phpPgAdmin，登录云控制台安全组中，检查 **Inbound（入）规则** 下的 **TCP:9090** 端口是否开启

## PostgreSQL 初始化验证

部署 PostgreSQL 之后，依次完成下面的步骤，验证其可用性

### 检测 PostgreSQL 安装

1. 使用 SSH 连接 PostgreSQL 所在的服务器，运行下面的命令，查看 PostgreSQL 的安装信息和运行状态
   ```
   sudo systemctl status postgresql
   ```
2. 运行服务状态查询命令，PostgreSQL 正常运行会得到 " Active: active (running)... " 的反馈

镜像安装完成后，PostgreSQL就可以使用了。使用PostgreSQL有两种方式方式

### 命令方式连接 PostgreSQL

先切换到 postgre 用户，在运行 `psql` 命令，即可使用 psql 连接数据库

```
sudo -i -u postgres
psql

psql (12.3)
Type "help" for help.

postgres=#
```

### 图形化工具连接 PostgreSQL

如果部署方案中包含 phpPgAdmin 或 pgAdmin 图形化工具，使用就更加便捷方便：

#### phpPgAdmin

1. 本地浏览器 Chrome 或 Firefox 访问：*http://服务器公网IP:9090*，进入 phpPgAdmin
   ![登录phpPgAdmin](https://libs.websoft9.com/Websoft9/DocsPicture/zh/postgresql/pgadmin.png)
   图1. phpPgAdmin 界面

2. 输入数据库用户名和密码([不知道密码？](/zh/stack-accounts.md#postgresql))

3. 开始管理数据库
   ![phpPgadmin](https://libs.websoft9.com/Websoft9/DocsPicture/zh/postgresql/phppgadmin-gui-websoft9.png)

#### pgAdmin

1. 本地浏览器 Chrome 或 Firefox 访问：*http://服务器公网IP:9090*，进入 pgAdmin
   ![登录pgAdmin](https://libs.websoft9.com/Websoft9/DocsPicture/zh/postgresql/pgadmin-loginui-websoft9.png)

2. 输入 pgAdmin 管理员的用户名和密码([查看账号密码](/zh/stack-accounts.md#postgresql))之后，进入控制台
   ![pgAdmin 控制台](https://libs.websoft9.com/Websoft9/DocsPicture/zh/postgresql/pgadmin-console-websoft9.png)

2. 点击【Server】>【添加服务器】，使用 pgAdmin 连接 PostgreSQL 数据库([不知道密码？](/zh/stack-accounts.md#postgresql))
   ![pgAdmin 连接服务器](https://libs.websoft9.com/Websoft9/DocsPicture/zh/postgresql/pgadmin-createserver-websoft9.png)

3. 开始管理数据库
   ![pgAdmin 管理数据库](https://libs.websoft9.com/Websoft9/DocsPicture/zh/postgresql/pgadmin-serverss-websoft9.png)

4. 修改密码
   ![pgAdmin 修改密码](https://libs.websoft9.com/Websoft9/DocsPicture/zh/postgresql/pgadmin-modifypw-websoft9.png)

> 需要了解更多使用，请参考本文档 [phpPgAdmin 章节](/zh/solution-phppgadmin.md) 或  [pgAdmin 章节](/zh/solution-pgadmin.md) 


## 常见问题

#### 浏览器无法访问图形化界面（白屏没有结果）？

您的服务器对应的安全组 9090 端口没有开启（入规则），导致浏览器无法它

#### phpPgAdmin 或 pgAdmin 是如何安装的？

采用 Docker 安装，保证 PostgreSQL 环境具有良好的隔离性。

#### 为什么我的系统中没有 pgAdmin ？

由于产品设计原因，我们从 2021年2月之后的产品中才包含 pgAdmin