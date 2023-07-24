# **How to Copy File from Windows to Linux Remote Server or VPS**  

**Note:- Best way is to copy Complete Project Folder by making it a Zip File then Unzip it on Server.**  

### **On Local Windows Machine Make Your Project Folder a Zip File using any of the software e.g. winzip using following steps**  

**Open Command Prompt**  
**Copy Zip File from Local Windows Machine to Linux Remote Server**  
Syntax:- scp -P Port_number Source_File_Path Destination_Path  
Example:- scp -P 22 myproj.zip root@xxx.xxx.xxx.xxx:/var/www  

**To Access Remote Server via SSH**  
Syntax:- ssh -p PORT USERNAME@HOSTIP  
Example:- ssh -p 22 root@xxx.xxx.xxx.xxx.   

### **Note:- Run Below Commands on Your Remote Server Linux Machine or VPS, Not on Your Local Windows Machine**  

**Go to the Destination Path Where you copied the zip file**  
Syntax:- cd Destination_Path  
Example:- cd /var/www  

**Run ls command to verify that the zip file is present**  
ls


**Unzip the Copied Zip File**  
Syntax:- unzip zip_file_name  
Example:- unzip myproj.zip  

# **How to Copy File from Linux Remote Server or VPS to Windows Local Machine**  

**Note:- You can Copy Complete Project Folder by making it a Zip File then Unzip it on Local Machine.**  

**To Access Remote Server via SSH**  
Syntax:- ssh -p PORT USERNAME@HOSTIP  
Example:- ssh -p 22 root@xxx.xxx.xxx.xxx  

**Install zip**  
apt install zip  

**On VPS or Linux Remote Server Make Your Project Folder a Zip File**  

**Zip the Folders and Files**  
Syntax:- zip -r zip_filename.zip target_folder_name  
Example:- zip -r myproj.zip myproj  

**Note:- Run Below Commands on Your Local Windows Machine, Not on Your Remote Server Linux Machine or VPS**  

**Open Command Prompt**

**Copy Zip File from Linux Remote Server to Local Windows Machine**  
Syntax:- scp -P Port_number Source_File_Path Destination_Path  
Example:- scp -P 22 root@2xxx.xxx.xxx.xxx:/var/www/myproj.zip D:\new\  

**Copied Successfully!**