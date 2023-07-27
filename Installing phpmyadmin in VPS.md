# **How to Install phpmyadmin with Apache Web Server**   
**Install phpMyAdmin and Other Plugins**   
Note: You should be logged in as User in VPS and not in MySql

```console
apt update  
apt upgrade  
apt install phpmyadmin php-mbstring php-zip php-gd php-json php-curl  
```
- php-mbstring: A module for managing non-ASCII strings with different encodings  
- php-zip: An extension that facilitates uploading .zip files to phpMyAdmin  
- php-gd: Enables support for GD graphics library  
- php-json: Provides support for JSON serialization  
- php-curl: Allows PHP to communicate with other servers  

### **Screen Walkthrough**  
1. Webserver to reconfigure automatically: apache2 (use Space key to select)
2. Configuring with dbconfig-common?: Yes
3. Password for PhpMyAdmin: [password] it will overwrite existing root password of MySql
4. If strong password error occured: Choose Exit and Retry to move forward
5. Configuring with dbconfig-common?: Yes
6. Connection Method for MySql Database of PhpMyAdmin: Unix Socket
7. Authentication with MySql method: caching_sha2_password [This was installed earlier during MySql Installation see the relevant repo for information]
8. Name of PhpMyAdmin Database: [Name of your choice]
9. MySql Username for PhpMyadmin: root
10. MySql Password for PhpMyAdmin User: Give password already given at Step 3
11. MySql Application Password for PhpMyAdmin: Give Password already given at Step 3    
12. You may now login through Browser by navigating to [VPS Host Address]/phpmyadmin