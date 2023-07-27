# **How to Remove Apache2 from Remote Server or VPS having Ubuntu OS**  

**Stop Apache Service**  
service apache2 stop  

**Remove and Cleanup all apache2 packages**  
apt purge apache2 apache2-utils apache2.2-bin apache2-common  
//or  
apt purge apache2 apache2-utils apache2-bin apache2.2-common  

**Remove other dependencies**  
apt autoremove  

**Check if There is any Folder or File**  
whereis apache2  

**Remove if found any**  
Syntax:- rm -r File_or_Folder_Path  
Syntax:- rm -r /etc/apache2  