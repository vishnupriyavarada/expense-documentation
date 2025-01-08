# MySQL

Developer has chosen the database MySQL. Hence, we are trying to install it up and configure it.

**Versions of the DB Software you will get context from the developer, Meaning we need to check with developer.**

Prior to installation. Once you connect to server , switch to root user

```
sudo su -
```

Install MySQL Server 8.0.x

```
dnf install mysql-server -y
```
Note : when you install mysql, automatically mysql client also get installed or comes with mysql. we do not have to install it separately

Start MySQL Service

```
systemctl enable mysqld
```
```
systemctl start mysqld
```

Generally we use below 3 commands to check the health of DB server       

        To check the status of mysqld. to check all database is up and running and active or not.
        
        1) systemctl status mysqld
        
        another command to check the status

        2)  ps -ef | grep mysql
       
        To check port is opened or not 
     
        3) netstat -nltp
        
Next, We need to change the default root password in order to start using the database service. Use password ExpenseApp@1 or any other as per your choice.
By default, SQL comes without password. we need to set password. if we don't set password then when ever we try to start mysql service or login it keeps on asking password and authentication fails to the server
```
mysql_secure_installation --set-root-pass ExpenseApp@1
```

## Verification

We can check data by using client package called mysql.
        Note: server always need a client to serve.
        for ex: Linux server client is GitBash or mobaxtream.
        similarly to connect to mysql server we need a mysql client. mysql client is nothing but mysql command line.

Usually command to connect mysql server is

```
mysql -h <host-address> -u root -p<password>
```

But if your client and server both are in a single server, you can simply issue.

```
mysql
```

Once you got mysql prompt, you can use below command to check schemas/databases exist.

```
show databases;
```

Once you are in particular schema, you can get the list of tables.
schema is something like a wardrobe where we allocate some shelves for children, few more shelves for spouse and some are for self. similarly schema/database is like a shelf.
schema is a logical separation. for ex: want to see tables in sys schema 

```
use sys schema;

show tables;
```

if you want to connect to mysql database. command is ... use mysql;

```
use mysql;

show tables;
```

You can get entries of a table using

```
select * from <table_name>;
```
To exit MySQL client in Linux, you can: 

```
EXIT
```
or
```
Ctrl-D
```
or
```
\quit, \q, or \exit
```

