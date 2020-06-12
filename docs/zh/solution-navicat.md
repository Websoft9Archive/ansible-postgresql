# 图形化工具：Navicat

如果你已经开启服务器安全组 5432 端口，并设置完成 PostgreSQL 远程连接，可以参考如下的步骤使用 Navicat：

1. 打开Navicat Premium，点击顶部菜单栏， 【文件】>【新建连接】>【PostgreSQL】

2. 自定义连接名，将localhost更改为数据库所在的主机公网IP地址
  ![navicat](http://libs.websoft9.com/Websoft9/DocsPicture/zh/postgresql/navicate-newconnection-websoft9.png)

3. 输入账号和密码（[不知道账号密码？](/zh/stack-accounts.md)）

3. 点击“测试连接”，系统提示：连接成功 ! 即表示成功连接