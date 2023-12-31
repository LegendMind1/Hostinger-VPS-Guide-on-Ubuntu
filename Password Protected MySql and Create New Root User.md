# **How to Set Password for MySQL Root User and Create a New User with Root Privileges**  

**Note - You must login on your operating system or VPS Remote server as root user (Not Sudo User). You can switch from sudo to root.**  

**What is mysql_secure_installation ?**  
- This program enables you to improve the security of your MySQL installation in the following ways:  

1. You can set a password for root accounts  
2.  You can remove root accounts that are accessible from outside the local host.  
3. You can remove anonymous-user accounts.  
4. You can remove the test database (which by default can be accessed by all users, even anonymous users), and privileges that permit anyone to access databases with names that start with test_.  

**What is caching_sha2_password ?**  
It is a Plugins that performs authentication using SHA-256 password hashing. This is stronger encryption than that available with native authentication. There are some other plugins e.g. mysql_native_password.

**Install MySQL If not Installed**  
apt update  
apt upgrade  
apt install mysql-server  

**Login to MySQL**  
mysql  

**Set Password for Root**  
Note: The same ALTER USER query can be used to change the MySql root / user password.
```console
Syntax:- ALTER USER 'user_name'@'localhost' IDENTIFIED WITH caching_sha2_password by 'user_password';
Example:- ALTER USER 'root'@'localhost' IDENTIFIED WITH caching_sha2_password by '#o012345abc#';
```

**Exit from MySQL**  
exit

**Run the mysql_secure_installation Program**  
mysql_secure_installation  

**Login to MySQL as Root User**  
mysql -u root -p

**Create New User**  
```console
Syntax:- CREATE USER 'user_name'@'localhost' IDENTIFIED WITH caching_sha2_password BY 'user_password';
Example:- CREATE USER 'noman'@'localhost' IDENTIFIED WITH caching_sha2_password BY '#o01234abc#';
```

**Grant New User All Privileges**  
```console
Syntax:- GRANT ALL PRIVILEGES ON *.* TO 'user_name'@'localhost' WITH GRANT OPTION;
Syntax:- GRANT ALL PRIVILEGES ON *.* TO 'noman'@'localhost' WITH GRANT OPTION;
```

**Exit from MySQL**  
exit

**Restart Web Server**  
- If Apache  
service apache2 restart

- If Nginx  
service nginx restart

## **Sometimes You may want to open following config file of PhpMyAdmin**  
config-db.php i.e.  
[VPS Server Prompt]:/etc/phpmyadmin$ sudo nano config-db.php  