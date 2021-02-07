# 账号密码

通过**SSH**连接云服务器，运行 `sudo cat /credentials/password.txt` 命令，查看所有相关账号和密码

![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/common/catdbpassword-websoft9.png)

下面列出可能需要用到的几组账号密码：

## PostgreSQL

- Linux 系统

   * 管理员账号：*`postgres`*
   * 管理员密码：存储在您的服务器中的文件中 */credentials/password.txt*  

- Window 系统

     **密码存储路径**：*C:/credentials/password.txt*     
     **获取方式**： 远程桌面到服务器，打开此文件即可   

 > 需要登录PostgreSQL，请参考图形化工具 [phpPgAdmin](/zh/solution-phppgadmin.md) 或 [PgAdmin](/zh/solution-pgadmin.md)

## phpPgAdmin

phpPgAdmin 共用 PostgreSQL 的账号密码

## pgAdmin 

pgAdmin 有自己的账号密码体系：

* 管理员账号: `user@domain.com`
* 管理员密码: `存储在您的服务器中的文件中 */credentials/password.txt*  

> 登录 pgAdmin 之后请务必修改它的密码

## Linux

* 主机地址：服务公网IP地址
* 连接方式：云控制台在线SSH 或 SFTP客户端工具 或 SSH客户端工具
* 管理员密码：创建服务器的时候自行设置，若不记得密码需要通过云控制台重置。
* 管理员账号：不同的云平台有一定的差异
   |  云平台   |  管理员账号   | 其他|
   | --- | --- | --- |
   |  Azure   |  创建服务器的时候自行设置   | [如何开启root账户？](https://support.websoft9.com/docs/azure/zh/server-login.html#示例2：启用系统root账号) |
   |  AWS CentOS 系统   |  centos   | [如何开启root账户？](https://support.websoft9.com/docs/aws/zh/server-login.html#示例2：启用系统root账号) |
   |  AWS AmazonLinux 系统   | ec2-user   | [如何开启root账户？](https://support.websoft9.com/docs/aws/zh/server-login.html#示例2：启用系统root账号) |
   |  AWS Ubuntu 系统  |  ubuntu   | [如何开启root账户？](https://support.websoft9.com/docs/aws/zh/server-login.html#示例2：启用系统root账号)  |
   |  阿里云，华为云，腾讯云   |  root   | |
   
## Windows

* 主机地址：服务公网IP地址
* 连接方式：云控制台在线管理 或 远程桌面工具
* 管理员密码：创建服务器的时候自行设置，若不记得密码需要通过云控制台重置。
* 管理员账号：不同的云平台有一定的差异
   |  云平台   |  管理员账号   |
   | --- | --- |
   |  Azure   |  创建服务器的时候自行设置   |
   |  AWS，阿里云，华为云，腾讯云   |  administrator   |
