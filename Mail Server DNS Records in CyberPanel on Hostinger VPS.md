# **Hostinger CyberPanel VPS DNS records for mail server**  

### **- Step 1 – Setup VPS and Create Site**  
### **- Step 2 – Setup VPS and Create Site**  
### **- Step 3 - Add A, AAAA and TXT Records in DNS Records at Web Domain like GoDaddy from where you purchased domain**   

| Type  | Name | Content | TTL  |
| ----- | ---- | ------- | ---- |
| AAAA  | mail | IPv6 | Auto   |
| AAAA  | smtp (no need for GoDaddy) | IPv6 | Auto  |
| A  | mail | IPv4 | Auto   |
| A  | smtp (no need for GoDaddy) | IPv4 | Auto  |
| MX  | domain.com OR mail (if on GoDaddy) | mail.domain.com | 0  |
| TXT  | default_domainkey OR OR mail (if on GoDaddy) | dkim (From Cyber Panel)  |   |
| TXT  | domain.com OR mail (if on GoDaddy) | v=spf1 ip6:Domain IPv6 ip4:Domain IPv4 ~all  |   |
| TXT  | domain.com OR mail (if on GoDaddy) | v=DMARC1; p=none; rua=mailto:emailuser@yourdomain.com  |   |  

### **Note: Replace domain.com with your domain and ip, email where applicable. If your server does not have ipv6 address you can skip those records.** 

### **Note 2: If you are using IPv6 for Email (Gmail and lot others have it as mandatory setting) You must have added IPv6 @ records for AA and AAAA too.**  

### **Note 3: Gmail is strictly enforcing PTR records too, otherwise you may recieve email in your mail server but won't be able to send to Gmail. Adding PTR records in Hostinger is piece of cake, just add yourdomain.com in IP Address Tab in Hostinger VPS HPanel through Add PTR Records button for both IPv4 and IPv6**  


## **Caution**  
When creating DKIM settings the permission error on following file/ folders might occuer in Cyber Panel:
```console
/usr/local/CyberCP/lib/python3.10/site-packages/tldextract/.suffix_cache/publicsuffix.org-tlds/de84b5ca2167d4c83e38fb162f2e8738.tldextract.json.lock
```
### **Steps to resolve the error on Ubuntu 22.04 64bit with CyberPanel**  
1. **Change the python3.10 version to your version** 
2. **Delete subfolders (Optional)**  
```console
publicsuffix.org-tlds/de84b5ca2167d4c83e38fb162f2e8738.tldextract.json.lock
```
3. **Run this command without sudo:**  
```console
chown -R cyberpanel:cyberpanel /usr/local/CyberCP/lib/python3.8/site-packages/tldextract/.suffix_cache/
```

# Success.
### For more useful information you may visit http://legendsol.com