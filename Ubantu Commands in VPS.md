# **Ubantu Commands to be used un VPS**  

https://www.hostinger.com/tutorials/ssh/basic-ssh-commands  

1. clear  ----> clear screen
2. ls -a ---> List all directories hidden or not
3. whoami    ---> see who is logged in user
4. adduser [username]   ----> Add new user  
5. cut -d: -f1 /etc/passwd    ----> see all users in Ubuntu  
6. groups [username]     ----> see group of the user  
7. usermod -aG sudo [username] ----> make user a root user  
8. grep -Po '^sudo.+:\K.*$' /etc/group    ----> See which users belong to sudo group  
9. nano [pathe and filename] ----> File reader writer  
10. nano /etc/ssh/sshd_config  ----> open ssh configuration file  
11. service ssh restart  ----> restart the ssh service  

