## VMWARE - INSTALL UBUNTU SERVER

### Requirements
- Install Ubuntu Server 18.x with VMware.
- Create swap memory and root partition.
- Local server can connect to the internet.

## VMWARE - SETUP NETWORK

### Requirements
- Change network from NAT to Bridge
- Setup static IP for Ubuntu Server

## VMWARE - SERVER FOR APPLICATION

### Requirements
- Update and upgrade the system operation.
- Install node.js 10.x
- Clone application in here https://github.com/sgnd/dumbplay-frontend
- Change directory to **frontend** and deploy the application.

## CREATE & SETUP SERVER

### Requirements
- Create a server with Ubuntu 18.x OS.
- Create two servers for reverse proxy and application with AWS.
- Server for reverse proxy need a public IP address.
- Server for the application only has a private IP address.
- Setup security group and open ports 22, 80, and 443 for reverse proxy.
- Setup security group and open all traffic for the application.

## SERVER FOR APPLICATION

###  Requirements
- Update and upgrade the system operation.
- Install node.js 10.x
- Clone application in here https://github.com/sgnd/dumbplay-frontend
- Change directory to **frontend** and deploy the application.

## SERVER FOR REVERSE PROXY

###  Requirements
- Update and upgrade the operating system.
- Install webserver for reverse proxy.
- Create reverse proxy from the application with port 3000 to port 80


## CUSTOM DOMAIN

### Requirements
- Please send your email to the group chat to invite in Cloudflare.
- Setup subdomain for the application **name.onlinecamp.id**

## SSL CONFIGURATION

### Requirements
- Install free SSL certificate for web server with let's encrypt
- The applications can access from **https://**

