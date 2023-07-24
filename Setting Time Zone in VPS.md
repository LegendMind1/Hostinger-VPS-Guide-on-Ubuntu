# **How to Set TimeZone** 
 
**To Get Access via SSH**  
Syntax:- ssh -p PORT USERNAME@HOSTIP  
Example:- ssh -p 21350 root@xxx.xxx.xxx.xxx    

**Check Current System Time Zone**  
timedatectl  

**Check All TimeZone**  
timedatectl list-timezones  

**Filter TimeZone by City**  
Syntax:- timedatectl list-timezones | grep City_Name  
Example:- timedatectl list-timezones | grep Karachi  

**Set TimeZone**  
Syntax:- timedatectl set-timezone [timezone]  
Example:- timedatectl set-timezone Asia/Karachi  