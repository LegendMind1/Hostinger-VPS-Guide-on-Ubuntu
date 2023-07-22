# **Ubantu Commands to be used un VPS**  

https://www.hostinger.com/tutorials/ssh/basic-ssh-commands  

1. clear  ----> clear screen
2. ls -a ---> List all directories hidden or not
3. pwd  ----> Displays full path to the current prompt
4. whoami    ---> see who is logged in user
5. adduser [username]   ----> Add new user  
6. cut -d: -f1 /etc/passwd    ----> see all users in Ubuntu  
7. groups [username]     ----> see group of the user  
8. usermod -aG sudo [username] ----> make user a root user  
9. grep -Po '^sudo.+:\K.*$' /etc/group    ----> See which users belong to sudo group  
10. nano [pathe and filename] ----> File reader writer  
11. nano /etc/ssh/sshd_config  ----> open ssh configuration file  
12. service ssh restart  ----> restart the ssh service  

