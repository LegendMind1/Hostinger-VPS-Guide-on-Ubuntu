# **Steps to be taken after fresh install of VPS OS**  

1.  **Delete C:\users\[username]\.ssh\known_hosts file in Win OS**  
Note: You may also need to use 'Reset SSH' option under Settings>SSH Configuration in Hostinger VPS Panel

### **Now Login to root@xxx.xxx.xxx.xxx of the VPS**  

**Firstly Set TimeZone**  
Syntax:- timedatectl set-timezone [timezone]  
Example:- timedatectl set-timezone Asia/Karachi  

2.  **Change default Port number in /etc/ssh/sshd_config file**

3.  **Restart ssh service using 'service ssh restart' command**

4.  **Add new user 'adduser' command**  

5.  **Give sudo privileges to new user using 'usermod -aG sudo [username]' command**

6.  **Prevent Root Login in /etc/ssh/sshd_config file**  

7.  **Rstart ssh srvice**  

8.  **Install firewall using 'sudo apt install ufw' command**  

9.  **Check status and allow essential services and port numbers through firewall**

10. **Enable firewall using 'sudo ufw enable' command** 

11. **Install Apache**  
- sudo apt update   
- sudo apt upgrade  
- sudo apt install apache2

12. **Allow Apache through Firewall**  
ufw allow "Apache Full"  
**Note:** At this point check Server IP on Web Browser You will see Apache Default Page  

13. **Install MySQL**  
apt install mysql-server  

**Aftr this, you may want to check installation success through following commands**  
- mysql -v  ---> Vrsion checking
- mysql  ---> Go to **mysql prompt**  
- show databases;  ---> MySql command to show all available databases


14. ### **Install PHP**  
apt install php libapache2-mod-php php-mysql  

**The above command includes three packages:-**  
- php --->  To Install PHP  
- libapache2-mod-php ---> It is Used by apache to handle PHP files  
- php-mysql ---> It is a PHP module that allows PHP to connect to MySQL  

15. **To Restart Apache**  
service apache2 restart 

16. **Point Domain to VPS**  

17. **Install SSL Crtificate**  



