# **Deploy NextJS App on VPS CybrPanel with Reverse Proxy**
1. Login into your cyber panel with the following URL like this. (your-ip:8090)  
2. Click on the vHost Conf.  
3. The first line should indicate the document root folder path like this
```console
docRoot $VH_ROOT/public_html/dist/<Your-Project-name>/browser/
```
4. In **handler** section adds this code.
```console
scripthandler  {
 add proxy:<Cyber-panel-generated-project-name> html
}
```
5. In **extprocessor** section copy this code and paste it.
```console
type proxy
address <Your Node JS server url like (127.0.0.1:4000)>
maxConns 2000
initTimeout 20
retryTimeout 0
respBuffer 0
```
6. In **Rewrite** section add this code.
```console
rewrite  {
RewriteCond %{HTTP:UPGRADE} ^WebSocket$ [NC]
RewriteCond %{HTTP:CONNECTION} Upgrade$ [NC]
RewriteRule /(.*) ws://<your node js server url>/$1 [P]
  enable                  1
  autoLoadHtaccess        1
}
```
7. Add a new object in this file end of the code.
```console
context / {
type proxy
handler <Cyber-panel-generated-project-name>
addDefaultCharset off
}

### **Note:- Finally our vHost file would be like this code.**
```console
docRoot                   $VH_ROOT/public_html
vhDomain                  $VH_NAME
vhAliases                 www.$VH_NAME
adminEmails               spaceisnotnull@gmail.com
enableGzip                1
enableIpGeo               1

index  {
  useServer               0
  indexFiles              index.php, index.html
}

errorlog $VH_ROOT/logs/$VH_NAME.error_log {
  useServer               0
  logLevel                WARN
  rollingSize             10M
}

accesslog $VH_ROOT/logs/$VH_NAME.access_log {
  useServer               0
  logFormat               "%h %l %u %t "%r" %>s %b "%{Referer}i" "%{User-Agent}i""
  logHeaders              5
  rollingSize             10M
  keepDays                10  
  compressArchive         1
}

scripthandler  {
  add                     proxy:legen5300 php
}

extprocessor legen5300 {
  type proxy
address 127.0.0.1:3001
maxConns 2000
initTimeout 20
retryTimeout 0
respBuffer 0
}

phpIniOverride  {

}

module cache {
 storagePath /usr/local/lsws/cachedata/$VH_NAME
}

rewrite  {
RewriteCond %{HTTP:UPGRADE} ^WebSocket$ [NC]
RewriteCond %{HTTP:CONNECTION} Upgrade$ [NC]
RewriteRule /(.*) ws://127.0.0.1:3001/$1 [P]
 enable                  1
  autoLoadHtaccess        1
}

context /.well-known/acme-challenge {
  location                /usr/local/lsws/Example/html/.well-known/acme-challenge
  allowBrowse             1

  rewrite  {
     enable                  0
  }
  addDefaultCharset       off

  phpIniOverride  {

  }
}

context / {
type proxy
handler legen5300
addDefaultCharset off
}
```
