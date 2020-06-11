# Modify and reset PostgreSQL password

Modify password: Change the current password to another password  
Reset password: Have forgotten your password, need to get an initial password

## Modify password

You can modify password by PostgreSQL GUI or commands:

### Use phpPgAdmin(Recommend) 

![](http://libs.websoft9.com/Websoft9/DocsPicture/zh/postgresql/websoft9-modifypostgresqlpw.gif)

### Use commands
```
postgresqladmin -u root -p oldpassword password 'newpassword' 
```

## Reset password

You can reset your PostgreSQL password by the following two solution:  

### Quick Plan(Recommend) 

1. Use SSH to connect PostgreSQL Server
2. Run the following command
   ```
   sudo git clone https://github.com/Websoft9/linux.git; cd linuxscript/Mysql\_ResetPasswd\_Script;sudo sh reset\_postgresql\_password.sh
   ```
### Manual solution

1. Use SSH to connect PostgreSQL Server
2. Stop PostgreSQL
   ~~~
   sudo systemctl stop postgresqld
   ~~~
3. Use the safe mode to restart PostgreSQL
   ~~~
   sudo postgresqld_safe --skip-grant-tables &
   ~~~
4. Reset password(e.g reset password to `123456`)
   ~~~
   sudo postgresql -e "use postgresql;update user set password=password('123456') where user='root';"
   ~~~
5. Shut down PostgreSQL service
   ~~~
   sudo kill all postgresqld
   ~~~ 
6. Start PostgreSQL service
   ~~~
   sudo systemctl start postgresqld
   ~~~