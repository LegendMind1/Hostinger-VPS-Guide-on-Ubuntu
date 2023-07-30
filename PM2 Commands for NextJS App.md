# **PM2 Commands for NexJS App Deployment**
- npm install -g pm2 ---> Install PM2 on Apache Ubuntu 22.04
- pm2 start npm --name "[name of your NextJS app in package.json]" -- start
- pm2 status  ---> Check status of PM2
- pm2 kill  ---> Kill the process if errored out
  **or**  
- pm2 restart Server ---> To restart it
- pm2 flush ---> Used after killing process so all logfiles will be reset
