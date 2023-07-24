# **How to Install LAMP (Linux Apache MySQL PHP) Stack**  

**To Get Access via SSH**  
Syntax:- ssh -p PORT USERNAME@HOSTIP  
Example:- ssh -p 22 root@216.32.44.12  

**Updates the package lists for Upgrades then Upgrades**  
1. apt update  
2. apt upgrade  
3. Install Apache  
4. apt install apache2  

**(Optional) If Get Error While Installation "cannot stat '/usr/share/apache2/default-site/index.html': No such file or directory dpkg: error processing package apache2 (--configure)" then Try to Install Again**  
apt purge apache2-data  

**Allow Apache through Firewall**  
ufw allow "Apache Full"  

**Check Server IP on Web Browser You will see Apache Default Page**  
1. Install MySQL  
2. apt install mysql-server  
3. Install PHP  
4. apt install php libapache2-mod-php php-mysql  

**The above command includes three packages:-**  
1. php -  To Install PHP  
2. libapache2-mod-php - It is Used by apache to handle PHP files  
3.  php-mysql - It is a PHP module that allows PHP to connect to MySQL  

**To Restart Apache**  
service apache2 restart  