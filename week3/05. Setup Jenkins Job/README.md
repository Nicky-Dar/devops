After done with the user configuration, we can start using jenkins![image](https://user-images.githubusercontent.com/88620315/140757530-0819063f-ec3e-4249-94bd-c032b3a200df.png) 
![image](https://user-images.githubusercontent.com/88620315/140756294-9165a152-d078-43f5-aecf-a1e804b28931.png)

 ## Create job for jenkins
  
![image](https://user-images.githubusercontent.com/88620315/140756339-3869f455-a18c-40c3-87e3-605c8dcbe4fb.png)

![image](https://user-images.githubusercontent.com/88620315/140756356-5343aaa6-cbf1-47db-ba71-09a5f34851a7.png)


Installasi plugin

Manage Jenkins > manage plugins
 
![image](https://user-images.githubusercontent.com/88620315/140756692-d3ca9f16-18db-4dab-b82f-7e61cf7d6b35.png)

 
![image](https://user-images.githubusercontent.com/88620315/140756712-ece5d813-183c-4cb2-be92-2982fb50acd3.png)

![image](https://user-images.githubusercontent.com/88620315/140756745-d3a59a60-f6c3-48e5-a67f-2404feecdf96.png)

 

- Pada menu key bisa masukan RSA key
- Config ssh server
- Timeout -> 0


![image](https://user-images.githubusercontent.com/88620315/140756817-67268839-1611-4118-b27c-9412b2b80516.png)


 ```
cd /home/ubuntu/dumbplay-frontend
git pull origin master
npm install
pm2 restart ecosystem.config.js
```

 ![image](https://user-images.githubusercontent.com/88620315/140757530-0819063f-ec3e-4249-94bd-c032b3a200df.png)


- Log in into git hub
- Masuk ke repositori
- Setting 
- Webhook

 
![image](https://user-images.githubusercontent.com/88620315/140757597-6c0c8431-c2dc-4991-9d5c-764e36633666.png)

`http://3.80.84.48:8080/github-webhook/`
 
![image](https://user-images.githubusercontent.com/88620315/140757671-916adc09-8c36-4ff6-af89-14d652f08653.png)


Login ke jenkins server.
Install slack notification plugin

![image](https://user-images.githubusercontent.com/88620315/140757710-cac38832-9c70-4e29-965d-65c8434742b1.png)
