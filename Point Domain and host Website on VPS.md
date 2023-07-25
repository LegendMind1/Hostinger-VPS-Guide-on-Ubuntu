# **How to Point Domain and Host HTML Website on Remote Server or VPS**  

**Login to Your Domain Provider Website**  

**Navigate to Manage DNS**  

**Add Following Records:**  
**Type**	     **Host/Name**	                **Value**    
A	            @	                    Your Remote Server IP  
A	            www	                    Your Remote Server IP  
AAAA	        @	                    Your Remote Server IPv6  
AAAA	        www	                    Your Remote Server IPv6  

**On Local Windows Machine Make Your Project Folder a Zip File using any of the software e.g. winzip**  

**Open Command Prompt**  
**Copy Zip File from Local Windows Machine to Linux Remote Server**  
Syntax:- scp -P Port_number Source_File_Path Destination_Path  
Example:- scp -P 22 osmsProject.zip root@216.32.44.12:/var/www  


**To Access Remote Server via SSH**  
Syntax:- ssh -p PORT USERNAME@HOSTIP  
Example:- ssh -p 22 username@xxx.xxx.xxx.xxx  

**Note:- Run Below Commands on Your Remote Server Linux Machine or VPS, Not on Your Local Windows Machine**  

**Go to the Destination Path Where you copied the zip file**  
Syntax:- cd Destination_Path  
Example:- cd /var/www  

**Run ls command to verify that the zip file is present**  
ls  

**Unzip the Copied Zip File**  
Syntax:- unzip zip_file_name  
Example:- unzip osmsProject.zip  

**Verify that all required softwares are installed**  
apache2 -v  
mysql  
php -v  

**Verify Apache2 is Active and Running**  
service apache2 status  

**Verify Web Server Ports are Open and Allowed through Firewall**  
ufw status verbose  

**Create Virtual Host File**  
nano /etc/apache2/sites-available/your_domain.conf  

**Add Following Code in Virtual Host File**  

<VirtualHost *:80>  
    ServerName www.example.com  
    ServerAdmin contact@example.com  
    DocumentRoot /var/www/project_folder_name  
    ErrorLog ${APACHE_LOG_DIR}/error.log  
    CustomLog ${APACHE_LOG_DIR}/access.log combined  
</VirtualHost>  
  
**Enable Virtual Host**  
cd /etc/apache2/sites-available/  
a2ensite your_domain.conf  

**You can Disable Default Virtual Host**  
cd /etc/apache2/sites-available/  
a2dissite 000-default.conf

**Restart Apache2**  
service apache2 restart  

### **Important Notes**  

1. **Note: In order to point http to https create / update .htaccess in the root of the website i.e. /var/www/[website folder]/.htaccess then insert the following code:**

RewriteEngine On
RewriteCond %{HTTPS} off
RewriteRule ^(.*)$ https://%{HTTP_HOST}%{REQUEST_URI} [L,R=301]  


2. **Note: In order to Force HTTPS on a Specific Folder**
RewriteEngine On 
RewriteCond %{HTTPS} off 
RewriteRule ^(folder1|folder2|folder3) https://%{HTTP_HOST}%{REQUEST_URI} [R=301,L]