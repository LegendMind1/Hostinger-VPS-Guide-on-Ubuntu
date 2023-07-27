# **Ubantu Commands to be used un VPS**  

https://www.hostinger.com/tutorials/ssh/basic-ssh-commands

1. clear  ----> clear screen
2. whoami    ---> see who is logged in user
3. cd\ ---> To root directory
4. cd ~ ---> Change propmt to load system folders path
5. cd / ---> Change Propmt to load server folders path
6. cd ..  ---> Drop current directory
7. rm -r [dir/filename]  ---> Delete directory/ file
8. nano [pathe and filename] ----> File reader writer 
9. lsb_release -a && ip r  ---> See which Ubantu version installed 
10. apt install unzip ---> Install Unzip
11. unzip [filename] ---> Unzip a zip file
   
**Add / Manage Users**  
1. adduser [username]   ----> Add new user
2. cut -d: -f1 /etc/passwd    ----> see all users in Ubuntu
3. deluser [username]. ----> Delete user 
4. groups [username]     ----> see group of the user
5. rm -r [username].  ----> Remove user home directory 
6. usermod -aG sudo [username] ----> make user a root user
7. grep -Po '^sudo.+:\K.*$' /etc/group    ----> See which users belong to sudo group 

**Change SSH port**  
1. nano /etc/ssh/sshd_config  ----> open ssh configuration file
2. Change ---> Port [any number from 1024 to 65535]
3. service ssh restart  ----> restart the ssh service
4. service ssh status  ---> Check SSH service status

**Check status of any service**  
1. service apache2 status