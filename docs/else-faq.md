# FAQ

#### What is the password for the database root user?

The password is stored in the server related file: `/credentials/password.txt`

#### Is there a web-base GUI database management tools?

Yes, phpPgAdmin is on it, visit by *http://Server Internet IP:9090*

#### Can I connect PostgreSQL from Internet(remote)?

You should enable the remote connection first

#### How to get the status of PostgreSQL?

Run command `ps ``-``ef ``| grep postgresqld` to list postgresql process

#### Can I modify the root directory of PostgreSQL?

Yes, please refer the documentation [Modify PostgreSQL Data Directory](/solution-more.html#modify-postgresql-data-directory)

#### What's the difference between Deployment and Installation?

- Deployment is a process of installing and configuring a sequence of software in sequence in a different order, which is a complex system engineering.  
- Installation is the process of starting the initial wizard after the application is prepared.  
- Installation is simpler than deployment. 

#### What's Cloud Platform?

Cloud platform refers to platform manufacturers that provide cloud computing services, such as: **Azure, AWS, Alibaba Cloud, HUAWEI CLOUD, Tencent Cloud**, etc.

#### What is the difference between Instance, Cloud Server, Virtual Machine, ECS, EC2, CVM, and VM?

No difference, just the terminology used by different manufacturers, actually cloud servers