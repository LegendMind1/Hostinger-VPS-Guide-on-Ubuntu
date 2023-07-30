# **PM2 Commands for NexJS App Deployment**
- npm install -g pm2 ---> Install PM2 on Apache Ubuntu 22.04
- pm2 start npm --name "[name of your NextJS app in package.json]" -- start
  **or**
- PORT=3001 pm2 start npm --name "[name of your NextJS app in package.json]" -- start ---> Start NextJS App with PM2 on specified port
- pm2 status  ---> Check status of PM2
- pm2 kill  ---> Kill the process if errored out
  **or**  
- pm2 restart Server ---> To restart it
- pm2 flush ---> Used after killing process so all logfiles will be reset  

**Note:** chmod -R +x [node_modules] ---> The chmod +x command makes a file or a directory executable. This command may come handy in the event of error saying 'sh: 1: next: Permission denied'  