# FAQ

#### phpPgAdmin 与 pgAdmin 哪个更好？

pgAdmin

#### pgAdmin 支持多语言吗？

支持数十种语言（包含中文）

#### pgAdmin 是什么类型的客户端？

pgAdmin 是通过浏览器访问的客户端，即使在 Windows 下安装，也是间接调用浏览器来访问的

#### 什么是 PostgreSQL 的 Client 和 Server？

PostgreSQL Server 是指 PostgreSQL 程序本体，而 PostgreSQL Client 指采用TCP协议用于连接程序本地的客户端工具。  

它们是两个完全不同的程序，也就是说它们并需要同时安装到同一台服务上。

#### PostgreSQL 安装后有默认数据库吗？

有，名称为 postgres

#### 是否可以修改 PostgreSQL 根目录？

可以，但不建议修改，除非你需要将数据库整体迁移到数据盘

#### 数据库 postgres 用户对应的密码是多少？

密码存放在服务器相关文件中：`/credentials/password.txt`

#### 是否有可视化的数据库管理工具？

有，采用 Docker 部署的 phpPgAdmin 或 pgAdmin，通过：*http://服务器公网IP:9090* 访问

#### 部署和安装有什么区别？

部署是将一序列软件按照不同顺序，先后安装并配置到服务器的过程，是一个复杂的系统工程。  
安装是将单一的软件拷贝到服务器之后，启动安装向导完成初始化配置的过程。  
安装相对于部署来说更简单一些。 

#### 云平台是什么意思？

云平台指提供云计算服务的平台厂家，例如：Azure,AWS,阿里云,华为云,腾讯云等

#### 实例，云服务器，虚拟机，ECS，EC2，CVM，VM有什么区别？

没有区别，只是不同厂家所采用的专业术语，实际上都是云服务器

#### 推荐一些不错的学习资料？

* [从pg_hba.conf文件谈谈postgresql的连接认证](https://www.cnblogs.com/flying-tiger/p/5983588.html?tdsourcetag=s_pcqq_aiomsg)