# Initial Installation

If you have completed the PostgreSQL deployment on Cloud Platform, the following steps is for you to start use it quikly

## Preparation

1. Get the **Internet IP** on your Cloud Platform
2. Check you **[Inbound of Security Group Rule](https://support.websoft9.com/docs/faq/tech-instance.html)** of Cloud Console to ensure the **TCP:9090** is allowed if you using the phpPgAdmin on Docker
3. Check you **[Inbound of Security Group Rule](https://support.websoft9.com/docs/faq/tech-instance.html)** of Cloud Console to ensure the **TCP:5432** is allowed if you want to connect PostgreSQL from local GUI tools

## PostgreSQL Installation Wizard

### Check PostgreSQL

1. Use the **SSH** to connect Server, and run these command below to view the installation information and running status
   ```
   sudo systemctl status postgresql
   ```
2. You can ge the message from SSH " Active: active (running)... " when PostgreSQL is running

Then, you can login PostgreSQL 

### Login PostgreSQL with commands

Using SSH to connect PostgreSQL Server(or remote to Windows Server), run the following commands

```
sudo -i -u postgres
psql

psql (12.3)
Type "help" for help.

postgres=#
```

### Login PostgreSQL with GUI tool

#### phpPgAdmin

If you used the deployment solution included the phpPgAdmin, the database management is very easy

1. Using local Chrome or Firefox to visit the URL *http://server's Internet IP:9090* to visit phpPgAdmin
  ![login phpPgAdmin](https://libs.websoft9.com/Websoft9/DocsPicture/zh/postgresql/phppgadmin-login-websoft9.png)
2. Input your database account([Don't know password?](/stack-accounts.md#postgresql))
3. Start using phpPgAdmin to modify root password of PostgreSQL
  ![phpMyadmin](https://libs.websoft9.com/Websoft9/DocsPicture/zh/postgresql/phppgadmin-gui-websoft9.png)

#### pgAdmin

1. Using local Chrome or Firefox to visit the URL *http://server's Internet IP:9090* to access pgAdmin
   ![access pgAdmin](https://libs.websoft9.com/Websoft9/DocsPicture/en/postgresql/pgadmin-loginui-websoft9.png)

2. Input pgAdmin administrator account([view username and password](/stack-accounts.md#postgresql)) and enter to console
   ![pgAdmin console](https://libs.websoft9.com/Websoft9/DocsPicture/en/postgresql/pgadmin-console-websoft9.png)

3. Click【Server】 to add PostgreSQL connection([don't known password?](/stack-accounts.md#postgresql))
   ![pgAdmin connect server](https://libs.websoft9.com/Websoft9/DocsPicture/en/postgresql/pgadmin-createserver-websoft9.png)

4. You can enter to pgAdmin console successfully
   ![pgAdmin console](https://libs.websoft9.com/Websoft9/DocsPicture/en/postgresql/pgadmin-console-websoft9.png)

5. Modify password if you want
   ![pgAdmin modify password](https://libs.websoft9.com/Websoft9/DocsPicture/en/postgresql/pgadmin-modifypw-websoft9.png)

> More useful phpPgAdmin guide, please refer to [phpPgAdmin](/solution-phppgadmin.md) or [pgAdmin](/solution-pgadmin.md) of this documentation


## Q&A

#### I can't visit the phpPgAdmin?

Your TCP:9090 of Security Group Rules is not allowed so there no response from Chrome or Firefox

#### How phpPgAdmin or pgAdmin installed?

Install phpPgAdmin or pgAdmin used Docker, that can make sure PostgreSQL environment has good isolation
