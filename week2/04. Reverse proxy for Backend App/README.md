# REVERSE PROXY

## A. Requirements
- Update and upgrade the operating system.
- Install web server for reverse proxy.
- Create reverse proxy from application with port 5000 to port 80

### 
## 

- Login ke instance gateaway.

- Update dan upgrade.

- Install nginx.

- Masuk ke folder /etc/nginx/dumbplay.

![image](https://user-images.githubusercontent.com/88620315/139601199-cee93f51-4b39-4aca-a707-f9693869448b.png)

- Buat sebuah file config untuk backend app api.nicky.onlinecamp.id.

- Edit arahkan proxy_pass ke ip private server backend.

![image](https://user-images.githubusercontent.com/88620315/139601235-0f40d13d-bda6-4ac1-80fc-bc4fc685dc38.png)

- Test config file 

>sudo nginx -t
