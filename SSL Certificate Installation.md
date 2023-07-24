# **How to Enable HTTPS in Your Domain Hosted on Linux Remote Server or VPS**  

### **Note: Let's Encrypt is a non-profit certificate authority run by Internet Security Research Group that provides X.509 certificates for Transport Layer Security encryption at no charge.**  

**To Access Remote Server via SSH**  
Syntax:- ssh -p PORT USERNAME@HOSTIP  
Example:- ssh -p 22 root@xxx.xxx.xxx.xxx  

**Install Certbot and python3-certbot-apache**  
apt install certbot python3-certbot-apache  

Note: Certbot is a free, open source software tool for automatically using Let’s Encrypt certificates on manually-administrated websites to enable HTTPS.
python3-certbot-apache is a Apache plugin for Certbot.  

**Verify Web Server Ports are Open and Allowed through Firewall**  
ufw status verbose

**Obtain an SSL certificate**  
certbot --apache

**Check Status of Certbot**  
systemctl status certbot.timer

**Dry Run SSL Renewal**  
certbot renew --dry-run