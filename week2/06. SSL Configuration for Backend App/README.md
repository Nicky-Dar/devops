# SSL CONFIGURATION

## Requirements
- The applications can access from **https://**api.name.onlinecamp.id

masuk ke frontend
>nano dumbplay-fronted/src/config/api.js

>ubah baseURL: 'http://localhost:5000/api/v1' -> baseURL: api.nicky.onlinecamp.id/api/v1'

- ![image](https://user-images.githubusercontent.com/88620315/139676037-c802b371-43c4-439d-a95d-7ae253a1c0fd.png)

- restart aplikasi
>pm2 restart all

Masuk ke gateaway
>sudo certbot certonly -d api.nicky.onlinecamp.id

![image](https://user-images.githubusercontent.com/88620315/139676227-c58aeaab-b912-4bd5-8aed-7a8045fbe82e.png)

![image](https://user-images.githubusercontent.com/88620315/139676243-799633fe-6c0b-4baf-8d18-e5f15d8ca8e2.png)

pilih 1 ( nginx ) 

![image](https://user-images.githubusercontent.com/88620315/139676276-0d5f71bd-337c-4c71-85ab-7bec5983c7ea.png)

![image](https://user-images.githubusercontent.com/88620315/139676363-357c36e7-9a23-429c-9b13-189bd5a2bccf.png)

![image](https://user-images.githubusercontent.com/88620315/139676435-72912702-fc16-4518-aed4-e0501998d200.png)

![image](https://user-images.githubusercontent.com/88620315/140001755-a45218ef-214b-4c1b-b9bb-57de6f668fd4.png)
