# How to access server via ssh and setup ssh key for passwordless authentication
Without setting up SSH Key It will ask Password each time we try to get access

- **To Get Access via SSH**  
Syntax:- ssh -p PORT USERNAME@HOSTIP  
Example:- ssh -p 21350 root@xxx.xxx.xxx.xxx


## **Note:- Run Below Commands on Your Local Machine, Not on Your VPS or Remote Server**

### **Generate SSH Key**  
ssh-keygen [-f C:\Users\username/.ssh/my_key] -t rsa -b 4096  

**Copy SSH Public Key to Remote Server (Not for Windows)  **
Syntax:- ssh-copy-id -p PORT -i ~/.ssh/keyname.pub USERNAME@HOSTIP  
Example:- ssh-copy-id -p 21350 -i ~/.ssh/id_rsa.pub user@xxx.xxx.xxx.xxx  


**Copy Public Key to Remote Server (for Windows)  **

1. **Make sure you have .ssh folder in remote server**  
Syntax:- ssh -P PORT USERNAME@HOSTIP "mkdir /home/USERNAME/.ssh"  
Example:- ssh -P 22 USERNAME@xxx.xxx.xxx.xxx "mkdir /home/USERNAME/.ssh"  

**OR**  

Create in remote/ VPS server using *mkdir .ssh* command

2. **Copy Public Key  **
Syntax:- scp -P PORT SSH_PUBLIC_KEY_PATH USERNAME@HOSTIP:/home/USERNAME/.ssh/authorized_keys  

Example:- scp -P 22 C:\Users\USERNAME/.ssh\id_rsa.pub USERNAME@xxx.xxx.xxx.xxx:/home/USERNAME/.ssh/authorized_keys  
