# short-url-nodejs
```
1. Install node.js from --> https://deb.nodesource.com/
2. check node version --> node -v
3. check node package manager version --> npm -v
4. Install mongodb from --> https://www.mongodb.com/docs/manual/tutorial/install-mongodb-on-ubuntu/
5. sudo sytemctl start mongod
6. sudo systemctl enable mongod
7. mongosh
8. test> show dbs
9. test> exit
10. 
11. Clone your project from Github --> git clone <url>
12. go to short-url-nodejs directory
13. cd short-url-nodejs
14. npm install
15. sudo npm i pm2 -g
16. pm2 start index
17. pm2 list
18. npm list
19. npm list -g
20. pm2 startup
21. sudo env PATH=$PATH:/usr/bin /usr/lib/node_modules/pm2/bin/pm2 startup systemd -u ubuntu --hp /home/ubuntu
22. copy and execute the output and make auto start of an node.js app even on reboot
23. mongosh
24. test> show dbs
25. test> use short-url
26. test> show collections
27. exit
28. sudo apt install nginx -y
29. sudo systemctl enable nginx
30. sudo vi /etc/nginx/sites-available/default

server_name yourdomain.com www.yourdomain.com;

location / {
    proxy_pass http://localhost:8001;
    proxy_http_version 1.1;
    proxy_set_header Upgrade $http_upgrade;
    proxy_set_header Connection 'upgrade';
    proxy_set_header Host $host;
    proxy_cache_bypass $http_upgrade;
}

Check NGINX config

sudo nginx -t

Restart NGINX

sudo nginx -s reload

Add SSL with LetsEncrypt
sudo add-apt-repository ppa:certbot/certbot 

sudo apt update 

sudo apt install python3-certbot-nginx 

sudo certbot --nginx -d yourdomain.com -d www.yourdomain.com

Only valid for 90 days, test the renewal process with

certbot renew --dry-run
