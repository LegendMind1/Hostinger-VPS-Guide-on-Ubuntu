# **Passowrd Protection in Website running on Apache Hosted on Linux Remote Server or VPS**  

**Create Login Credentials**  
htpasswd -c /etc/apache2/.htpasswd user_name  

**Verify that Credential has been Created**  
cat /etc/apache2/.htpasswd  

**Go to /etc/apache2/sites-available**  
cd /etc/apache2/sites-available  

**Open the Required Virtual Host File**  
nano 000-default.conf  

**Add below Content**  
<Directory /var/www/html/admin>  
        AuthType Basic  
        AuthName "admin area"  
        AuthUserFile /etc/apache2/.htpasswd  
        Require valid-user  
<[/]Directory>  

**Restart Apache**  
service apache2 restart  