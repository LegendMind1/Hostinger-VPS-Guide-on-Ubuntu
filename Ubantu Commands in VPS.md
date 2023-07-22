# **Ubantu Commands to be used un VPS**  

https://www.hostinger.com/tutorials/ssh/basic-ssh-commands  

1. clear  ----> clear screen
2. whoami    ---> see who is logged in user
3. adduser [username]   ----> Add new user  
4. cut -d: -f1 /etc/passwd    ----> see all users in Ubuntu  
5. groups [username]     ----> see group of the user  
6. usermod -aG sudo [username] ----> make user a root user  
7. grep -Po '^sudo.+:\K.*$' /etc/group    ----> See which users belong to sudo group  
8. nano [pathe and filename] ----> File reader writer  
9. nano /etc/ssh/sshd_config  ----> open ssh configuration file  
10. service ssh restart  ----> restart the ssh service  

