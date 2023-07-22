# **Ubantu Commands to be used un VPS**  

https://www.hostinger.com/tutorials/ssh/basic-ssh-commands  

clear  ----> clear screen

whoami    ---> see who is logged in user

adduser [username]   ----> Add new user  
cut -d: -f1 /etc/passwd    ----> see all users in Ubuntu  
groups [username]     ----> see group of the user  
usermod -aG sudo [username] ----> make user a root user  
grep -Po '^sudo.+:\K.*$' /etc/group    ----> See which users belong to sudo group  

nano [pathe and filename] ----> File reader writer  
nano /etc/ssh/sshd_config  ----> open ssh configuration file  
service ssh restart  ----> restart the ssh service  