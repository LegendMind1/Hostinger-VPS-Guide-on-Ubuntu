# **Ubantu Commands to be used un VPS**  

https://www.hostinger.com/tutorials/ssh/basic-ssh-commands


1. clear  ----> clear screen
2. whoami    ---> see who is logged in user
3. cd\ ---> Up one directory
4. nano [pathe and filename] ----> File reader writer  
   
**Add / Manage Users**  
1. adduser [username]   ----> Add new user
2. cut -d: -f1 /etc/passwd    ----> see all users in Ubuntu
3. deluser [username]. ----> Delete user 
4. groups [username]     ----> see group of the user
5. rm -r [username].  ----> Remove user home directory 
6.  usermod -aG sudo [username] ----> make user a root user
7.  grep -Po '^sudo.+:\K.*$' /etc/group    ----> See which users belong to sudo group 

**Change SSH port**  
1.  nano /etc/ssh/sshd_config  ----> open ssh configuration file
2.  service ssh restart  ----> restart the ssh service

