# PostgreSQL remote connection

Most of the time, if you want to use GUI tools to manage PostgreSQL on you local computer, you shoud open the remote connection of PostgreSQL. 

Database is high security application, you need two steps for remote connection settings at least:

## Enable the TCP:3306 port

In general, PostgreSQL uses port 3306.

First, you must go to the Cloud Console and enable the **TCP:3306** port of Security Group
![](http://libs.websoft9.com/Websoft9/DocsPicture/zh/postgresql/postgresql3306-websoft9.png)


## Open PostgreSQL remote connection

After the security group is turned on, the setup of the PostgreSQL remote solution has not been completed.

Next, you need to set up PostgreSQL itself so that it can access external networks

We provide two solutions to open the remote connection of PostgreSQL. The first is GUI and the second is the command mode:

#### Use GUI(recommend)

To enable remote in phpPgAdmin, you only need to change the access mode of the root account to "any way to access", as follows:

1. Log in phpPgAdmin, go to User account->Edit privileges of root account
   ![](http://libs.websoft9.com/Websoft9/DocsPicture/en/phppgadmin/phppgadmin-modifypw001-websoft9.png)

2. Select the tab Login Information, Host Name fill in "%", click "Go" button completing this setting
   ![](http://libs.websoft9.com/Websoft9/DocsPicture/en/phppgadmin/phppgadmin-modifypw002-websoft9.png)

#### Use commands

If you have not installed phpPgAdmin or other GUI tools in you Server, you should use command to open the PostgreSQL remote connection:

1. Use SSH to connect PostgreSQL Server
   ```
   sudo postgresql -u root -p password
   ```
 
2. Open the remote connection
   ```
   postgresql>  use postgresql;
   postgresql>  update user set host = '%' where user = 'root';
   ```

3. Test it
   ```
   select host,user from user where user='root'
   ```
4. Exit PostgreSQL command mode, return to Linux and restart it
   ```
   sudo systemctl restart postgresqld
   ```
   > This step is necessary, otherwise Navicat Premium/PostgreSQL-Front can't connect to PostgreSQL