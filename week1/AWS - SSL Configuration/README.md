Login dan masuk ke dashboard cloudflare.

Pada bagian account klik my profile.

Masuk ke halaman API tokens.

![image](https://user-images.githubusercontent.com/88620315/138643056-4c4e073e-80f4-4794-a5fc-2a289ed95828.png)

view Global API key 

![image](https://user-images.githubusercontent.com/88620315/138643782-e83b999a-eeaf-419d-b3d8-a8cc5d32b2d2.png)


Masukkan password dan verifikasi untuk mendapatkan key.

Copy dan simpan api key.

Login ke server.

Buat folder kemudian di dalamnya buat file untuk menyimpan api key cloudflare.

![image](https://user-images.githubusercontent.com/88620315/138646072-02048920-352d-49de-9bce-ad309b80f4fb.png)

Di dalam file masukkan email dan api key.

> dns_cloudflare_email = "youremail@example.com"
> dns_cloudflare_api_key = "4003c330b45f4fbcab420eaf66b49c5cbcab4"

![image](https://user-images.githubusercontent.com/88620315/138648713-adb6538f-edb6-4393-8a0d-0c86c2efa09c.png)

> sudo chmod 700 .cloudflare


> sudo chmod 400 .cloudflare/api-key.ini


![image](https://user-images.githubusercontent.com/88620315/138677826-504f411e-c9ad-46b2-ad5a-2a9b62406958.png)
### Install Certbot and the CloudFlare DNS authenticator plugin

Update snapd sudo snap install core; 
> sudo snap refresh core.

Install certbot 
> sudo snap install --classic certbot.

Link certbot dari /snap/bin/certbot ke /usr/bin/certbot 
> sudo ln -s /snap/bin/certbot /usr/bin/certbot.

![image](https://user-images.githubusercontent.com/88620315/138678713-e9bbedd5-cfd1-4b4a-bc3a-4149be9c4a27.png)

> sudo certbot --nginx

![image](https://user-images.githubusercontent.com/88620315/138680267-11de3471-9459-4555-a92a-2a4224bcd441.png)

> cd /etc/nginx/dumbplay

> cat nicky.onlinecamp.id 
 

![image](https://user-images.githubusercontent.com/88620315/138681378-2f327294-d9a9-43d3-a287-b3f23f84ca59.png)

> sudo nginx -t

> sudo systemctl reload nginx

![image](https://user-images.githubusercontent.com/88620315/138682053-543f4735-62d2-40dd-87ab-c9552c91c61d.png)

run nicky.onlinecamp.id on browser

![image](https://user-images.githubusercontent.com/88620315/138682086-58321b9e-2e11-40f1-a60c-d671acd2dca7.png)
