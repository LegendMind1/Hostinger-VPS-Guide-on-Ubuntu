# **Hostinger CyberPanel VPS DNS records for mail server**  

### **- Step 1 – Setup VPS and Create Site**  
### **- Step 2 – Setup VPS and Create Site**  
### **- Step 3 - Add A, AAAA and TXT Records in DNS Records at Web Domain like GoDaddy from where you purchased domain  

| Type  | Name | Content | TTL  |
| ----- | ---- | ------- | ---- |
| AAAA  | mail | IPv6 | Auto   |
| AAAA  | smtp | IPv6 | Auto  |
| A  | mail | IPv4 | Auto   |
| A  | smtp | IPv4 | Auto  |
| MX  | domain.com | mail.domain.com | 0  |
| TXT  | default_domainkey | dkim (From Cyber Panel)  |   |
| TXT  | domain.com | v=spf1 ip6:Domain IPv6 ip4:Domain IPv4 ~all  |   |
| TXT  | domain.com | v=DMARC1; p=none; rua=mailto:emailuser@yourdomain.com  |   |  

### **Note: replace domain.com with your domain and ip, email where applicable. If your server do not have ipv6 address you can skip those records.** 